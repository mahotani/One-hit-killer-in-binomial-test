# 一撃必殺技で三タテ！バグでは？

ポケモンの対戦で、30%の確率で当たればどんなにステータスに差があったとしてもひんしにさせることができる技があります。  

主な一撃必殺技
---

<img width="300" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74586461-e63fa280-502a-11ea-990f-05620ca3d264.png">
<img width="300" alt="one-hit_kill2" src="https://user-images.githubusercontent.com/39772824/74586381-3a965280-502a-11ea-80de-122b7919d1e2.png">

- ハサミギロチン
- つのドリル
- じわれ
- ぜったいれいど

これらの技で３タテなんかされたら
**「どっかバグってるのでは？」**
と疑いたくなります。  

## 3タテされる確率は？

とりあえず、単純に3ターンで3タテされる（3回一撃必殺技を打たれて、3回とも当てられてしまった）確率を求めてみましょう。  

<img width="600" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74602273-49dcd500-50ea-11ea-8be6-96720a35d609.png">

となります。  

2.7%なら、まぁなくはないかなぁ・・・程度のものです。  
**デレステでSSRを一連で引き当てるようなもの**
です。(2020年2月現在で3%)  

## 本当に珍しい事象なの？

3ターンで3タテされる確率は2.7%と出ましたが、これは本当に珍しい事象なのでしょうか？  
試しに二項検定をしてみましょう。  

## 二項検定

二項検定とは、「二項分布を用いた統計的仮説検定」のことです。  
統計学では、まず仮説を立てるとこから始まります。  
例えば、

- マクドナルドとケンタッキーのLサイズのポテトの本数に差はない
- A型インフルエンザとB型インフルエンザの致死率には差はない

のように仮説をたてます。  
これらの「差はない」とする仮説のことを
**帰無仮説**
と呼びます。  
逆に「差がある」とする仮説のことを
**対立仮説**
と呼びます。  
この帰無仮説と対立仮説のどっちが正しいの？というのを調べるのが統計学での検定になります。

## 二項分布

今回のように、
**「技を使ったら当たるのか当たらないのか」**
のように結果が2つしかない試行のことを
**ベルヌーイ試行**
といいます。  

### ベルヌーイ試行

ベルヌーイ試行では、一般に2つの結果のうち一方を「成功」とし、確率変数Xがとる値を「1」。もう一方を「失敗」とし、Xがとる値を「0」とします。  
要は起こったら嬉しい方を1、嫌な方を0にしようということです。  
成功した時の確率をpとして式で表すと、成功時は・・・

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;1)&space;=&space;p" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;1)&space;=&space;p" title="P(X = 1) = p" /></a>

失敗時は・・・

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;0)&space;=&space;1&space;-&space;p" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;0)&space;=&space;1&space;-&space;p" title="P(X = 0) = 1 - p" /></a>

となります。

一撃必殺技の場合は、当たる場合が成功の方になり、当たる確率は30%なので・・・

<img width="300" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74586377-3833f880-502a-11ea-88be-db74f597fe0a.png">

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;1)&space;=&space;0.3" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;1)&space;=&space;0.3" title="P(X = 1) = 0.3" /></a>

当たらない確率は・・・

<img width="300" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74589029-11cf8680-5045-11ea-8b94-1cdc16abc445.png">

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;0)&space;=&space;1&space;-&space;0.3&space;=&space;0.7" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;0)&space;=&space;1&space;-&space;0.3&space;=&space;0.7" title="P(X = 0) = 1 - 0.3 = 0.7" /></a>

と表すことができます。  

### 本題の二項分布とは・・・

ベルヌーイ試行を複数回行い、成功した回数Xが従う分布のことを
**二項分布**
といいます。

n回のベルヌーイ試行を行い、k回成功する(X = k)確率を次の式で表します。

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;k)&space;=&space;{}_n&space;C&space;_k&space;p^k&space;(1&space;-&space;p)^{(n&space;-&space;k)}&space;\&space;\&space;\&space;(k&space;=&space;0,&space;1,&space;2,&space;\cdots&space;,&space;n)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;k)&space;=&space;{}_n&space;C&space;_k&space;p^k&space;(1&space;-&space;p)^{(n&space;-&space;k)}&space;\&space;\&space;\&space;(k&space;=&space;0,&space;1,&space;2,&space;\cdots&space;,&space;n)" title="P(X = k) = {}_n C _k p^k (1 - p)^{(n - k)} \ \ \ (k = 0, 1, 2, \cdots , n)" /></a>

<img width="600" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74601341-7d1a6680-50e0-11ea-9f8c-f3db332f7c54.png">

