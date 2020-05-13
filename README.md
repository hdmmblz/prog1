**1.用组合方法证明，$K_p$中某个顶点到自身的长为$l$的闭游动的条数是$\frac{(p-1)^l+(p-1)(-1)^l}{p}$**

解：关于邻接矩阵特征值的代数方法书里有，这里是组合方法，比较简单

设答案数列为$a_l$

设$l\ge2$,则考虑从$1$走两步后，有$(p-2)$种方法走到除$1$以外的点，有$(p-1)$种方法走到$1$,那么$\frac{a_l-a_{l-2}}{p-2}=(p-1)^{l-2}$（等式右边即为反着考虑从$1$走$l-2$步到达任意一个点），那么带入公式可证。

**5.设$H_n$为一个两边都为$n$个点的完全二分图$K_{nn}$，减去任意一个完美匹配得到的图，那么，证明这个图的邻接矩阵特征值为$+1,-1$(每个$n-1$重)和$\pm(n-1)$(每个$1$重)**

由于是二分图，当$l$是奇数时闭游动数量为零，根据本节引理1.7，本题命题的充要条件是$H_n$闭游动条数为$a_l=2[(n-1)^l+(n-1)],2|l$

根据与上一题类似的思路，我们仍然可以通过组合意义得到递推式：

$\frac{a_l-a_{l-2}}{2n(n-2)}=(n-1)^{l-1}$,发现所得通项公式即为命题所需公式，证毕

**6.完全$p$部图$K(n,p)$的闭游动条数**

观察本节1.6，只要把完全$p$部图看成$p$个点完全图，而每个点都有$n$权值的贡献即可，套用公式，可得答案为

$n^l((p-1)^l+(p-1)(-1)^l)$

**8.$G$是一个$n$个顶点的图，新加入$n$个节点，并且把第$i$个新节点和第$i$个原来的节点加一条边，得到图$G'$,$G$原来的邻接矩阵特征值为$\{\lambda\}_n$，$G'$的邻接矩阵特征值是？**

$A(G')-\lambda E=\begin{pmatrix}-\lambda E , E\\E,A(G)-\lambda E\end{pmatrix}$

这是一个分块矩阵，块消元一下得到$\begin{pmatrix}-\lambda E , O\\O,A(G)-(\lambda+\frac{1}{\lambda}) E\end{pmatrix}​$

得到$G'$的特征多项式$f_{G'}(x)=(-x)^nf_G(x+\frac{1}{x})$

可知$G'$邻接矩阵特征值为$\{(\lambda\pm\sqrt{\lambda^2+4})/2\}_{2n}$

**12.（a）设$G$是有限图，$\Delta$为$G$中最大点度数，$A(G)$最大特征值为$\lambda_1$,证明$\lambda_1\leq\Delta$**

反证，若$\lambda_1>\Delta$，闭游动条数$a_l=\sum_{i=1}^{|G|}\lambda_i^l$,同时，$a_l\leq|G|\Delta^l$

得到$\forall l>0,b_l=|G|\Delta^l-\sum_{i=1}^{|G|}\lambda_i^l\ge0$,但$\lim\limits_{l\rightarrow+\infty}\frac{b_{2l}}{\lambda_1^{2l}}<0$(因为负特征值的绝对值也肯定不能比$\lambda_1$大)，这是矛盾的，因此一定有$\lambda_1\leq\Delta$

**12.(b)设$G$是有$m$条边的简单无向图，$A(G)$最大特征值为$\lambda_1$,证明$\lambda_1\leq\sqrt{2m}$**

反证，若要$\lambda_1>\sqrt{2m}$,考虑$A^2(G)$这个矩阵必有特征值$\Lambda>2m$,但考虑以$A^2(G)$为邻接矩阵的图$G'$，$v$在$G'$中的度$deg_{G'}(v)\leq\sum_{i=1}^{|G'|}deg_G(i)=2m$,因此$\Delta_{G'}\leq2m$那么根据上一题结论，最大特征值$\Lambda_1\leq\Delta_{G'}\leq2m$,因此不可能有$\lambda_1>\sqrt{2m}$

**13.设$G$是至少两个点的简单有限无向图，$\exist l\ge1,s.t.\forall u,v\in V(G),A(G)^l_{uv} mod 2=1$证明存在非空顶点子集$S$,使得$S$非空，有偶数个节点且$G$的任意节点$v$都与$S$中偶数个顶点相连**

以下矩阵和向量运算都在$mod2$意义下进行

首先$rank(A(G)^l)=1$,说明$A(G)$ 不满秩，存在非零向量$v$，使得$A(G)v=0$

如果 $v$有奇数个$1$,那么$A(G)^lv=0$，但$A(G)^l$为全$1$矩阵$J$,因此这是不可能的，所以$v$只有偶数个$1$，$v$所对应的子集即为所求，证毕。

