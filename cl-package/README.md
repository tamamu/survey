# CLにおけるパッケージの扱い

## パッケージとは  
他のプログラミング言語におけるモジュールシステム。  
名前空間とエクスポートするシンボル(すなわち関数や変数)を記述する仕組み。  
ES6のimport/exportの仕様が近い気がする。

## パッケージの定義方法  
```lisp
(defpackage package-name
  (:nicknames :package-nickname)
  (:use :cl :name-space-A :name-space-B)
  (:export variable-A variable-B function-A function-B))
```

:useで指定したパッケージ名(名前空間)は省略可能になる。  
基本的には事前にasdfでロードした外部ライブラリのパッケージ名を列挙する。  
:exportで指定したシンボルは外部から参照可能(public)になる。

## パッケージの読み込み方  
```lisp
(in-package :cl-user)
(defpackage hoge)
(in-package :hoge)
```

環境をリセットするため、最初にユーザー用パッケージに入って名前空間を初期化する。  
これで事前に定義されたシンボルを忘れることが出来るため、シンボル名が被る可能性も極力減らせる。  
その後に作成したパッケージに入る。