つまり、3回一撃必殺技を放って、0回当たる確率〜3回当たる確率は・・・

**0回**

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;0)&space;=&space;{}_3&space;C_0&space;0.3^0&space;\times&space;0.7^3&space;=&space;0.343" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;0)&space;=&space;{}_3&space;C_0&space;0.3^0&space;\times&space;0.7^3&space;=&space;0.343" title="P(X = 0) = {}_3 C_0 0.3^0 \times 0.7^3 = 0.343" /></a>

**1回**

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;1)&space;=&space;{}_3&space;C_1&space;0.3^1&space;\times&space;0.7^2&space;=&space;0.441" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;1)&space;=&space;{}_3&space;C_1&space;0.3^1&space;\times&space;0.7^2&space;=&space;0.441" title="P(X = 1) = {}_3 C_1 0.3^1 \times 0.7^2 = 0.441" /></a>

**2回**

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;2)&space;=&space;{}_3&space;C_2&space;0.3^2&space;\times&space;0.7^1&space;=&space;0.189" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;2)&space;=&space;{}_3&space;C_2&space;0.3^2&space;\times&space;0.7^1&space;=&space;0.189" title="P(X = 2) = {}_3 C_2 0.3^2 \times 0.7^1 = 0.189" /></a>

**3回**

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;3)&space;=&space;{}_3&space;C_3&space;0.3^3&space;\times&space;0.7^0&space;=&space;0.027" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;3)&space;=&space;{}_3&space;C_3&space;0.3^3&space;\times&space;0.7^0&space;=&space;0.027" title="P(X = 3) = {}_3 C_3 0.3^3 \times 0.7^0 = 0.027" /></a>

一応、全ての事象の確率を足し合わせると1になります。  

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;0)&space;&plus;&space;P(X&space;=&space;1)&space;&plus;&space;P(X&space;=&space;2)&space;&plus;&space;P(X&space;=&space;3)&space;\\&space;=&space;0.343&space;&plus;&space;0.441&space;&plus;&space;0.189&space;&plus;&space;0.027&space;\\&space;=&space;1.0" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;0)&space;&plus;&space;P(X&space;=&space;1)&space;&plus;&space;P(X&space;=&space;2)&space;&plus;&space;P(X&space;=&space;3)&space;\\&space;=&space;0.343&space;&plus;&space;0.441&space;&plus;&space;0.189&space;&plus;&space;0.027&space;\\&space;=&space;1.0" title="P(X = 0) + P(X = 1) + P(X = 2) + P(X = 3) \\ = 0.343 + 0.441 + 0.189 + 0.027 \\ = 1.0" /></a>

コロモゴロフの確率の公理より当たり前のことですね。

### 平均と分散は？

試行回数をn、成功確率をpとした時の二項分布の平均と分散はそれぞれ以下の通りになる。

**平均**

<a href="https://www.codecogs.com/eqnedit.php?latex=E[X]&space;=&space;np" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E[X]&space;=&space;np" title="E[X] = np" /></a>

**分散**

<a href="https://www.codecogs.com/eqnedit.php?latex=V[X]&space;=&space;E[X^2]&space;-&space;\{&space;E[X]&space;\}^2&space;\\&space;\\&space;=&space;\{&space;n(n&space;-&space;1)p^2&space;&plus;&space;np&space;\}&space;-&space;(np)^2&space;\\&space;\\&space;=&space;np&space;(1&space;-&space;p)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?V[X]&space;=&space;E[X^2]&space;-&space;\{&space;E[X]&space;\}^2&space;\\&space;\\&space;=&space;\{&space;n(n&space;-&space;1)p^2&space;&plus;&space;np&space;\}&space;-&space;(np)^2&space;\\&space;\\&space;=&space;np&space;(1&space;-&space;p)" title="V[X] = E[X^2] - \{ E[X] \}^2 \\ \\ = \{ n(n - 1)p^2 + np \} - (np)^2 \\ \\ = np (1 - p)" /></a>

細かい証明等々は別ページに記載します。

## 二項検定してみよう

まず、有意水準を決めます。  
有意水準とは、統計的仮説検定において誤りを起こしてしまう確率のことです。
一般的に
<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a>
で表し、
<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha&space;=&space;0.05" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha&space;=&space;0.05" title="\alpha = 0.05" /></a>
もしくは
<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha&space;=&space;0.01" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha&space;=&space;0.01" title="\alpha = 0.01" /></a>
と設定することが多いです。

