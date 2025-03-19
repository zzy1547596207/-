# Day 17 哈希表

# 四数相加II

## 题目描述：

给你四个整数数组nums1、nums2、nums3、nums4，数组的长度都是n，请计算有多少个元素【i ， j ，k ，l】能满足。

nums1[i]+nums2[j]+nums3[k]+nums4[l]==0

## 思路：

1.直接用暴力for循环的方法搜索，但时间复杂度是O(n4)。

2.可以将四个数组分成两组，利用哈希表用count把map中key对应的value也就是出现次数统计出来。

## 代码:

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1742372589972-9df94659-4936-484a-a33a-9a0ea49f2656.png)