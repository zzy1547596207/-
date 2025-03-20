# Day 18 哈希表

# 赎金信

## 题目描述：

给你两个字符串：ransomNode和magazine，判断ransomNode能否由magazine中的字符构成，magazine中的字符每个只能用一次

## 思路：

1.可以使用双层for循环暴力解决，挨个遍历不断去寻找

2.可以使用哈希表来解决，但使用map的空间消耗比数组大，所以采用数组在哈希法里的应用

## 代码：

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1742453523013-3704c4cb-3f10-4442-9a4a-be08aecceb41.png)