---
title: Cmakeandmake-1
date: 2022-01-27 00:31:44
tags: C++
categories: coding
---
# Cmake & make


Cmake:用于多平台编译程序

## 1.Workflow

1. 编写main.c

   ```c
   #include <stdio.h>
   
   int main(void)
   {
   	printf("Hello World\n");
   
   	return 0;
   }
   
   ```

2. 在main.c同目录下编写CmakeList.txt

   单行注释：使用“#”
   多行注释：使用“#[[ ]]”

   ```
   # cmake最低版本2.8
   cmake_minimum_required (VERSION 2.8)
   # 本工程信息，工程名demo
   project (demo)
   # 最终生成的 可执行文件的名字叫main
   add_executable(main main.c)
   ```

3. 运行cmake . 生成Makefile和其他自动生成的文件

4. 运行 make 生成可执行文件

5. ./main 执行命令

## 2.Tips

```
cmake -DCMAKE_INSTALL_PREFIX=/usr ..
```

