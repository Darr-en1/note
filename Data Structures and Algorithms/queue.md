# 队列
## 基本操作：
**入队**： enqueue    在表末端（叫做表尾（rear））插入一个元素
**出队**：dequeue    在表开头（叫做表头（front））删除一个元素

## 链表实现 
表尾部插入，表头删除

## 数组实现  
入队时，通过rear的位置判断队列是否已满。如果没有满，则将rear后移一位，将新元素放置在rear所在位置。出队时，也可以通过rear的
位置判断队列是否为空。如果不空，则只需将front后移一位即可。 获取队头元素，判断队列不空，则只需返回front指向位置的元素即可。
   
**•存在问题**
通过出队操作将数据弹出队列后，front之前的空间不能够再次得到。所以使用普通数组实现队列，就再也不能使用front之前的空间了，这会导致大量空间丢失。<br>

设数组长度为M，数组空间固定，则：<br>
–当front=0,rear=M时，再有元素入队发生溢出——真溢出<br>
–当front!=0,rear=M时，再有元素入队发生溢出——假溢出 <br> 


**•解决方案**
1.队首固定，每次出队剩余元素向下移动——时间复杂度增加 <br> 
2.循环队列 <br> 
»基本思想：把队列设想成环形，让sq[0]接在sq[M-1]之后，若rear+1==M,则令rear=0;<br>