---
title: Linux 整理
date: 2017-05-02 12:31:33
tags:
    - 前端
    - 个人
    - 复制粘贴专用
---
整理了日常常用的 Linux 命令及英译，并不是所有的，只是我平时常用到的（oh my zsh 下）。
<!--more-->

# 目录
1. **[ls](#ls)**
2. **[cd](#cd)**
3. **[pwd](#pwd)**
4. **[mkdir](#mkdir)**
5. **[rm](#rm)**
6. **[mv](#mv)**
7. **[cp](#cp)**
8. **[touch](#touch)**


## <a name="ls"></a>ls

英译：（list）

格式：ls [选项] [目录名]

ls命令是linux下最常用的命令，主要可以查看文件（夹）

- `-a` : all 列出目录下所有文件
- `-l` : list 除了列出文件名，还将文件的权限，所有者，文件大小等信息列出
- `-r` : reverse 反次序排列
- `-t` : time 按时间排序

**举例：**

- 列出当前目录中所有以“t”开头的目录的文件并且愈新的排愈后面，可以使用如下命令：
  ```zsh
  ls -ltr t*   
  ```
- 只列出文件下的子目录
  ```zsh
  ls -F |grep /$  
  ```
- 计算当前目录下的文件数和目录数
  ```zsh
  ls -l * |grep "^-"|wc -l ---文件个数  
  ls -l * |grep "^d"|wc -l    ---目录个数
  ```
----

## <a name="cd"></a>cd

英译：（change directory）

格式：cd [目录名]

cd命令也是linux下最常用的命令，主要可以切换目录

**举例：**

- 返回进入此目录之前所在的目录
  ```zsh
  cd -
  ```
----

## <a name="pwd"></a>pwd

英译：（print work directory）

格式：pwd [选项]

pwd 命令来查看”当前工作目录“的完整路径

----

## <a name="mkdir"></a>mkdir

英译：（make directory）

格式：mkdir [选项] 目录

mkdir 命令用来创建指定的名称的目录,不能重名

- `-p` : parents 可以是一个路径名称。此时若路径中的某些目录尚不存在,加上此选项后,系统将自动建立好那些尚不存在的目录,即一次可以建立多个目录;

**举例：**

- 一个命令创建项目的目录结构
  ```zsh
  mkdir -p test/{lib/,bin/,doc/{info,product},logs/{info,product},service/deploy/{info,product}}
  ```
----

## <a name="rm"></a>rm

英译：（remove）

格式：rm [选项] 文件

rm 命令用来删除一个目录中的一个或多个文件或目录

- `-f` : force 直接删除，不出现提示;
- `-r` : recursive 将所有目录和子目录均递归地删除。

**举例：**

- 将 test 目录及子目录中所有档案删除,并且不用一一确认
  ```zsh
  rm -rf test
  ```
----

## <a name="mv"></a>mv

英译：（move）

格式：mv [选项] 文件

mv 命令是move的缩写，可以用来移动文件或者将文件改名

- `-f` : force 直接复制，如出现同名文件，直接替换，不出现提示;
- `-i` : 如果出现同名，会提示。

**举例：**

- 把当前目录的的 a.txt 文件换名为 b.txt
  ```zsh
  mv a.txt b.txt
  ```

- 把当前目录的的.txt文件移动到另一个目录里
  ```zsh
  mv test/*.txt test-other
  ```
----

## <a name="cp"></a>cp

英译：（copy）

格式：cp [选项] 源 目的

mv 命令是move的缩写，可以用来移动文件或者将文件改名

- `-R,-r` : recursive 递归复制目录及目录内所有内容;
- `-l` : 链接文件而不复制

**举例：**

- 复制的 log.log 建立一个连结档 log-link.log,建立的是一个“快捷方式”
  ```zsh
  cp -s log.log log-link.log

  //[root@localhost test]# ll
  //lrwxrwxrwx 1 root root    7 10-28 15:18 log-link.log -> log.log
  ```

----

## <a name="touch"></a>touch

英译：（touch）

格式：touch [选项] 文件

touch命令不常用，一般在使用make的时候可能会用到，用来修改文件时间戳，或者新建一个不存在的文件。

- `-c` : --no-create , 不建立任何文档
- `-t` : 使用指定的日期时间，而非现在的时间  [[CC]YY]MMDDhhmm[.SS]  
**举例：**

- 创建一个时间为5月10号12点10分的文件
  ```zsh
  touch -t 05101210 log.log
  ```

----

***未完待续***