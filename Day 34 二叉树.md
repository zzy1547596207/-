# Day 34 二叉树

# 二叉树的迭代遍历

## 前序遍历

```javascript
var preorderTraversal = function(root) {
    const result = [];
    if (!root) return result;
    const stack = [root];
    while (stack.length) {
        const node = stack.pop();
        result.push(node.val);
        if (node.right) stack.push(node.right);
        if (node.left) stack.push(node.left);
    }
    
    return result;
};
```

## 中序遍历

```javascript
var inorderTraversal = function(root) {
    const stack = [];
    let cur = root;
    while(stack.length || cur) {
        if(cur) {
            stack.push(cur);
            cur = cur.left;
        } else {
            cur = stack.pop();
            res.push(cur.val); 
            cur = cur.right;
        }
    };
    return res;
};
```

## 后序遍历

```javascript
var postorderTraversal = function(root) {
    if (!root) return res;
    const stack = [root];
    let cur = null;
    do {
        cur = stack.pop();
        res.push(cur.val);
        cur.left && stack.push(cur.left);
        cur.right && stack.push(cur.right);
    } while(stack.length);
    return res.reverse();
};
```