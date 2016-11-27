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
例えば`hoge::*special*`としていたシンボルが`*special*`として参照出来る。  
基本的には事前にasdfでロードした外部ライブラリのパッケージ名を列挙することになる。  
:exportで指定したシンボルは外部から参照可能(public)になる。

## パッケージの読み込み方  
```lisp
(use-package :hoge)
```

上記の:useで指定するのと同じ。
