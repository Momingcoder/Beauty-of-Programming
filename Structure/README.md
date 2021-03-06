## 结构之法

### 字符串移位

判断一个字符串$s_1$所有移位后的结果是否包含另一个字符串$s_2$

1. 循环判断
2. 判断$s_2$是否为$s_1s_1$的一个子串

### 电话号码对应的英语单词

1. 直接循环法
2. 递归

判断号码对应的英语单词是否存在，可以直接把整本字典对应的号码保存下来

### 计算字符串相似度

删除、修改、增加3种情况

可以递归求解，有些地方重新计算了，可以把每次计算的结果保存下来

### 无头单链表删除节点

删除后面那个节点，把该节点的值赋到当前节点上

### 最短摘要生成

在之前搜索结果的基础上继续往后找

### 判断两个链表是否相交

1. 为第一个链表建立Hash表，查表
2. 把第二个链表头接到第一个链表尾，遍历第二个链表，看是否会回到其头部
3. 判断两个链表最后一个节点是否相同

### 队列中取最大值

1. 在队列之外维护一个最大堆
2. 维护一个最大序列

### 求二叉树中节点的最大距离

相距最远的两个节点，一定是两个叶子节点或者一个叶子节点到它的根节点。

若路径经过Root，则都是各自子树中到根节点最远的节点。

若不经过Root，则一定属于k个子树之一。

动态规划：$max{d(U_1,V_1),\dots,d(U_k,V_k),max_1+max_2+2}$

采用深度优先搜索

### 重建二叉树

给出前序和中序遍历的结果，重建一棵二叉树。

找出Root，分出左子树和右子树，递归重建。

### 分层遍历二叉树

广度搜索遍历，打印当前节点的内容并将其左右子节点入队列，直到队列为空
