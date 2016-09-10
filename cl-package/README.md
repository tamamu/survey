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

:useで指定した名前空間は省略可能になる。  
:exportで指定したシンボルは外部から参照可能になる。

## パッケージの読み込み方  
```lisp
(in-package :cl-user)
(defpackage hoge)
(in-package :hoge)
```

最初にユーザー用パッケージに入って名前空間を初期化する。  
その後に作成したパッケージに入る。
