# Day 7 链表

# 设计链表 

## 题目描述：

使用单链表或者双链表，来设计并实现自己的链表。

单链表需要具备两个属性：val和next。val是当前节点的值，next是指向下一个节点的指针/引用。

如果是双向链表，则还需要prev指向上一个节点，链表中所有节点下标从0开始



## 代码实现：

```javascript
class LinkNode {
    constructor(val, next) {
        this.val = val;
        this.next = next;
    }
}

var MyLinkedList = function() {
    this._size = 0;
    this._tail = null;
    this._head = null;
};

/** 
 * @param {number} index
 * @return {number}
 */
 MyLinkedList.prototype.getNode = function(index) {
    if(index < 0 || index >= this._size) return null;
    let cur = new LinkNode(0, this._head);
    while(index-- >= 0) {
        cur = cur.next;
    }
    return cur;
};

MyLinkedList.prototype.get = function(index) {
    if(index < 0 || index >= this._size) return -1;
    return this.getNode(index).val;
};

/** 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtHead = function(val) {
    const node = new LinkNode(val, this._head);
    this._head = node;
    this._size++;
    if(!this._tail){
        this._tail = node;
    }
};

/** 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtTail = function(val) {
    const node = new LinkNode(val, null);
    this._size++;
    if(this._tail) {
        this._tail.next = node;
        this._tail = node;
        return;
    }
    this._tail = node;
    this._head = node;
};

/** 
 * @param {number} index 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtIndex = function(index, val) {
    if(index > this._size) return;
    if(index <= 0) {
        this.addAtHead(val);
        return;
    }
    if(index === this._size) {
        this.addAtTail(val);
        return;
    }
    const node = this.getNode(index - 1);
    node.next = new LinkNode(val, node.next);
    this._size++;
};

/** 
 * @param {number} index
 * @return {void}
 */
MyLinkedList.prototype.deleteAtIndex = function(index) {
    if(index < 0 || index >= this._size) return;
    if(index === 0) {
        this._head = this._head.next;
        if(index === this._size - 1){
            this._tail = this._head
        }
        this._size--;
        return;
    }
    const node = this.getNode(index - 1);    
    node.next = node.next.next;
    if(index === this._size - 1) {
        this._tail = node;
    }
    this._size--;
};
```

对链表的实现主要包括，链表自身的定义和链表节点的定义，以及其方法的实现。

在上述代码中主要实现的方法有：

- get方法：获取到第index个节点的数值
- getNode方法：获取到第index个节点
- addAtHead：在头节点的位置插入元素
- addAtTail：在尾节点的位置插入元素
- addAtIndex：在第index个节点的位置插入元素
- deleteAtIndex：删除第index个节点的元素

本题实现要注意的细节，判断原列表是否为空，在插入或者删除元素时候，判断是否为头，尾节点。