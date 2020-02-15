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

<a href="https://www.codecogs.com/eqnedit.php?latex=0.3&space;\times&space;0.3&space;\times&space;0.3&space;=&space;0.027&space;\&space;(=&space;2.7\%)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?0.3&space;\times&space;0.3&space;\times&space;0.3&space;=&space;0.027&space;\&space;(=&space;2.7\%)" title="0.3 \times 0.3 \times 0.3 = 0.027 \ (= 2.7\%)" /></a>

となります。  

2.7%なら、まぁなくはないかなぁ・・・程度のものです。  
**デレステで星５を一連で引き当てるようなもの**
です。(2020年2月現在で3%)  

## 本当に珍しい事象なの？

3ターンで3タテされる確率は2.7%と出ましたが、これは本当に珍しい確率なのでしょうか？  
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

一撃必殺技の場合は、当たる場合が成功の方になるので、当たる確率は・・・

<img width="300" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74586377-3833f880-502a-11ea-88be-db74f597fe0a.png">

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;1)&space;=&space;0.3" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;1)&space;=&space;0.3" title="P(X = 1) = 0.3" /></a>

当たらない確率は・・・

<img width="300" alt="one-hit_kill1" src="https://user-images.githubusercontent.com/39772824/74589029-11cf8680-5045-11ea-8b94-1cdc16abc445.png">

<a href="https://www.codecogs.com/eqnedit.php?latex=P(X&space;=&space;0)&space;=&space;0.7" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(X&space;=&space;0)&space;=&space;0.7" title="P(X = 0) = 0.7" /></a>

と表すことができます。  
