---
title: while循环嵌套练习题
date: '2019-04-18 08:01:53 +0800'
tags: while
categories: python
---

# 练习3

## 1、求 100-200以内同时能被2、3、5整除的第一个数

```text
start_num = 100
end_num = 200
while start_num < end_num:
    if start_num % 2 == 0 and start_num % 3 == 0 and start_num % 5 == 0:
        print(start_num)
        break
    start_num += 1
```

## 2、打印200以内能被7整除又不包含7的数

```text
end_num = 200
start_num = 1

while start_num <= end_num:
    unit_1 = start_num % 10
    unit_2 = start_num // 10 % 10
    unit_3 = start_num // 100
    if start_num % 7 == 0 and unit_3 != 7 and unit_2 != 7 and unit_1 != 7:
        print(start_num)
    start_num += 1
```

## 3、9\*9乘法表输出

```text
i = 1
xx = ""
while i <= 9:
    j = 1
    while j <= i:
        xx += ("{0:d} * {1:d} = {2:2d} | ".format(i, j, i*j))
        j += 1
    i += 1
    xx += "\n"
print(xx)
```

## 4、求s=a+aa+aaa+aaaa+aa...a的值，其中a是一个数字。 例如2+22+222+2222+22222\(此时共有5个数相加\)，几个数相加有键盘控制。

```text
numa = input("请输入要相加的数字0~9：")
numb = int(input("请输入需要相加几次："))
xx = ""
i = 1
sum_s = 0
while i <= numb:
    numa_a = numa * i
    numa_a = int(numa_a)
    sum_s = sum_s + numa_a
    i += 1
print("最后相加结果为：%d" %sum_s)
```

## 5、一球从100米高度自由落下，每次落地后反跳回原高度的一半；再落下，求它在 第10次落地时，共经过多少米？第10次反弹多高？

```text
total = 1
high_start = 100
high_end = 0
while total <= 10:

    high_end = high_start / (total * 2)
    total += 1
```

## 6、打印如下图形

* \*
* \*

```text
i = 1
while i <= 4:
    if i == 1 or i == 4:
        print(" " * 5 + "*" * 9)
        i += 1
    else:
        print(" " * 5 +"*" + " " * 7 + "*")
        i += 1
```

```text
       *
      ***
     *****
    *******
```

```text
n = 7
mid = n // 2 + 1
i = 1
while n >= i:
    if i <= mid:
        space_num = i -1
    else:
        space_num = n - i
    base_num = abs(mid - i) + 1
    star_num = 2*base_num - 1
    print(" "*space_num + "*" * star_num)

    i += 1
```

```text
n = 5
a = n                          #3
j = 2 * n + 1                  #7
while j > 0:                   #循环7次
    space_num = n - abs(a)     # 初始化
    j -= 1                     #j控制循环
    line_num = abs(2 * a) + 1  #  *  数
    a -= 1                     #  a递减 3 2 1 0 -1 -2 -3
    print(" "* (space_num) + "*" *line_num )
```

```text
     A
    ABA
   ABCBA
  ABCDCBA
```

```text
theStr = input('please input the letter:\n')
theCode = ord(theStr)
i = 65
while i <= theCode:
    for j in range(theCode-i,0,-1):
        print(" ",end='')

    for i_temp in range(65, i):
        print(chr(i_temp), end='')

    for i_temp_temp in range(i, 64, -1):
        print(chr(i_temp_temp), end='')

    i+=1
    print("\n")
```

```text
         1
        121
       12321
      1234321
```

```text
i = 0
higth = 6
while i < higth:
    space_num = higth - i
    k = 1
    j = i - 1
    while k < 2 * i:
        if k <= i:
            num_1 = k
        else:
            num_1 = j
            j -= 1
        k += 1
        print(num_1)
    i += 1
```

```text
    **
    *
```

```text
i = 0
num = 6
while i < 6:
    string = ("*" * num)
    i += 1
    num = num - 1
    print(string)
```

