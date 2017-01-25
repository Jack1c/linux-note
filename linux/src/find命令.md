## find

使用格式:
+ find [搜索范围] [搜索条件] 搜索文件

例如:
+ `find /root -name install.log`         在 `/root` 目录下搜索 'install.log文件'
+ `find /root -iname  install.log`  不区分大小写搜索 
+ `find /root -nouser `             搜索没有所有者的文件

+ `find /var/log/ -mtime + 10 ` 查找10天前修改的文件
    + `-10` 10天内修改文件
    + `10` 10当天修改的文件
    + `+10` 10天前修改的文件
    
 +  `atime`  文件访问时间
 +  `ctime` 改变文件属性
 +  `mtime`  修改文件内容

+ `find . size 25k` 查找出文件大小是25k的文件
    + > 兆:M
    + > G 
    
    +  `-25k`    小于25k的文件
    +  `25k`     等于25k的文件
    +  `+25k`    小于25k的文件
        
+ `find . inum 262422` 查找i节点是262422的文件    

混合条件: 
`find /etc -size +20k -a -size -50k` 查找/etc/ 目录下大于20k小于50k的文件
+ `-a`  and 逻辑与,两个条件都满足
+ `-o`  or  逻辑或,两个条件满足一个就可以 

`find /etc -size +20k -a -size -50k -exec ls -lh {} \;` 查找/etc/ 目录下大于20k小于50k的文件,并显示详细信息
 > | `-exec/-ok 命令 {} \;` 对搜索结果执行操作
    
    

*注意:*
+ 避免大范围搜索,会非常耗费系统资源
+ find在系统中搜索符合条件的文件名.如果需要匹配,使用通配符,通配符是完全匹配


###Linux 中的通配符
+ `*` 匹配任务内容
+ `?` 匹配任意一个字符
+ `[]` 匹配任意一个中括号内的字符



