---
title: shell脚本学习
date: 2022-04-24 12:34:00 +0800
categories: [编程]
tags: [Linux]
pin: false
author: 东三儿

toc: false
comments: true

math: false
mermaid: true

typora-root-url: ../../penciler-star.github.io

---

![bash](/assets/blog_res/2022-04-24-first-shell.assets/bash.png)

# 文件生成、编辑和执行

#### 生成和编辑.sh文件

```shell
touch test.sh
vi test.sh
```

#### 执行.sh文件

```shell
. test.sh
```

# shell脚本

#### 简单的输出hello world

```shell
#! /bin/bash

str="hello world!"
echo $str
```

#### 传入变量

```shell
#! /bin/bash

#$1表示传入的第一个参数，$@表示传入的全部参数
str="hello $1!"
echo $str
```

#### 表达式运算

```shell
#! /bin/bash

sum=$[ 5 + 7 ]
echo $sum
```

#### if条件判断

```shell
#! /bin/bash

if [ 3 -gt 1 ] && [ 3 -lt 4 ]
then
	echo "OK";
else
	echo "FALSE";
fi
```

#### for循环

```shell
#! /bin/bash

#第一种
sum=0
for((i=1;i<=100;i++));
do
	sum=$[ $sum + $i ];
done
echo $sum

#第二种
sum=0
for i in {1..100}
do
	sum=$[ $sum + $i ];
done
echo $sum
```

#### 函数

```shell
#! /bin/bash

function add()
{
	sum=$[ $1 + $2 ];
	echo $sum
}
my_sum=`add 1 3`
echo $my_sum
```

#### 其他命令

```shell
#! /bin/bash

#执行后的返回值
$?
#输入参数的个数
$#
#输入所有的参数
$*

str="/home/test/a.sh"
#删除str的第一个/及其前面的所有内容"home/test/a.sh"
${str#*/}
#删除str的最后一个/及其前面的所有内容"a.sh"
${str##*/}
#删除str的最后一个/及其后面的所有内容"/home/test"
${str%/*}
#删除str的第一个/及其后面的所有内容""
${str%%/*}
```

