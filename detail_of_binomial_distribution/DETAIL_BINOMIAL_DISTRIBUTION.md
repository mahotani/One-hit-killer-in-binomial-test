# 二項分布の補足

## 平均

二項分布は離散型確率変数です。  
なので、平均を求めるには、

<a href="https://www.codecogs.com/eqnedit.php?latex=E(X)&space;=&space;\sum^n_{k&space;=&space;1}&space;x_k&space;\times&space;f(X)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E(X)&space;=&space;\sum^n_{k&space;=&space;1}&space;x_k&space;\times&space;f(X)" title="E(X) = \sum^n_{k = 1} x_k \times f(X)" /></a>

の式に当てはめていきましょう。

この時、
<a href="https://www.codecogs.com/eqnedit.php?latex=x_k" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_k" title="x_k" /></a>
は技が当たる回数なので、1 ~ n回の全パターンなので
<a href="https://www.codecogs.com/eqnedit.php?latex=k" target="_blank"><img src="https://latex.codecogs.com/gif.latex?k" title="k" /></a>
にします。

<a href="https://www.codecogs.com/eqnedit.php?latex=f(X)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f(X)" title="f(X)" /></a>
の部分に関しては、確率分布が入ります。  
今回は二項分布なので、技が当たる確率をp、技が当たる回数をkとすると、  

<a href="https://www.codecogs.com/eqnedit.php?latex=f(X)&space;=&space;{}_n&space;C_k&space;p^k&space;(1&space;-&space;p)^{(n&space;-&space;k)}&space;\&space;\&space;\&space;\&space;\&space;\&space;(k&space;=&space;0,&space;1,&space;\cdots,&space;n)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f(X)&space;=&space;{}_n&space;C_k&space;p^k&space;(1&space;-&space;p)^{(n&space;-&space;k)}&space;\&space;\&space;\&space;\&space;\&space;\&space;(k&space;=&space;0,&space;1,&space;\cdots,&space;n)" title="f(X) = {}_n C_k p^k (1 - p)^{(n - k)} \ \ \ \ \ \ (k = 0, 1, \cdots, n)" /></a>

となります。

これらを平均を求める式に代入して解いていきましょいう。

<a href="https://www.codecogs.com/eqnedit.php?latex=E(X)&space;\\&space;=&space;\sum^n_{k&space;=&space;0}&space;k&space;{}_n&space;C_k&space;p^k&space;(1&space;-&space;p)^{(1&space;-&space;k)}&space;\\&space;=&space;\sum^n_{k&space;=&space;1}&space;k&space;{}_n&space;C_k&space;p^k&space;(1&space;-&space;p)^{(1&space;-&space;k)}&space;\\" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E(X)&space;\\&space;=&space;\sum^n_{k&space;=&space;0}&space;k&space;{}_n&space;C_k&space;p^k&space;(1&space;-&space;p)^{(1&space;-&space;k)}&space;\\&space;=&space;\sum^n_{k&space;=&space;1}&space;k&space;{}_n&space;C_k&space;p^k&space;(1&space;-&space;p)^{(1&space;-&space;k)}&space;\\" title="E(X) \\ = \sum^n_{k = 0} k {}_n C_k p^k (1 - p)^{(1 - k)} \\ = \sum^n_{k = 1} k {}_n C_k p^k (1 - p)^{(1 - k)} \\" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\because" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\because" title="\because" /></a>
k = 0の場合、
<a href="https://www.codecogs.com/eqnedit.php?latex=0&space;\times&space;{}_n&space;C_0&space;\times&space;p^0&space;\times&space;(1&space;-&space;p)^{(n&space;-&space;k)}&space;=&space;0" target="_blank"><img src="https://latex.codecogs.com/gif.latex?0&space;\times&space;{}_n&space;C_0&space;\times&space;p^0&space;\times&space;(1&space;-&space;p)^{(n&space;-&space;k)}&space;=&space;0" title="0 \times {}_n C_0 \times p^0 \times (1 - p)^{(n - k)} = 0" /></a>
となるので、足しても関係ないので飛ばして良い。

