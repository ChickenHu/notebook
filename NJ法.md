基本原理正如同它的名字——neighbor joining，找到邻居并合并。
## 菊花图
NJ 法的合并操作是在一颗菊花图上进行的，0 号并不是一个 OTU，它只是我为了方便画图假定的一个节点
![[graph.png]]
## Q 矩阵

类似但不同于 UPGMA，NJ 法使用了一个名叫 Q 矩阵的东西代替距离矩阵，每次找出 Q 矩阵中值最小的一对节点进行合并

对于每两个节点，有

$$
Q(i,j)=(n-2)distance(i,j)-\sum\limits_{k=1}^ndistance(i,k)-\sum\limits_{k=1}^ndistance(j,k)
$$
## 构建
构建出 Q 矩阵后，每一次合并操作还会涉及到**距离**和**Q 矩阵**的更新。和假定演化速率相同的 UPGMA 不一样，NJ 法涉及到了一些校正

首先是新的距离，假定 i, j 节点合并到了同一个共同祖先 f 上，则有

![[NJ法 2025-04-25 15.19.39.excalidraw]]

$$
distance(f,i)=\frac{1}{2}distance(i,j)+  \frac{1}{2(n-2)}\left[\sum\limits_{k=1}^ndistance(i,k)-\sum\limits_{k=1}^ndistance(j,k)\right]
$$

可以注意到，式子的后半部分就是 NJ 法中引入的校正，且对于 i 和 j 不过是符号的差异。因此有

$$
\begin{align}
distance(f,i)+distance(f,j)&=distance(i,j)\\
distance(f,j)&=distance(i,j)-distance(f,i)
\end{align}
$$

现在只需要用 f 节点代替原来的 i 和 j，参与新一轮的构建，这里为了维持总枝长保持不变, 更新距离的操作和 UPGMA 有点像
$$
distance(k,f)=\frac{1}{2}\left[distance(k,i)+distance(k,j)-distance(i,j)\right]
$$
再用更新后的距离计算新的 Q 矩阵
## 什么时候结束？
当最后 Q 矩阵只剩下 3 个节点时，有且仅有一种拓扑结构 ![[graph(1).png]]
例如这张图中，最后一轮只会剩下**并非 OTU4**、**并非OTU2**、**3**三个节点，此时拓扑结构已经确定下来，进行更多的构建没有意义