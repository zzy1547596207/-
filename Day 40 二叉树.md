# Day 40 二叉树

# 填充每个节点的下一个右侧节点指针II

## 题目：

填充它的每个 next 指针，让这个指针指向其下一个右侧节点。如果找不到下一个右侧节点，则将 next 指针设置为 Null。

初始状态下，所有 next 指针都被设置为 Null 。

## 代码：

```javascript
var connect = function(root) {
    if (root === null) {
        return null;
    }
    let queue = [root];
    while (queue.length > 0) {
        let n = queue.length;
        for (let i=0; i<n; i++) {
            let node = queue.shift();
            if (i < n-1) node.next = queue[0];
            if (node.left != null) queue.push(node.left);
            if (node.right != null) queue.push(node.right);
        }
    }
    return root;
};
```