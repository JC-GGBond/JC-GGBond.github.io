---
title: Interview_RF_prepare
date: 2022-09-19 21:22:52
tags:
categories: careering
---
# RF面试准备
## RF基础问题准备
可能会出一个大题，
射频问题，
看同门提供问题集，
有没有可能好死不死让写一个代码呢？
```
给定一个非空字符串 s，请判断如果 最多 从字符串中删除一个字符能否得到一个回文字符串。
class Solution {
    //人家写的这代码思想真不错
public:
    bool checkPalindrome(const string& s, int low, int high) {
        for (int i = low, j = high; i < j; ++i, --j) {
            if (s[i] != s[j]) {
                return false;
            }
        }
        return true;
    }

    bool validPalindrome(string s) {
        int low = 0, high = s.size() - 1;
        while (low < high) {
            char c1 = s[low], c2 = s[high];
            if (c1 == c2) {
                ++low;
                --high;
            } else {
                return checkPalindrome(s, low, high - 1) || checkPalindrome(s, low + 1, high);
            }
        }
        return true;
    }
};
```

## 个人介绍流程
* 简历展示
* 毕业研究方向说明：
  * 介绍比赛报告内容，复习DPD架构，前逆后逆,**daily20220304,20220610**
  * 介绍进度情况，曹中华师兄功放，延续性介绍，done

Pre:
* 完成功放设计简略ADS流程
* 曹师兄论文：
  * 宽带匹配技术

连续类功放？

  * 复阻抗匹配技术
复阻抗变换器

* 乐哥给的PPT



* 项目
  * 本科脑电近红外一句话
  * 毕设提一句
  * 选通开关
    * 无源介绍wilkinson divider，复习原理，done
    * 有源介绍设计想法，频率检测，那个管子可能像PLL，复习下PLL

Pre:
* wilkinson功分

在非互易网络下可实现全部端口输入输出匹配无耗。环形器

有耗互易，阻性功分

弯折由于微带线长宽不变，离得远3倍？微带线宽避免近场耦合？

涉及奇偶模分析，略

* 选通开关有源

* linear LTC5507,修改$C_1,C_2$
* TYPE-C供电
* 电压判决LM393


* 实习
  
  介绍PPT

* 文章
  
确实主要工作不是我，介绍个人工作，revision问题
  
