# LSTM based Conversation Models

[arXiv](https://arxiv.org/abs/1603.09457)

## Field

NLP, Neural Network, Dialogue System

## Purpose

2人での会話における，参加者の役割と文脈を盛り込んだ会話モデルの提案．

## Former

LSTMの使い方が異なる．

## Breakthrough

Perplexity, Recall共に向上．

## Challenge

教師有り領域の知識をモデルに組み込み，応答のトピックへの関連性を高める．

## Approach

役割係数(role factor)とトピック(topic feature)をLSTMに入力することで，
違う役割のための単語分散(word distribution)をモデル化する．

## Theorem

RNNLM(LSTM) <+ speaker roles <+ topic context
Let
```latex
x_1, ..., x_I
```

as word sequence,

```latex
p(x_i \mid {\bf x}_{\leqslant i-1}) \propto g_r(h_i)
= softmax(W_r h_i)
= softmax(W_r f_\theta (x_i, h_{i-1}))

h_{t,1} = f_\theta (x_{t,1}, h_{t-1, N_{t-1}})
```

where t is number of turn, 1 is number of recursion, N is number of words in the turn,
as probabilities.

同じ役割を共有し続ける文章(複数)の最小単位，一連の対話をturnとする．



