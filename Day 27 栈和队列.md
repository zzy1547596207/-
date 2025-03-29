# Day 27 栈和队列

# 用队列实现栈

## 题目：

使用队列实现栈的下列操作：

- push(x) -- 元素 x 入栈
- pop() -- 移除栈顶元素
- top() -- 获取栈顶元素
- empty() -- 返回栈是否为空

## 思路：

1.根据用栈实现队列，那么我们也可以用两个队列实现栈。用数组来模拟队列

```javascript
var MyStack = function() {
    this.queue1 = [];
    this.queue2 = [];
};

/** 
 * @param {number} x
 * @return {void}
 */
MyStack.prototype.push = function(x) {
    this.queue1.push(x);
};

/**
 * @return {number}
 */
MyStack.prototype.pop = function() {
    if(!this.queue1.length){
        [this.queue1,this.queue2] = [this.queue2,this.queue1]
    }
    while(this.queue1.length > 1){
        this.queue2.push(this.queue1.shift())
    }
    return this.queue1.shift()
};

/**
 * @return {number}
 */
MyStack.prototype.top = function() {
    const x = this.pop();
    this.queue1.push(x);
    return x
};

/**
 * @return {boolean}
 */
MyStack.prototype.empty = function() {
    return !this.queue1.length && !this.queue2.length;
};
```

2.用一个队列实现栈。

```javascript
var MyStack = function() {
    this.queue1 = [];
};

/** 
 * @param {number} x
 * @return {void}
 */
MyStack.prototype.push = function(x) {
    this.queue1.push(x);
};

/**
 * @return {number}
 */
MyStack.prototype.pop = function() {
    let size = this.queue1.length;
    while(size-- >1){
        this.queue1.push(this.queue1.shift())
    }
    return this.queue1.shift();
};

/**
 * @return {number}
 */
MyStack.prototype.top = function() {
    const x = this.pop()
    this.queue1.push(x);
    return x;

};

/**
 * @return {boolean}
 */
MyStack.prototype.empty = function() {
    return !this.queue1.length
};
```

