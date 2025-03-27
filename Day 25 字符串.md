# Day 25 字符串

# 实现strStr()

## 题目描述：

给定两个字符串haystack和needle，请你在haystack字符串中找出needle字符串的第一个匹配项的下标志（下标从0开始）。如果needle不是haystack的一部分，则返回-1

## 思路：

1. 暴力for循环来解决，通过两层for循环判断子串是否在字符串中重复出现
2. kmp算法

- - 通过前缀表来判断是否子串在字符串中出现过

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1743038432895-51ef67b9-1c06-478b-85b4-e2bad77586a3.png)