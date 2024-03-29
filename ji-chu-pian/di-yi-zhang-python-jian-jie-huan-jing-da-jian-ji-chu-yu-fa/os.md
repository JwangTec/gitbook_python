---
title: python os/shtuil
date: '2019-04-26 22:01:53 +0800'
tags: os/shtuil
categories: python
---

# 2. os

## 1.os/shtuil模块常用命令

```text
os模块
path函数os模块中的abspath:找出当前运行函数的绝对路径
os.mkdir:不能递归创建目录
os.path.join:相当于"+/"，如果是windos则是"\+"
os.makedirs: 可递归创建文件
os.path.abspath:显示同层文件的绝对路径
os.path.dirname:显示同层文件上层目录
os.rmdir:删除空文件
shutil模块
shutil rmtree:强制删除文件
shutil move:移动文件
shutil copy:
shutil copytree:
```

## 2.文件路径的查找

```text
import os
import shutil #更高级一点的库

 def get_path():
     xx = os.path.abspath(__file__)  #__file__相当于当前所在文件名
     return xx
```

```text
一直找上层路径直到项目路径
 c_path = os.path.abspath(__file__)
 module_path = os.path.dirname(c_path)
 pycode_path = os.path.dirname(module_path)
 print(os.path.dirname(pycode_path))

相当于下面代码
 BASE_DIR = os.path.dirname(os.path.dirname(__file__))
 print(BASE_DIR)
 os.mkdir(BASE_DIR+'/b_test')
```

## 3.创建或删除文件/文件夹

```text
 xx = os.path.join(BASE_DIR,'text1','text2') #在BASE_DIR的路径下创建text1并在该文件下再创建text2
 os.mkdir(xx)   #不能递归创建
 os.makedirs(xx) #可递归创建文件
 os.makedirs(xx,exist_ok=True)  #若有该文件名存在则不会再报错

 os.rmdir(os.path.join(BASE_DIR,'b_test'))  #只能删除空目录

shutil.rmtree(os.path.join(BASE_DIR,'text1')) #使用shutil库函数删除文件夹(包括非空文件夹)
```

## 4.文件/文件夹的移动，以及文件夹遍历

```text
将位于BASE_PATH路径下的a_text移动到b_text下

 os.mkdir(os.path.join(BASE_DIR,'a_text'))
 os.mkdir(os.path.join(BASE_DIR,'b_text'))
 shutil.move(os.path.join(BASE_DIR,'a_text'),os.path.join(BASE_DIR,'b_text'))  

拷贝文件到一个新文件中  操作的是文件
 shutil.copy('test1.py','test4.py') 
拷贝文件夹到新文件夹中，操作的是文件夹       
 shutil.copytree(os.path.join(BASE_DIR,'module'),os.path.join(BASE_DIR,'module2')) 

遍历文件夹
 yy = os.listdir(BASE_DIR+'/module')  
 print(yy)
```

## 5.遍历文件夹

```text
import os
import shutil

#深度遍历文件夹
def deep_first(dir):  
    dir_lists = os.listdir(dir)
    if len(dir_lists) == 0:
        return
    for d in dir_lists:
        print(d)
        deep_first(os.path.join(dir,d))
deep_first('test')

#广度遍历文件夹
def brand_first(dir):   
    buckets = []
    buckets.append(dir)

    while len(buckets) > 0:
        tmp = buckets.pop(0)
        print(tmp)
        files = os.listdir(tmp)    #listdir中容易乱序，需要排序
        files.sort()
        for i in files:
            buckets.append(os.path.join(tmp,i))

brand_first('test')
```

