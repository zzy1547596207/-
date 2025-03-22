# Day 20 哈希表

# 四数字之和

## 题目描述

给你一个由n哥整数组成的数组nums，和一个目标值target。请你找出并返回满足下述全部条件且不重复的四元组`[nums[a], nums[b], nums[c], nums[d]]` （若两个四元组元素一一对应，则认为两个四元组重复）

- 0 <= a, b, c, d < n
- a、b、c 和 d 互不相同
- nums[a] + nums[b] + nums[c] + nums[d] == target

## 思路：

1.哈希解法

- - 三层层for循环可以确定两个值，可以使用哈希表来确定第四个数 0 -（a+ b +c）是否在数组中出现过。但是题目中说不可以包含重复的四元组。把符合条件的四元组放进vector中，然后再去重十分费时间

2.双指针解法

先通过双层for循环确定两个值，再用双指针来寻找符合条件的元组。

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1742655801806-09957132-094d-4a48-aded-bbe94bd9e69d.png)