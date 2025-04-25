基本原理正如同它的名字——neighbor joining，找到邻居并合并。
## Q 矩阵
类似但不同于 UPGMA，NJ 法使用了一个名叫 Q 矩阵的东西代替距离矩阵
对于每两个 OTU，有
$$
Q(i,j)=(n-2)distance(i,j)-\sum\limits_{k=1}^ndistance(i,k)-\sum\limits_{k=1}^ndistance(j,k)
$$
构建出 Q 矩阵后，每一次合并操作还会涉及到**距离**和**Q 矩阵**的更新。和假定演化速率相同的 UPGMA 不一样，