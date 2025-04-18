# Day 38 二叉树

# N叉树的层序遍历

## 题目：

给定一个 N 叉树，返回其节点值的层序遍历。（即从左到右，逐层遍历）

树的序列化输入是用层序遍历，每组子节点都由 null 值分隔（参见示例）

## 思路：

与二叉树的层序遍历不同的是，对子节点的处理方式，因为是N叉树，所以不能用node.lfet和node.right而是要利用for循环挨个遍历node的孩子

## 代码：

```javascript
var levelOrder = function(root) {
    let res = [],queue = [];
    queue.push(root);
    while(queue.length && root !== null){
        let length = queue.length;
        let curLevel = [];
        while(length--){
            let node = queue.shift();
            curLevel.push(node.val);
            for(let item of node.children){
                item&&queue.push(item);
            }
        }
        res.push(curLevel);
    }
    return res;
};
```