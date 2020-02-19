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

<a href="https://www.codecogs.com/eqnedit.php?latex==&space;\sum^n_{k&space;=&space;1}&space;k&space;\times&space;\frac{n&space;\times&space;(n&space;-&space;1)&space;\times&space;\cdots&space;\times&space;(n&space;-&space;k&space;&plus;&space;1)}{k&space;\times&space;(k&space;-&space;1)&space;\times&space;\cdots&space;\times&space;1}&space;p^k&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;=&space;\sum^n_{k&space;=&space;1}&space;k&space;\times&space;\frac{n}{k}&space;\times&space;\frac{(n&space;-&space;1)&space;\times&space;(n&space;-&space;2)&space;\times&space;\cdots&space;\times&space;(n&space;-&space;k&space;&plus;&space;1)}{(k&space;-&space;1)&space;\times&space;(k&space;-&space;2)&space;\times&space;\cdots&space;\times&space;1}&space;p^k&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;\\&space;=&space;\sum^n_{k&space;=&space;1}&space;n&space;\times&space;{}_{(n&space;-&space;1)}&space;C_{(k&space;-&space;1)}&space;p^k&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;=&space;n&space;\sum^n_{k&space;=&space;1}&space;\times&space;{}_{(n&space;-&space;1)}&space;C_{(k&space;-&space;1)}&space;p&space;\times&space;p^{(k&space;-&space;1)}&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;=&space;np&space;\sum^n_{k&space;=&space;1}&space;\times&space;{}_{(n&space;-&space;1)}&space;C_{(k&space;-&space;1)}&space;p^{(k&space;-&space;1)}&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\" target="_blank"><img src="https://latex.codecogs.com/gif.latex?=&space;\sum^n_{k&space;=&space;1}&space;k&space;\times&space;\frac{n&space;\times&space;(n&space;-&space;1)&space;\times&space;\cdots&space;\times&space;(n&space;-&space;k&space;&plus;&space;1)}{k&space;\times&space;(k&space;-&space;1)&space;\times&space;\cdots&space;\times&space;1}&space;p^k&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;=&space;\sum^n_{k&space;=&space;1}&space;k&space;\times&space;\frac{n}{k}&space;\times&space;\frac{(n&space;-&space;1)&space;\times&space;(n&space;-&space;2)&space;\times&space;\cdots&space;\times&space;(n&space;-&space;k&space;&plus;&space;1)}{(k&space;-&space;1)&space;\times&space;(k&space;-&space;2)&space;\times&space;\cdots&space;\times&space;1}&space;p^k&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;\\&space;=&space;\sum^n_{k&space;=&space;1}&space;n&space;\times&space;{}_{(n&space;-&space;1)}&space;C_{(k&space;-&space;1)}&space;p^k&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;=&space;n&space;\sum^n_{k&space;=&space;1}&space;\times&space;{}_{(n&space;-&space;1)}&space;C_{(k&space;-&space;1)}&space;p&space;\times&space;p^{(k&space;-&space;1)}&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\&space;=&space;np&space;\sum^n_{k&space;=&space;1}&space;\times&space;{}_{(n&space;-&space;1)}&space;C_{(k&space;-&space;1)}&space;p^{(k&space;-&space;1)}&space;(1&space;-&space;p)&space;^&space;{(n&space;-&space;k)}&space;\\" title="= \sum^n_{k = 1} k \times \frac{n \times (n - 1) \times \cdots \times (n - k + 1)}{k \times (k - 1) \times \cdots \times 1} p^k (1 - p) ^ {(n - k)} \\ = \sum^n_{k = 1} k \times \frac{n}{k} \times \frac{(n - 1) \times (n - 2) \times \cdots \times (n - k + 1)}{(k - 1) \times (k - 2) \times \cdots \times 1} p^k (1 - p) ^ {(n - k)} \\ \\ = \sum^n_{k = 1} n \times {}_{(n - 1)} C_{(k - 1)} p^k (1 - p) ^ {(n - k)} \\ = n \sum^n_{k = 1} \times {}_{(n - 1)} C_{(k - 1)} p \times p^{(k - 1)} (1 - p) ^ {(n - k)} \\ = np \sum^n_{k = 1} \times {}_{(n - 1)} C_{(k - 1)} p^{(k - 1)} (1 - p) ^ {(n - k)} \\" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\because" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\because" title="\because" /></a>
nとpはkに関係がないので、
<a href="https://www.codecogs.com/eqnedit.php?latex=\sum^n_{k&space;=&space;1}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum^n_{k&space;=&space;1}" title="\sum^n_{k = 1}" /></a>
の外に出せる。

<a href="https://www.codecogs.com/eqnedit.php?latex==&space;np&space;\sum^{n&space;-&space;1}_{k&space;=&space;0}&space;{}_{n&space;-&space;1}&space;C_k&space;p^k&space;(1&space;-&space;p)^{(n&space;-&space;i&space;-&space;1)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?=&space;np&space;\sum^{n&space;-&space;1}_{k&space;=&space;0}&space;{}_{n&space;-&space;1}&space;C_k&space;p^k&space;(1&space;-&space;p)^{(n&space;-&space;i&space;-&space;1)}" title="= np \sum^{n - 1}_{k = 0} {}_{n - 1} C_k p^k (1 - p)^{(n - i - 1)}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\because" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\because" title="\because" /></a>
kのあたりをすべて-1すると、
<a href="https://www.codecogs.com/eqnedit.php?latex=\sum^n_{k=0}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum^n_{k=0}" title="\sum^n_{k=0}" /></a>
の上側も下側も1ずつ減らせる。  

<a href="https://www.codecogs.com/eqnedit.php?latex==&space;np&space;(p&space;&plus;&space;(1&space;-&space;p))&space;^&space;{(n&space;-&space;1)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?=&space;np&space;(p&space;&plus;&space;(1&space;-&space;p))&space;^&space;{(n&space;-&space;1)}" title="= np (p + (1 - p)) ^ {(n - 1)}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\because" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\because" title="\because" /></a>
二項定理でググってください。

<a href="https://www.codecogs.com/eqnedit.php?latex==&space;np&space;(p&space;&plus;&space;1&space;-&space;p)&space;^&space;{(n&space;-&space;1)}&space;\\&space;=&space;np&space;\times&space;1^{(n&space;-&space;1)}&space;\\&space;=&space;np" target="_blank"><img src="https://latex.codecogs.com/gif.latex?=&space;np&space;(p&space;&plus;&space;1&space;-&space;p)&space;^&space;{(n&space;-&space;1)}&space;\\&space;=&space;np&space;\times&space;1^{(n&space;-&space;1)}&space;\\&space;=&space;np" title="= np (p + 1 - p) ^ {(n - 1)} \\ = np \times 1^{(n - 1)} \\ = np" /></a>

以上より、
<a href="https://www.codecogs.com/eqnedit.php?latex=E(X)&space;=&space;np" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E(X)&space;=&space;np" title="E(X) = np" /></a>
