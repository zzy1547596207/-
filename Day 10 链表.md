# Day 10 链表

# 删除链表的倒数第n个节点

## 题目描述：

给你一个链表，删除链表的倒数第n个节点，返回链表的头节点。

## 思路：

这道题可以使用双指针的方法，让fast的指针先走n+1步，当fast的值为null的时候，slow指针此时正是要删除节点的上一个元素，接下来进行对节点的删除。



![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741773159901-46cea5a6-b2be-46c2-95dc-8a70cc5af07c.jpeg)

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741773171257-1d51945e-0787-4c7b-b726-89b5f2ffe144.png)