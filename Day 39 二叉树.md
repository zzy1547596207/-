# Day 39 二叉树

# 在每个树行中找最大值

## 题目：

给定一棵二叉树的根节点 root ，请找出该二叉树中每一层的最大值。

## 思路：

先使用层序遍历，将每一层的值保存在数组中，设每层的第一个值是他的最大值，如果出现比他大的值的话，就将这个值赋值给max。

## 代码

```javascript
var largestValues = function(root) {
    let res = [],queue = [];
    queue.push(root);
    while(root!= null && queue.length){
        let max = queue[0].val;
        let length = queue.length;
        while(length--){
            let node = queue.shift();
            max = max > node.val ? max : node.val;
            node.left && queue.push(node.left);
            node.right && queue.push(node.right)  
        }
        res.push(max)
    }
    return res
};
```