# Distributed Representations of Words and Phrases and their Compositionality

###### Skip-gram model, softmax, negative sampling, binary Huffman tree

> Distributed representations of words in a vector space help learning algorithms to achieve better performance in natural language processing tasks by grouping similar words.

ベクトル空間内の単語の分布表現は、似た単語をグルーピングすることによって、自然言語処理のタスクをより良い性能にするためのアルゴリズムを学びやすくする。

> Skip-gram model, an efficient method for learning high-quality vector representations of words from large amounts of unstructured text data.

Skip-gramモデルは、大量の構造化されていないテキストデータから、単語の良いベクトル表現を学習するための効率的な方法である。

> The word representations computed using neural networks are very interesting because the learned vectors explicitly encode many linguistic regularities and patterns.

ニューラルネットワークを使って計算された単語表現はとても興味深い。なぜなら学習したベクトルは、明確に、多くの言語学的規則やパターンを符号化するからだ。


Skip-gramモデルで訓練の目標となるのは、周辺の単語を予測するのに適した単語のベクトル表現を学習すること。

> In our work we use a binary Huffman tree, as it assigns short codes to the frequent words which results in fast training. It has been observed before that grouping words together by their frequency words well as a very simple speedup technique for the neural network based language models.

我々は仕事で、頻出語句に短いコードを割り振るためにbinary Huffman treeを使っているが、それは結果として高速な訓練となっている。これはニューラルネットワークベースの言語モデルのための非常に単純な高速化技術として、頻出語句のグルーピングの前によく見られる。


Hierarchical Softmaxの代わりとなるのがNoise Contrastive Estimationである。
それに対してNegative Samplingはそのどちらよりも速い。


> The subsampling of the frequent words improves the training speed several times and makes the word representations significantly more accurate.

頻出語句のサブサンプリングは学習スピードを数倍に改善し、単語表現をより正確にする。