最近のトレンドは
<a href="https://www.codecogs.com/eqnedit.php?latex=\alpha&space;=&space;0.01" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha&space;=&space;0.01" title="\alpha = 0.01" /></a>
なので今回も0.01に設定して話を進めていくことにします。

次に以下の式にしたがって検定統計量というものを算出します。  
検定統計量は検定するための値と思っていただければ良いです。

<a href="https://www.codecogs.com/eqnedit.php?latex=z&space;=&space;\frac{X&space;-&space;np}{\sqrt{np(1&space;-&space;p)}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?z&space;=&space;\frac{X&space;-&space;np}{\sqrt{np(1&space;-&space;p)}}" title="z = \frac{X - np}{\sqrt{np(1 - p)}}" /></a>

分子のnpは先ほどの平均で、分母の根号の中は分散と同じです。  
Xは対象としている確率変数が入ります。  
今回の場合は、

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;3)&space;=&space;{}_3&space;C_3&space;0.3^3&space;\times&space;0.7^0&space;=&space;0.027" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;3)&space;=&space;{}_3&space;C_3&space;0.3^3&space;\times&space;0.7^0&space;=&space;0.027" title="P(X = 3) = {}_3 C_3 0.3^3 \times 0.7^0 = 0.027" /></a>

なので0.027が入ります。

実際に当てはめてみましょう。

<a href="https://www.codecogs.com/eqnedit.php?latex=z&space;=&space;\frac{X&space;-&space;np}{\sqrt{np(1&space;-&space;p)}}&space;\\&space;\\&space;=&space;\frac{0.027&space;-&space;3&space;\times&space;0.3}{\sqrt{3&space;\times&space;0.3&space;\times&space;(1&space;-&space;0.3)}}&space;\\&space;\\&space;=&space;\frac{0.027&space;-&space;0.9}{\sqrt{0.63}}&space;\\&space;\\&space;=&space;-1.3857&space;\cdots" target="_blank"><img src="https://latex.codecogs.com/gif.latex?z&space;=&space;\frac{X&space;-&space;np}{\sqrt{np(1&space;-&space;p)}}&space;\\&space;\\&space;=&space;\frac{0.027&space;-&space;3&space;\times&space;0.3}{\sqrt{3&space;\times&space;0.3&space;\times&space;(1&space;-&space;0.3)}}&space;\\&space;\\&space;=&space;\frac{0.027&space;-&space;0.9}{\sqrt{0.63}}&space;\\&space;\\&space;=&space;-1.3857&space;\cdots" title="z = \frac{X - np}{\sqrt{np(1 - p)}} \\ \\ = \frac{0.027 - 3 \times 0.3}{\sqrt{3 \times 0.3 \times (1 - 0.3)}} \\ \\ = \frac{0.027 - 0.9}{\sqrt{0.63}} \\ \\ = -1.3857 \cdots" /></a>

二項検定は標準正規分布の元、検定を行います。

<img width="400" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74603037-667d0b00-50f2-11ea-8f1f-729af970b9e4.png">

この分布は積分すると１になるのですが、この分布内のどれぐらい端に当たるのかなぁというのを見るのが統計的検定です。  

今回の事象をこの分布に当てはめていくと以下の通りになります。

<img width="600" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74603369-2a4ba980-50f6-11ea-9676-fb02742eb8a0.png">

上の図の青い線(-2.25)の部分が先に決めた有意水準に対応しており、赤い線(-1.3857)の部分が検定統計量に対応しています。  

青い線よりも左に赤い線があった場合はちょっとやばいんじゃないか？と思われる事象だったのですが、今回はそこまで珍しい事象ではないという結果になりました。  
つまり、一撃必殺技で3ターンで3タテされても**お使いのゲームは正常です**。

## 余談：何回連続で当たればバグを疑える？

3回だと大したことがないということがわかりましたが、果たして何回連続で当たればおかしい事象であると言えるのだろうかということが気になります。

上記の図より検定統計量が-2.25を下回れば良いので、以下の式を解くとわかります。

<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{0.3^n&space;-&space;0.3n}{\sqrt{0.27n}}&space;<&space;-2.25" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{0.3^n&space;-&space;0.3n}{\sqrt{0.27n}}&space;<&space;-2.25" title="\frac{0.3^n - 0.3n}{\sqrt{0.27n}} < -2.25" /></a>

これをnについて解くと・・・

<a href="https://www.codecogs.com/eqnedit.php?latex=n&space;>&space;15.1875" target="_blank"><img src="https://latex.codecogs.com/gif.latex?n&space;>&space;15.1875" title="n > 15.1875" /></a>

となります。  
つまり、**16回連続**で当たってしまった場合は**お使いのゲームは正常ではないかもしれません**。
