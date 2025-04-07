# Day 33 二叉树

# 二叉树的三种遍历

前中后序的三种遍历，用递归的方式实现。

## 前序遍历

```javascript
var preorderTraversal = function(root) {
    let res = [];
    const dfs = function(root){
        if(root === null) return;
        res.push(root.val)
        dfs(root.left);
        dfs(root.right)
    }
    dfs(root)
    return res
};
```

## 中序遍历

```javascript
var inorderTraversal = function(root) {
    let res = []
    let dfs = function(root){
        if(root === null) return 
        dfs(root.left);
        res.push(root.val)
        dfs(root.right)
    } 
    dfs(root);
    return res;
};
```

## 后序遍历

```javascript
var postorderTraversal = function(root) {
    let res = [];
    let dfs = function(root){
        if(root === null) return ;
        dfs(root.left);
        dfs(root.right);
        res.push(root.val)
    }
    dfs(root);
    return res
};
```