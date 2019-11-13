---
title: 'py_practice_[进制转换，类型，运算符]'
date: '2019-04-15T20:28:36.000Z'
tags: 基础
categories: python
---

# 练习1

## 基础输出练习

```text
import keyword
import math
import os
print("hello world!")   #   使用CPU进行标准输出到屏幕

print(type('world'))
```

```text
print(1)
print(2+3)
print(1.0)
print(2.5+2.5)
print    ('hello')
print('hello' + 'world')
print('hello' + "world")
print(1+2.0)
print(type(1))
print(type(1.0))
```

二进制输出

```text
print(bin(12345))

print(0b11000000111001)
```

占位符输出

```text
aa =12344
bb = 12345.0
print("%5d, %.1f" %(aa, bb))
cc ="asdf"
print("%d, %e" %(aa, aa))
```

十六进制转换函数

```text
aa = int(input("请输入一个十进制整数num："))
def XD_exchange(num):
    print("%d 的 十六进制是 %x " %(num, num))
    print("%d 的 十六进制是 %x " %(num, num)) 

XD_exchange(aa)
```

## 输入练习

```text
aa = int(input("请输入一个十进制数整数num："))
print("%d 的 十六进制是 %x " %(aa, aa))
aa = int(input("请输入一个十进制数整数num："))
print("{0} 的 十六进制是 {1} ".format(aa, aa))
```

## 变量

```text
def X_exchange(aa):
    print("%d 的 十六进制是 %x " %(aa, aa))
def E_exchange(bb):
    print("%d 的 科学计数法是 %e " %(bb, bb))
def B_exchange(cc):
    print("{0} 的 二进制是 {1}".format(cc, bin(cc)))
num = input("请确认需要输入的整数：")
if  num.isdigit():
     num1 = int(num)
     X_exchange(num1)
     E_exchange(num1)
     B_exchange(num1)
else:
    num2 = len(num)
    print("{0} 是一个字符串，其占用字节数为{1}".format(num,num2))

name = "超级咸蛋超人"

kill = 99999999.55555555555

print("%s 一拳伤害 %d, 精确到小数点后9位为：%.9f"%(name, kill,kill))
```

## format

```text
    aa = 100
    bb = 100.01
    print("{0:%d},{1:%.2f},{2}".format(aa, bb, aa)
```

## 运算符

1. 运算符： + - \* / %
2. 向下取整： // 
3. 向上取整 ： 调用函数math， math.ceil\(\)
4. 取模：%
5. 幂运算：   **2**3 = 2^3
6. 比较符：&gt; &lt;  &gt;=  &lt;= != == \(判断的是对象的值\)  python可以使用连续判断
7. 布尔代数：二进制位运算：\| &gt;&gt; &lt;&lt; & ^ 
8. not 0 = true  not 4 = false  除0全是true  字符串空也为false 非空为true             注意：False 首字母大写
9. 逻辑运算符：and  in  or not is\(对象是否相同：地址等\)
10. 惰性原则：print\(\(1 &lt; 2\) or \(x &gt; 6\)\)  true
11. python优化机制

