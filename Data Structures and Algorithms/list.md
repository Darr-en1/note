# list(表) 
### 表的抽象数据类型（基本组成部分）：  数组      链表（单向链表，双向链表）

## 数组：
特点：数据是连续的；随机访问速度快。<br>
数组实现：对于Java而言，Collection集合中提供了ArrayList和Vector。<br>

## 链表
最左边的节点为头结点（head）

### 单向链表
单向链表(单链表)是链表的一种，它由节点组成，每个节点都包含下一个节点的指针。<br>
单链表的特点是：节点的链接方向是单向的；相对于数组来说，单链表的的随机访问速度较慢，但是单链表删除/添加数据的效率很高。<br>
<br>
```java
public class SingleLinkedListNode {
    int val;
    SingleLinkedListNode next;
    SingleLinkedListNode(int x) { val = x; }
}
```
缺陷：在最后的位置删除一个节点 倒数第二个节点需要将其next链设为null.在最后的位置添加一个节点 该节点需要将其next链设为null.<br>

### 双向链表
双向链表(双链表)是链表的一种。和单链表一样，双链表也是由节点组成，它的每个数据结点中都有两个指针，分别指向直接后继和直接前驱。所以，从双向链表中的任意一个结点开始，都可以很方便地访问它的前驱结点和后继结点。<br>
注：head的前驱指向最后一个结点

##### ArrayList类提供了可增长数组的实现（两倍增长）<br>
##### LinkedList类提供了双向链表的实现

### 针对遍历迭代的讨论
```java
for (String string : list) {
	if(string=="lis")list.remove(string);   //这个删除需要找到对应索引，效率不高  O(N²)
}

while(itr.hasNext()){
	itr.next();
	if(itr.next()=="lis")itr.remove();     //得到位置直接删除（迭代器）   O(N)
}
```

### 如何判断单链表是否存在环
**方法一、穷举遍历**<br>
**方法二、哈希表缓存**<br>
**方法三、快慢指针**<br>



