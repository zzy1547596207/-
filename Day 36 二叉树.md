# Day 36 二叉树

# 二叉树的右视图

## 题目：

给定一个二叉树的 根节点 root，想象自己站在它的右侧，按照从顶部到底部的顺序，返回从右侧所能看到的节点值。

## 思路：

根据层序遍历，判断当前元素是否为该层级的最后一个元素，如果是的话就存储到res数组中

## 代码：

```javascript
var rightSideView = function(root) {
    let res =[];
    let queue = [];
    queue.push(root)
    while(queue.length && root !== null){
        let length = queue.length;
        while(length--){
            let node = queue.shift();
            if(!length){
                res.push(node.val)
            }
            node.left && queue.push(node.left)
            node.right && queue.push(node.right) 
        }
    }
    return res;
};
```