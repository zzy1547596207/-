# 长度最小的子数组

## 题目描述：

给定一个含有n个正整数的数组，和一个正整数target。找出该数组中满足其总和大于等于target的长度最小的子数组。返回其长度，如果不存在返回-1

## 思路：

### 思路一：

可以采用双层for循环的办法来暴力破解。

但力扣好像已经不支持使用该方法。

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741254132714-913412e8-17d9-4bc0-841f-40e58df6d35f.png)

### 思路二：

滑动窗口：

思路上是通过双指针的方法，判断两个指针之间的元素之和是否大于等于target，如果大于target，让start向后移动一位，如果小于则让end向后移动一位。



![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741256259115-e6e2d7bf-b0ed-4e6c-8b7a-0b0818206eb6.jpeg)



![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741255114367-4d0c2ce3-5be5-4d95-a19c-f1c2acab2c9c.png)