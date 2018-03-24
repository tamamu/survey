# Relevance of Unsupervised Metrics in Task-Oriented Dialogue for Evaluating Natural Language Generation

MS Maluuba

[arXiv](https://arxiv.org/abs/1706.09799)

## Field

NLP, Dialogue System, Neural Network, Machine Learning, Metrics

## Purpose

Automated metricsが，非タスク指向対話システムと比較して，
タスク指向対話システムにおける人間の判断と強い相関がある，
ということをAutomated metricsで既存のモデルを評価することで示す．

## Former

ルールベース・テンプレートベースな対話システムが多い
これらはドメインのcomplexityが増加するとテンプレートの数が厄介になり，
スケール出来ない．

## Breakthrough

METEORはBLEUよりもタスク指向対話システムにおける人間の判断と相関がある．
すなわち，自然言語生成に向いている．

## Challenge

実験において，
より大きく複雑なデータセットをタスク指向対話システムで使うべき．

## Approach

DSTC2, Restaurants datasetによる評価実験．

## Theorem

* Metrics
  - Word-overlap based
    + BLEU
    + METEOR
    + ROUGE
  - Embedding based
    + Skip-Thought
    + Embedding average
    + Vector extrema
    + Greedy matching
* Models
  - Random
  - LSTM
  - delex-sc-LSTM
  - hierarchical-lex-delex-sc-LSTM
