[[dataview的演示2]]
[[dataview的演示3]]
[[dataview的演示4]]

# 案例1
以表格形式展示所有标签带有“美图”卡片中Yaml内的Date，并且按文件的创建时间降序。

```dataview
table Date from #美图 
sort file.ctime desc
```

# 案例2
展示"10 演示文件夹/dataview插件演示"文件夹内所有的任务，包括TODO和DONE。

```dataview
task FROM "10 演示文件夹/dataview插件演示"
```

202107122050这节演示在我移动后失效了，我也不懂得编写。有问题还是问Bon吧

# 案例3
以列表形式展示所有标签带有“美图”卡片，并且按文件的大小升序。

```dataview
list from #美图 
sort file.size asc
```