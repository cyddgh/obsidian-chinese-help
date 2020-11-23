用python来维护ob笔记 by [[shaosen]]
感兴趣可以将下面的代码块另存为“20201121 python维护笔记.py”后运行
运行环境：python 3.X
后续代码更新地址： https://gitee.com/vken/md_note/tree/master/
[[落山鸡]]提醒：运行代码有风险，请注意数据备份，如有能力请审视代码。
```
#! /usr/bin/env python 
# -*- coding: utf-8 -*
#使用前请做好备份，在不同设备上运行效果可能不一致，有可能损坏笔记数据；使用时请将rootdir(第9行）切换成自己的笔记地址，第9行(logdir)指定日志输出路径；20201122修复多个相同链接重复替换，转义不替换；bug:网址可能会胡乱替换
import os
import time
import re  # 导入正则表达式
import urllib.parse  # 导入urllib.parse模块，用于url转义，urllib模块主要用于url请求相关内容；
now = time.strftime("%Y-%m-%d-%H_%M_%S",time.localtime(time.time())) 
rootDir = r"D:\笔记\笔记"  #笔记文件夹地址，需要注意的是地址最后一位不能是\
logdir = "C:/Users/vkss/Desktop/"#运行记录保存文件夹
logdir1 = logdir+now+r"jreport.md"
logdir2 = logdir+now+r"lreport.md"
wenjian = {}  # 空字典wenjian，用于存储文件路径及内容，key为文件路径，值为对象，20201117
wjmm = []  # 空列表wjm，用于存储文件名
wjcm = []  # 空列表wenjianming，用于存储重名文件，20201117
jlog = ""#用于存储简单log
llog = ""#用于存储详细log

class Md():
    """对md文件进行操作"""

    def __init__(self, lujing, wjlb):
        """初始化路径"""
        self.lujing = lujing
        self.nr = ""  # md文档内容
        self.nr1 = ""# md原始文档内容
        self.lj = []  # md文档内链接
        self.ydqnr = 0  # 已读取内容，修改为1
        self.xg = 0  # 是否需要修改，如果需要改为1
        self.wjlb = wjlb  # 文件列表
        self.jlog = "" #保存简单修改log
        self.llog = "修改的文档:\n" #保存详细修改前后文件

    def dqnr(self):
        """读取md内容"""
        if self.ydqnr == 0:  # 如果已经读过了，应该跳过
            with open(lujing, encoding='utf-8') as f:
                self.nr = f.read()  # md文档内容
                self.nr1 = self.nr# 将nr复制到nr1，测试不会变

    def urlxg(self):
        """修改url"""
        self.dqnr()
        self.lj = re.findall(r"\]\(.*?\)", self.nr)
        tslj = []#特殊链接，比如http，file
        for i in self.lj:#挑出特殊链接
            if i[2:8] == "https:" or i[2:7] == "http:" or i[2:10] =="file:///":
                tslj.append(i)
        for i in tslj:#从地址列表中删除特殊链接
            self.lj.remove(i)

        for i in range(0, len(self.lj)):
            ddzjbl = urllib.parse.unquote(self.lj[i]).replace(" ", "%20")  # 中间变量
            if self.lj[i] != ddzjbl:
                # 首先将dd[i]从url转换成普通字符，再用%20替换掉空格
                self.nr = self.nr.replace(self.lj[i], ddzjbl)
                self.jlog = self.jlog+"\n\n"+lujing+":转义了地址\n\n"+self.lj[i]+"\n\n"+ddzjbl
                self.xg = 1
                self.lj[i] = ddzjbl

    def cxwj(self):
        """重写文件，会在写之前判断是否需要写"""
        if self.xg == 1:
            # 写入文件，a表示追加，w表示覆盖写入，,encoding='utf-8'表示以UTF8编码
            with open(self.lujing, 'w', encoding='utf-8') as f:
                f.write(self.nr)
                self.xg == 0  # 写完了，就不用再写了，修改标志改为0
            self.llog = self.llog+lujing+"\n"+self.nr1+"\n"+self.nr+"\n\n"

    def whlj(self):
        """维护链接"""
        self.urlxg()        
        for wjm in set(self.lj):#集合就可以了
            wjm1 = self.ljxz(wjm)
            # 拆解出文件名
            if wjm[2:-1] != wjm1:
                self.nr = self.nr.replace(wjm[2:-1], wjm1)
                self.xg = 1
                self.jlog = self.jlog+"\n\n"+lujing+":修改了地址\n\n"+wjm[2:-1]+"\n\n"+wjm1

    def ljxz(self, wjm):
        """链接修正，输入链接文件名，返回正确相对链接"""
        wjm = wjm[2:-1]
        dd3 = wjm
        wjm=wjm[wjm.rfind("/")+1:]
        if len(wjm) == 0:
            return dd3#如果拆出的文件名是空，那么就返回链接
        zjbl = 0
        wjm = wjm.replace("%20"," ")
        for ljj in self.wjlb:
            # 查找文件名,先不考虑重名的问题
            a1 = ljj.replace("/","\\").split("\\")
            try:
                if a1[-1].index(wjm) == 0:#链接中地址与路径中地址从0匹配
                    if len(a1[-1])>len(wjm) and wjm.find(".",len(wjm)-5)>0:
                        continue#后4位有小数点，认为是有后缀，应该完全匹配。但如果名字就带了小数点，可能会出现搜索不到，或者匹配错误，这极少发生
                    elif len(a1[-1])-len(wjm) > 5:
                        continue#如果长度差大于5，跳过，认为后缀最长为4
                    # 计算相对路径
                    b1 = self.lujing.replace("/","\\").split("\\")
                    for i in range(0, max(len(a1), len(b1))):
                        if a1[i] != b1[i]:
                            # join是把列表转化为字符串，用空""连接，这是求得的相对路径
                            dd = "../"*(len(b1)-i-1)+"/".join(a1[i:])
                            dd = urllib.parse.unquote(dd).replace(" ","%20")
                            zjbl = 1
                            return dd
                    break
            except ValueError:#这里以后写，无目标的链接
                continue
          # 相对路径比较
        if zjbl == 0:
            return dd3


def bianLi(rootDir):  # 遍历文件夹
    for root, dirs, files in os.walk(rootDir):
        for file in files:
            # 将路径存为wenjian字典的key，20201117
            wenjian[os.path.join(root, file)] = "彡"
            wjcm.append(os.path.join(root, file))
        for dir in dirs:
            bianLi(dir)


bianLi(rootDir)
for lujing in wenjian.keys():
    if lujing[-3:] == ".md":
        wenjian[lujing] = Md(lujing, wjcm)  # 类
        wenjian[lujing].whlj()
        wenjian[lujing].cxwj()
        if wenjian[lujing].xg == 1:
            jlog=jlog+wenjian[lujing].jlog
            llog=llog+wenjian[lujing].llog

with open(logdir1,'w',encoding='utf-8',errors='ignore') as f:
   f.write(jlog)#将简单日志输出到文件
with open(logdir2,'w',encoding='utf-8',errors='ignore') as f:
   f.write(llog)#将详细日志输出到文件
```