# Dialog-based Language Learning

Facebook AI Research

[arXiv](https://arxiv.org/abs/1604.06045)

## Field

NLP, Machine Learning, Dialogue System

## Purpose

対話パートナーの応答に暗黙的にsupervisionを与えた対話ベース言語モデルの研究．
報酬ベースのsupervision無しでも正しく学習可能であることを示す．会話から学ぶagentの構築．

## Former

単語レベルでタグ付けを行い，与えられたsupervisionから学ぶようモデル構築を行っていた．

## Breakthrough

## Approach

会話から学ぶ，すなわち自然言語で与えられるfeedbackから学ぶ．
dialog-based language learningのための評価データセットの構築を行った(?)

* [bAbI datasets](http://fb.ai/babi)
* MovieQA dataset

## Theorem

パートナーの応答に以下のsupervisionを暗黙的に与える．

* 正負フィードバック
* 答えの提示
* ヒントの提示
* 事実・理由の提示
* フィードバック無し
* 正解の暗示
* 正解を聞かれた時の返答
* 補助事実提示
