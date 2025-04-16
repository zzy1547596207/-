# Day 37 二叉树

# 二叉树的层平均值

## 题目：

给定一个非空二叉树的根节点 root , 以数组的形式返回每一层节点的平均值。与实际答案相差 10-5 以内的答案可以被接受

## 思路：

依据层序遍历的方法，获取每层的元素，累加器sum相加后除以lenth，将结果push到res中

## 代码：

```javascript
var averageOfLevels = function(root) {
    let res = [],queue = [];
    queue.push(root);
    while(queue.length && root !== null){
        let length = queue.length;
        let sum = 0;
        for(let i = 0; i < length; i++){
            let node = queue.shift();
            sum+=node.val;
            node.left && queue.push(node.left);
            node.right && queue.push(node.right)
        }
        res.push(sum/length)
    }
    return res
};
```