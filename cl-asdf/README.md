# ASDFの使い方

## ASDFの役割  
Lispシステムのコンパイルやロード、テストを司る。  
より分かりやすい表現では、外部ライブラリのリンクやテストの実行関数を提供する。

## 使い方  
外部システムはQuicklispでダウンロード・インストールすれば良いとして、それをロードするにはパスを通さなければならない。  
ASDFのデフォルトパスは`~/common-lisp`と`~/.local/share/common-lisp/source`を示している。  
基本的にはこの中にシステムをインストールすれば良いのだが、Quicklispは`~/quicklisp/dists/(dist name)/software/`にシステムをインストールしてしまう(Roswellを使っている場合は`~/.roswell/impls/ALL/ALL/quicklisp/dists/quicklisp/software/`)。  
ASDFの設定は`~/.config/common-lisp/source-registry.conf`に書く。  
```lisp
(:source-registry
  (:tree "~/quicklisp/dists/")
  (:tree "~/lisp-dev/")
  :INHERIT-CONFIGURATION)
```

:treeは下に書くほど優先度が高いため、開発版のテストなどをしたい時は`~/lisp-dev`にシステムを置くと良い。  
これで`(require 'your-system)`または`(asdf:load-system 'your-system)`で外部システムをロード出来る。  
テストをしたい時は`(asdf:test-system 'your-system)`で実行してくれる。  
ちなみにQuicklispは内部でASDFを呼んでいるので、quickloadのパスにも適用される。  

## 参考  
[require, ASDF, quicklispを正しく使う](http://keens.github.io/blog/2014/11/30/quicklisp/)
