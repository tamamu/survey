# プロジェクト作成の方法

パッケージとasdファイルを組み合わせ、手軽にインストール・ロードが出来る構造をプロジェクトと呼ぶことにする。  
なお、ここではライブラリとアプリケーションを区別しない。  

## 最も楽な方法  
CL-Projectを使う。  
`(ql:quickload :cl-project)`でインストール出来るので予めしておくこと。  
仮に、`lisp-dev/`以下に`your-system`というプロジェクトを作るとしよう。  
```
(cl-project:make-project #p"lisp-dev/your-system"
  :author "Your Name"
  :email "your.email@address.com"
  :license "LLGPL"
  :depends-on '(:cl-cffi-gtk :cl-annot))
```
これでプロジェクトを構成するファイルが指定したディレクトリ以下に作成される。  
:depends-onはlistの形式で記述しないと怒られるので注意。  
このプロジェクトはパスが通っていればそのままquickload出来る。  
テストは`asdf:test-system :your-system`で実行する。  
書き方は[prove](https://github.com/fukamachi/prove)に従う。

## 参考  
[第6回 Common Lispライブラリを書く](http://modern-cl.blogspot.jp/2011/07/6-common-lisp.html)
