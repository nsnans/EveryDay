# cut命令
`cut`命令用来显示行中的指定部分，其从文件的每一行剪切字节、字符和字段并将这些字节、字符和字段写至标准输出。如果不指定`File`参数，`cut`命令将读取标准输入，该命令常用的两项功能，一是用来显示文件的内容，它依次读取由参数`file`所指明的文件，将它们的内容输出到标准输出上，其二是连接两个或多个文件，如`cut f1 f2 > f3`将把文件`f1`和几的内容合并起来，然后通过输出重定向符`>`的作用，将它们放入文件`f3`中。当文件较大时，文本在屏幕上迅速闪过，也就是滚屏现象，为了控制滚屏，可以执行`Ctrl+S`按键停止滚屏，按`Ctrl+Q`键可以恢复滚屏，按`Ctrl+C`键终止该命令的执行等操作。

## 语法

```shell
cut [OPTION]... [FILE]...
```

## 参数
* `-b`: 仅显示行中指定直接范围的内容。
* `-c`: 仅显示行中指定范围的字符。
* `-d`: 指定字段的分隔符，默认的字段分隔符为`TAB`。
* `-f`: 显示指定字段的内容。
* `-n`: 与`-b`选项连用，不分割多字节字符。
* `--complement`: 补足被选择的字节、字符或字段。
* `--out-delimiter=<delimiter>`: 指定输出内容是的字段分割符。
* `--help`: 显示指令的帮助信息。
* `--version`: 显示指令的版本信息。

## 示例

截取`/tmp/file.txt`文件每一行的第`3`个字符。

```shell
cat /tmp/file.txt | cut -c 3
# 3
# 4
# 5
# 6
# 7
# 8
# 9
# 0
# 1
# 2
```

截取`/tmp/file.txt`文件每一行的第`3-6`个字符。

```shell
cat /tmp/file.txt | cut -c 3-6
# 3456
# 4567
# 5678
# 6789
# 7890
# 8901
# 9012
# 0123
# 1234
# 2345
```

截取`/tmp/file.txt`文件每一行的第`3`个字符到结尾字符。

```shell
cat /tmp/file.txt | cut -c 3-
# 34567890
# 45678901
# 56789012
# 67890123
# 78901234
# 89012345
# 90123456
# 01234567
# 12345678
# 23456789
```


## 每日一题

```
https://github.com/WindrunnerMax/EveryDay
```

## 参考

```
https://man.linuxde.net/cut
https://www.runoob.com/linux/linux-comm-cut.html
https://www.tutorialspoint.com/unix_commands/cut.htm
```
