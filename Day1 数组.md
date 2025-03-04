## 力扣704.二分查找

### 使用前提：

1. 数组是有序排列的（升序或者倒序）
2. 数组中没有重复元素

有重复元素可能导致返回的元素下标不唯一。

### 思路：

根据对不同区间的选择，会产生两种二分查找的写法。

1. 区间的定义为左闭右闭区间

即target在 [ left，right ]，该写法的注意点有两个：

（1） while循环中的结束判断条件为（left <= right），因为此时left == right 是有意义的

（2）if（nums[middle] > target）时，right要赋值为middle - 1，因为此时nums [ middle ]不为target，且区间为[left，right]，接下来要查找区间的结束位置为middle-1  。

例如在以下数组中查找target为2的索引

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741009259308-65ab2688-ec08-418a-b7d1-f3997f90e37f.jpeg)

<details class="lake-collapse"><summary id="ue122afab"><span class="ne-text">实现方法一</span></summary><p id="ue0f37ac7" class="ne-p" style="margin: 0; padding: 0; min-height: 24px"><img src="https://cdn.nlark.com/yuque/0/2025/png/43020085/1741010722907-3df8db62-98a0-4e34-8eab-f1aa59e702c7.png" width="496.6666666666667" title="" crop="0,0,1,1" id="u13323dc4" class="ne-image"></p></details>

1. 区间的定义为左闭右开区间

即target在[left，right ），该写法的注意点也有两个：

（1）while循环中的结束判断条件为（left < right），因为在[left，right）left == right 是无意义的

（2）if（nums[middle] >  target）时，right要赋值为middle，因为此时nums[ middle ]不为target，且此时寻找的区间为左闭右开区间，更新为middle，那么查询区间就不会比较nums[ middle ]。

例如在以下数组中查找target为2的索引

![img](https://ziyuantypora.oss-cn-beijing.aliyuncs.com/1741009667695-737e8e11-abb3-404a-a6eb-bf30abbe0407.jpeg)

<details class="lake-collapse"><summary id="uab85016a"><span class="ne-text">实现方法二</span></summary><p id="u4059b7e6" class="ne-p" style="margin: 0; padding: 0; min-height: 24px"><img src="https://cdn.nlark.com/yuque/0/2025/png/43020085/1741010663810-ede6f54f-4a04-4605-aadf-a915bfdc43c9.png" width="480" title="" crop="0,0,1,1" id="ud5be43b0" class="ne-image"></p></details>



