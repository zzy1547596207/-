# 螺旋矩阵

## 题目描述：

给定一个正整数n，生成一个包含1到n²的所有元素，且元素按照顺时针顺序螺旋排列的n x n正方形矩阵matrix。

## 思路：

模拟顺时针画矩阵的过程：

- 填充上行从左到右
- 填充右列从上到下
- 填充下行从右到左
- 填充左列从下到上

重要的点就是判断边界的条件，和二分法的思路类似，可以采用左闭右开的原则

模拟一圈如下

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741355614377-7710deb4-9d25-4239-811f-637fd8c870e9.jpeg)

代码如下

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741355656300-1b816ef6-18f3-4bd3-9124-c11c5485e12b.png)