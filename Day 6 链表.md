# 链表的删除

## 题目描述：

给定一个链表的头节点，和一个整数val，删除链表中所有满足Node.val=val的节点，并返回头节点

## 思路：

首先对head节点进行判断，如果head节点的值等于val，那就将head节点指向下一个节点，即head = head.next。直到找到头节点不为val且不为空的那一个节点，这是对头节点的处理。

接着来就是对非头节点的处理，判断该节点的下一个元素的值是不是等于val，如果等于就跳过这个节点，让该节点的上一个节点直接指向该节点的下一个节点

## 代码实现：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741438337400-e7f21928-9191-4538-b32d-29e365b2ad18.png)



![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741439029552-31a44958-6aed-4a35-b806-10f0ba0c1481.jpeg)



虚拟头节点的使用：

好处：不用区分头节点的判断和非头节点的判断情况。



代码如下：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741439404982-ea9ec62f-b17d-410e-8435-ab0322827f4b.png)