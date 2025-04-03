# Day 32 栈和队列

给定一个非空的整数数组，返回其中出现频率前 k 高的元素。

## 思路：

这道题目主要设计以下三个方面

- 要统计元素出现的频率
- 对频率进行排序
- 找出前k个高频元素

首先对于元素出现的频率，这一个问题我们可以使用map来进行统计。

## 代码

```javascript
class Heap {
    constructor(compareFn) {
        this.compareFn = compareFn;
        this.queue = [];
    }

    push(item) {
        this.queue.push(item);
        let index = this.size() - 1; 
        let parent = Math.floor((index - 1) / 2); 

        while (parent >= 0 && this.compare(parent, index) > 0) {
            [this.queue[index], this.queue[parent]] = [this.queue[parent], this.queue[index]];
            index = parent;
            parent = Math.floor((index - 1) / 2);
        }
    }
    pop() {
        if (this.size() <= 1) {
            return this.queue.pop()
        }
        const out = this.queue[0];
        this.queue[0] = this.queue.pop();
        let index = 0; 
        let left = 1; 
        let searchChild = this.compare(left, left + 1) > 0 ? left + 1 : left;

        while (this.compare(index, searchChild) > 0) { 
            [this.queue[index], this.queue[searchChild]] = [this.queue[searchChild], this.queue[index]];
            index = searchChild;
            left = 2 * index + 1;
            searchChild = this.compare(left, left + 1) > 0 ? left + 1 : left;
        }

        return out;
    }
    size() {
        return this.queue.length;
    }
    compare(index1, index2) {
        if (this.queue[index1] === undefined) return 1;
        if (this.queue[index2] === undefined) return -1;

        return this.compareFn(this.queue[index1], this.queue[index2]);
    }

}

const topKFrequent = function (nums, k) {
    const map = new Map();

    for (const num of nums) {
        map.set(num, (map.get(num) || 0) + 1);
    }
    const heap= new Heap((a, b) => a[1] - b[1]);
    for (const entry of map.entries()) {
        heap.push(entry);

        if (heap.size() > k) {
            heap.pop();
        }
    }
    const res = [];

    for (let i = heap.size() - 1; i >= 0; i--) {
        res[i] = heap.pop()[0];
    }

    return res;
};
```