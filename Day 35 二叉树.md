# Day 35 二叉树

# 二叉树的层序遍历

## 题目：

给你二叉树的根节点 root ，返回其节点值 自底向上的层序遍历 。 （即按从叶子节点所在层到根节点所在的层，逐层从左向右遍历）

## 思路：

可以用队列来记录节点，利用先进先出的特点，每弹出一个元素的时候，就将子节点加入到队列中

## 代码：

```javascript
var levelOrderBottom = function(root) {
    let res = [];
    let queue = [];
    queue.push(root);
    while(queue.length && root != null){
        let curLevel = [];
        let length = queue.length;
        while(length--){
            let node = queue.shift();
            curLevel.push(node.val);
            node.left && queue.push(node.left);
            node.right && queue.push(node.right)
        }
        res.unshift(curLevel)
    }
    return res;
};
```



## 题目

给你二叉树的根节点 root ，返回其节点值的 层序遍历 。 （即逐层地，从左到右访问所有节点）。

## 代码：

```javascript
var levelOrder = function(root) {
    let res = [];
    let queue = [];
    queue.push(root)
    while(queue.length && root !== null){
        let currLevel = []
        let length = queue.length
        while(length--){
            let node = queue.shift()
            currLevel.push(node.val)
            node.left && queue.push(node.left);
            node.right && queue.push(node.right)
        }
        res.push(currLevel)
        
    }
    return res
};
```