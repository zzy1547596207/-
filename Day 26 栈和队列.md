# Day 26 栈和队列

## 用栈实现队列

栈常见的操作

push(x) -- 将一个元素放入队列的尾部。
pop() -- 从队列首部移除元素。
peek() -- 返回队列首部的元素。
empty() -- 返回队列是否为空。

## 题目：

请你仅使用两个栈实现先入先出队列。队列应当支持一般队列支持的所有操作（push、pop、peek、empty）：

实现 MyQueue 类：

void push(int x) 将元素 x 推到队列的末尾

int pop() 从队列的开头移除并返回元素

int peek() 返回队列开头的元素

boolean empty() 如果队列为空，返回 true ；否则，返回 false

## 思路：

创建两个栈，一个用来模仿进入队列的操作，一个用来模仿出队列的操作。判断队列是否为空，只需要判断这两个栈是否还有元素存在。

## 代码：

```javascript
var MyQueue = function() {
    this.stackIn= [];
    this.stackOut =[];
};

/** 
 * @param {number} x
 * @return {void}
 */
MyQueue.prototype.push = function(x) {
    this.stackIn.push(x);
};

/**
 * @return {number}
 */
MyQueue.prototype.pop = function() {
    const size = this.stackOut.length;
    if(size){
        return this.stackOut.pop();
    }
    while(this.stackIn.length){
        this.stackOut.push(this.stackIn.pop())
    }
    return this.stackOut.pop()
};

/**
 * @return {number}
 */
MyQueue.prototype.peek = function() {
    const x= this.pop();
    this.stackOut.push(x);
    return x;
};

/**
 * @return {boolean}
 */
MyQueue.prototype.empty = function() {
    return !this.stackIn.length && !this.stackOut.length
};
```