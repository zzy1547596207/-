# Day 14 哈希表

# 两个数组的交集

## 题目描述：

给定两个数组，编写一个函数来计算它们的交集。

## 思路：

本道题可以使用数组来做哈希表，但是由于题目没有规定元素的大小范围，可能哈希值比较少，特别分散，跨度比较大，使用数组就会造成空间的浪费。

此时就可以用到另一个结构体：set

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1742136860690-7c430c3c-a25c-45cb-bbf2-3522c680404d.png)