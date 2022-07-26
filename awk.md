#### awk内置变量



```
FS：输入字段分隔符， 默认为空白字符

OFS：输出字段分隔符， 默认为空白字符

RS：输入记录分隔符(输入换行符)， 指定输入时的换行符

ORS：输出记录分隔符（输出换行符），输出时用指定符号代替换行符

NF：number of Field，当前行的字段的个数(即当前行被分割成了几列)，字段数量

NR：行号，当前处理的文本行的行号。

FNR：各文件分别计数的行号

FILENAME：当前文件名

ARGC：命令行参数的个数

ARGV：数组，保存的是命令行所给定的各参数
```

#### 添加文件名

```bash
awk '{printf("%s,%s\n",FILENAME,$0)}' *.csv > all.dat
```

#### 大/小写

```bash
$ echo Wps | awk '{printf("%s\n",toupper($0))}'
WPS
$ echo Wps | awk '{printf("%s\n",tolower($0))}'
wps
```

#### 取环境变量

```bash
$ echo Wps | awk '{printf("%s\n", ENVIRON["LANG"])}'
en_US.UTF-8
```

#### 添加/替换字段

```basj
$ echo a b c | awk '{$4="d"; print $0}'
a b c d
$ echo a b c | awk '{$1="d"; print $0}'
d b c
```

#### 设置FS/OFS

```bash
$ echo a,b,c,d | awk 'BEGIN{FS=",";OFS=","} {print $0}'
a,b,c,d

# 替换了内容, 也可以替换文件的
$ echo a,b,c,d | awk 'BEGIN{FS=",";OFS=","} {$3="haha";print $0}'
a,b,haha,d
```

#### 对指定的列进行汇总

```bash
# 对第二列rss进行汇总
ps -u postgres o pid,rss:20,cmd | awk 'NR>1 {A+=$2} {print} END{print "Total RSS:" A}'
```