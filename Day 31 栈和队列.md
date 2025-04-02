# Day 31 栈和队列

# 滑动窗口最大值

## 题目：

给定一个数组 nums，有一个大小为 k 的滑动窗口从数组的最左侧移动到数组的最右侧。你只可以看到在滑动窗口内的 k 个数字。滑动窗口每次只向右移动一位。

返回滑动窗口中的最大值。

## 思路：

1.可以用双指针显示窗口，用for循环来挨个遍历找出最大值，时间复杂度为O（n*k）

2.使用队列来表示，每次移动窗口时，就让队列一进一出。并且构建单调队列，只保存三个数中的最大数。

## 代码：

```javascript
var maxSlidingWindow = function(nums, k) {
    class MonoQueue{
        queue;
        constructor(){
            this.queue = [];
        }
        enqueue(value){
            let back = this.queue[this.queue.length - 1];
            while(back !== undefined && back < value){
                this.queue.pop();
                back = this.queue[this.queue.length - 1];
            }
            this.queue.push(value);
        }
        dequeue(value){
            let front = this.front();
            if(front === value){
                this.queue.shift()
            }
        }
        front(){
            return this.queue[0];
        }
    }
    let helperQueue = new MonoQueue();
    let i = 0, j = 0;
    let resArr = [];
    while(j < k){
        helperQueue.enqueue(nums[j++])
    }
    resArr.push(helperQueue.front());
    while(j < nums.length){
        helperQueue.enqueue(nums[j]);
        helperQueue.dequeue(nums[i]);
        resArr.push(helperQueue.front());
        i++,j++
    }
    return resArr
};
```