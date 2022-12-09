---
uid: 20221016220023
aliases: []
---
参考[[熱字串自動補全外掛Various Complements by 简睿]]
Main部分
Strategy选择default
Match strategy选择prefix（开头匹配）
Max number of suggestion输入多少个字符就触发补全，设置为3
Max number of suggestions给出多少个建议，设置 为15

Custom dictionary complement 字典档案
需要开启，开启后设置如下
Custom dictionary paths，可以指定线上（默认），但删除它，我们指定本地的md文字
Column delimiter分隔符选择，建议选择Pipe（即符号“|”），不建议使用TAB或者逗号

Delimiter to hidea suggestion设置为`+=`
Delimiter to divide suggestions for display from ones for insertion设置为`=>`
Caretlocation symbol after complement设置为`$END$`

范例1
`要插入的文字|说明内容|快捷键1|快捷键2`
`Look good to me|LGTM|lgtm`代表了输入LGTM或者lgtm，就能补全Look good to me

范例2
`co-bug=>> [!ERROR] 异常\n> $END$ | 🐞异常提示区块 |cob|ad-bug`
输入`cob`的提示`🐞异常提示区块`，输入的内容是`> [!ERROR] 异常\n> $END$ `，这是因为有`=>`的存在（上面设置了“Delimiter to divide suggestions for display from ones for insertion”），所以输入之后的内容

可以使用Ctrl+Shift+Space 弹出可视化的界面添加信息