# Day 11 链表

# 链表相交

## 题目描述：

给你两个单链表的头节点headA和headB，请你找出并返回两个单链表相交的起始节点，如果两个链表没有交点返回null。

## 思路：

如果两链表相交，那么他们当中一定存在某一个链表元素的地址相等。那么可以先判断两个链表的长度，让长的那个链表先走count步（count = 长链表的长度 - 短链表的长度），直到和短链表的长度相等。用双指针的办法对两个链表的元素挨个进行比较，看他们元素的地址是否相等。



![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741850257597-88f2c4f2-16b6-4464-8178-18831f91b3a1.jpeg)

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741849981668-81fcc476-9ba2-4719-854d-9896c6eac3a2.png)****

