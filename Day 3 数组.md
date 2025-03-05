# Day 3 有序数组的平方

题目描述：给定一个按非递减顺序排序的整数数组nums，返回每个数字的平方组成的新数组，并且也按照非递减顺序排序。

## 思路：

### 思路一：

最直接的思路就是暴力排序，首先将数组中的每个数平方之后，再进行排序

![image-20250305183447928](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/image-20250305183447928.png)

### 思路二：

双指针法

因为数组中存在负数，平方之后可能比某些正数大，导致数组变得无序。因此可以采用双指针的方法，head指向数组的头部，foot指向数组的尾部，两个平方之后进行比较，较大的一位元素放置foot的位置，将foot向前移动一位后继续进行比较。

例如：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741172211923-60a2e0b2-048f-4802-95f3-bda2d498ae76.jpeg)

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741173230556-5961cef1-6c20-4798-bda8-742dd4623fde.png)