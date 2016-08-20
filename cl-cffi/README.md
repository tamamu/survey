# CL-CFFIに関する備忘録

### defctype  
ポインタ型を定義する。Cのtypedefに対応。
:pointerのエイリアス型的な使い方が見られるので意味合いについては要検証。  

    (defctype image* (:pointer image))


### defcstruct  
構造体の定義。Cのstructに対応。  
フィールド名と型の位置が逆なので分かりにくい。  

    (defcstruct image
      (width :int)
	  (height :int)
	  (data :string))

### defcfun  
Cの関数へのインターフェースを作成。  
最初に返り値の型を書いて、その後ろに引数を羅列する。  

    (defcfun ("c_function_name" lisp-function-name) :void
      (x :double) (y :double) (img image*))


### with-foreign-objects  
C版letみたいなやつ。  
初期値じゃなくて型を指定する。  
let1に対応するwith-foreign-objectもある。  

    (with-foreign-objects ((x :int) (y :int) (img '(:struct image)))
      (setf x 3 y 9)
      (lisp-c-function x y img))


### with-foreign-slots  
defcstructで定義した構造体のフィールドにアクセスする。  

    (with-foreign-slots ((width height data) img (:struct image))
      (setf width 320 height 240 data *image-data*))
