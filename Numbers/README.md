## 数字之谜

### 二进制中1的个数

1. 对2取余，循环右移（除以2向下取整）
2. 和1进行“与”操作，循环右移（右移位运算）
3. 和自身减1进行“与”操作，直到自身为0
4. 查表法……（前提是位数不大）

### 阶乘

* 末尾0的个数：
  * 因子5的指数
  * 对于 $N!$ ，$Z=[N/5]+[N/5^2]+[N/5^3]+ \dots$
* 二进制中最低位1的位置：
  * 对于 $N!$ ，$Z=[N/2]+[N/2^2]+[N/2^3]+ \dots$
  * 等于N减去N的二进制表示中1的数目

### 寻找发帖“水王”

1. 对所有帖子ID进行排序，则中间的帖子就是
2. 每次删除两个不同的ID，不断缩小范围

### 1的数目

* 1到N之间出现“1”的个数
  * 个位+十位+百位+……
* $f(N)=N$
  * 数学归纳法

### 寻找最大k个数

1. 部分排序：选择排序、交换排序——$O(N*K)$
2. 快排思想
3. 二分法找出第k+1大的数
4. 维护一个最小堆
5. 分区块进行统计

### 精确表达浮点数

$X=0.a_1a_2\dots a_n(b_1b_2\dots b_m)$

令$Y=0.(b_1b_2\dots b_m)$，则有

$X=(a_1a_2\dots a_n+Y)/10^n$

​     $=(a_1a_2\dots a_n+b_1b_2\dots b_m/(10^m-1))/10^n$

### 最大公约数问题

1. 辗转相除法 $f(x,y)=f(y,x\%y)$ 
2. 把取模变为减法 $f(x,y)=f(x-y,y)$
3. $f(x,y)=f(x'*k,y'*k)=k*f(x',y')$，$f(x,y)=f(p*x',y)=f(x',y)$，取$p=2$，若均为偶数则利用前一个式子，若一奇一偶则利用后一个式子，若都为奇数则利用上面的式子

### 找符合条件的整数

任给一个正整数$N$，求一个最小正整数$M(M>1)$，使得$N*M$的十进制表示只有0和1。

> 从由0和1构成的数中寻找，保留余数信息，剪枝同余的数

### Fibonacci 数列

1. 递归

2. 保存计算过的项进行递归优化

3. 求解通项公式（特征方程）

4. 分治

   $(F_n \quad F_{n-1})=(F_{n-1} \quad F_{n-2})*A$

   $A=\begin{pmatrix}1&1\\1&0\end{pmatrix}$

   $(F_n \quad F_{n-1})=(F_{n-1} \quad F_{n-2})*A=(F_{n-2} \quad F_{n-3})*A=\dots=(F_1 \quad F_0)*A^{n-1}$

### 数组最大值和最小值

1. 把相邻的两个数，大数放在奇位，小数放在偶位，比较一遍即可
2. 把相邻的两个数中，大数和Max比较，小数和Min比较
3. 分治，分为两部分来算

以上三种方法复杂度一致，第一种会打乱原数组顺序，分治法对拓展有利，比如找第二大的

### 寻找最近点对

1. 一维的情况可以先排序，再计算相邻两个点的距离

2. 分治，在某个方向上分为两部分，分别求出两部分的最近点对，再跟中间MDist的比较

   $MDist=Max(Min_{center2left},Min_{center2right})$

### 寻找满足条件的两个数

从一个数组中找出两个数，和为一指定值。

1. 对$\forall x_i \in X$，判断$sum-x_i$是否在数组中
2. 利用两个下标进行遍历，一前一后，和小于$sum$时左边右移，大于时右边左移

### 子数组最大乘积

1. 空间换时间，$h[i],t[i],p[i]$分别表示$\prod_1^ia[i-1],\prod_i^na[i],h[i-1]\times t[i+1]$，计算出$h[i],t[i]$就可以很容易得到$p[i]$
2. 遍历统计数组中正数、负数、0的个数以及绝对值最小的正数、绝对值最小和最大的负数，后续进行分析即可

### 子数组之和最大值

1. 两层循环遍历
2. 分治算法
3. $max(A[0],A[0]+nStart,nAll)$

### 二维子数组之和最大值

1. 空间换时间，利用$Area[i,j]=Area[i-1,j]+Area[i,j-1]-Area[i-1,j-1]+X(i,j)$计算得到部分和，然后利用$Result[(i_{min},j_{min}),(i_{max},j_{max})]=Area[i_{max},j_{max}]-Area[i_{min}-1,j_{max}]-Area[i_{max},j_{min}-1]+Area[i_{min}-1,j_{min}-1]$
2. 先枚举左右边界的情况，对上下边界采用一维的方法去做即可

### 最长递增子序列

遍历入栈，对一个新元素，先跟栈顶元素比较，如果小则入新栈，等于则跳过，大于则入栈。

对于长度最长的栈，如果出现新的相同长度的栈，则销毁栈顶元素较大的。（前提是只需要一个最长递增子序列）

### 数组循环位移

1. 采用一个临时变量来存储
2. 逆序前k位，逆序剩下的几位，逆序全部

### 数组分割

> 待补充

### 区间重合判断

排序 -> 合并 -> 查找
