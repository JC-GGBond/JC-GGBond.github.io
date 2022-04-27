---
title: Cpp_tips
date: 2022-04-02 13:57:18
tags:
categories: coding
---
# C++ tips

## 函数命令
* 模板类：容器、迭代器、函数对象、算法
* string模板类使用
  
    获取长度,类方法

    使用string模板类，#include <cstring>

    str.length()

    str.size()
    
    strlen(s1)

    sizeof是判断字节大小

    strlen是获取字符串数组的，且要导入cstring模板类

* 数组求和
    
    模板类库函数

    ```
    #include <numeric>
    int sum=accumulate(起始，结尾，初值)
    ```
* 不能直接int a[]可变数组或者char a[]没有等于XXXX，用模板类vector
    ```
    vector<int> xxxx(长度，可为空)
    ```
    可以直接char XXX[]=XXXXX称为字符串常量

* 字符串某位数-'0'得到原数：因为ASCII字符中的数字（‘123456’）想转换为纯数字（1,2,3,4...）就要减去48（ASCII单位），而‘0’的ASCII单位正好等于48。
* 变量存储范围：
  ![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/C++/变量存储范围.20cvqdqyaglc.webp)

* STL容器unordered_map
  
  底层使用哈希表，在std命名空间中，要#include <unordered_map>

* C++位操作
  
  CSDN老鼠死问题有点意思，按二进制换转置

  |按位取或
* swap函数，sort函数
* 删除vector中重复的其他元素，只保留一个：
```
        sort(sum.begin(),sum.end());
        vector<vector<int>>::iterator pos=unique(sum.begin(),sum.end());
        sum.erase(pos,sum.end());
```