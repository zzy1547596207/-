# Day 24 字符串

# 重复的子字符串

## 题目描述：

给定一个非空的字符串，判断它是否可以由它的一个子串重复多次构成。给定的字符串只含有小写英文字母，并且长度不超过10000

## 思路

1. 通过两层for循环判断子串是否在字符串中重复出现
2. 移动匹配法

- - 设原先字符串尾s，那么将s+s进行拼接，并且去掉头和尾的第一个元素，判断s是否在新的字符串中出现，如果出现那么就可以判断是否由重复子字符串构成
  - ![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1742987197538-592faae5-9cb1-4727-a106-090e91e2bae4.png)

1. kmp算法

- - 首先构建字符串的前缀表next。
  - 然后根据next判断是否是有重复子字符串构成