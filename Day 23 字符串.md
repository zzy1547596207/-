# Day 23 字符串

# 翻转字符串里的单词

## 题目：

给你一个字符串s，请你反转字符串中单词的顺序

单词是由非空格字符组成的字符串。s中使用至少一个空格将字符串中的单词分隔开。

返回单词顺序颠倒且单词之间似乎用单个空格连接的结果字符串

注意：输入字符串s中可能会存在前导空格、尾随空格或者单词建的多个空格。返回的结果字符串中，单词间应当仅用单个空格分隔，且不包含任何额外的空格

## 思路：

最简单的方法就是使用split库函数，分割单词，然后定义一个新的string字符串，最后再把单词倒序相加。

第二种思路：

手动移除多余空格，将字符串反转，将每个单词反转

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1742901213162-9190fd78-9447-4220-b13d-db7e7023e396.png)