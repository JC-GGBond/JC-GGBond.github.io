---
title: Vim_learn
date: 2023-04-25 15:21:35
tags:
categories: software_skills
mathjax: true
---
# vim learn from Learn Vim

## Installation and Tutorial
vim in VS CODE

VIM learn
## move and mode
hjkl 左下上右

“0”移到行首

“^”移到第一个非空行首

“$”移到行尾

“g_”移到第一个非空行尾

“}”跳转段尾(注意是按了ctrl的{不是[)

“{“跳转段首

ctrl+D下一半页

ctrl+U上一半页

gg移到文首

G移到文末

多少行+gg移到该行

3个模式mode:

    默认的Normol mode，方框形状

    按i 进入Insert mode竖杠形状

    visual mode

    ESC返回到Normal mode

## motions
w跳到下一个word的首字母处

b跳到上一个word的尾字母处

W跳到下一个Word的首字母处，Word指一串字母标点数字序列

B跳到上一个Word的尾字母处

e跳到下一个word的尾字母处

ge(先按g再e)是跳到前一个word的尾字母

gE(先按g再E)是跳到前一个Word的尾字母



## Search
tips:写的上和下其实是继续或者反向当前搜索逻辑，比如当前向下搜索那么继续或者相反；

f+XXX是寻找本行中下一个XXX

F+XXX是寻找本行中上一个XXX

t+XXX是寻找本行中下一个XXX的前一个字母

T+XXX是寻找本行中前一个XXX的下一个字母

用完f后可以使用”;”寻找下一个XXX，使用”,”寻找前一个XXX

用完t后也可以使用”;”和”,”，”;”是继续寻找下一个XXX的前一个字母，而”,”是寻找上一个XXX的后一个字母。（不好用- -）

/+XXX+enter 向下全文搜索,甚至可以搜索标题比如/##搜索下一个二级标题

？+XXX+enter 向上全文搜索

n 下一个匹配项

N 前一个匹配项

%跳转到左括号对应的右括号或反之

先打一个数字X然后输入操作就是找第X个

## Operator
在normal mode下

operator count motion:比如d2w就是删除后面两个word

dw删去这个word

u撤销当前操作

ctrl+R恢复之前的操作

df'从光标处删除直到第一个'（删除'）

dt'从光标处删除直到第一个'(不删除')

d/XXX从光标处删除所有的直到第一个XXX

ggdG删除全文

dd删除整行

D删除光标至行末的所有内容

