# CLにおけるクラス

## Common Lisp Object System
略称CLOS。Common Lispをオブジェクト指向的に扱えるように標準機能として実装された。  
多重ディスパッチ・多重継承・動的クラス変更を大きな特徴として備えている。  

## 使い方  
1 クラス定義  
```lisp
(defclass flyable () ())                ;; as an interface

(defclass cryable ()                    ;; superclass for bird and airplane
  ((onomatopoeia :accessor get-onmtp    ;; accessor for get value from the slot
                 :initarg :onmtp        ;; keyword for initialization (make-instance :onmtp "baz")
                 :initform "twitter"))) ;; default value

(defclass bird (flyable cryable)        ;; subclass of flyable and cryable
  ((name :accessor look-name
         :initarg :name)
   (color :accessor look-color
          :initarg :color)))

(defclass airplane (flyable)            ;; subclass of flyable
  ((from :accessor where-from
         :initarg :from)
   (to :accessor where-to
       :initarg :to)))
```

2 メソッド定義  
```lisp
(defmethod fly ((obj flyable))                ;; fly method for flyable
  (format t "~A can fly!!~%"
    (type-of obj)))

(defmethod fly :before ((ap airplane))        ;; it's called before the airplane fly
  (format t "This airplane from ~A to ~A.~%"
    (where-from ap) (where-to ap)))

(defmethod cry ((animal cryable))             ;; cry method for cryable
  (format t "~A cries ~A.~%"
    (type-of animal)
	(get-onmtp animal)))

(defmethod look-for ((bird bird))             ;; look-for method for bird
  (format t "We look for the ~A bird, ~A.~%"
    (look-color bird)
    (look-name bird))
  (when (typep bird 'cryable)                 ;; typep for superclass is also t
    (format t "The clue is his cry as ~A.~%"
	  (get-onmtp bird))))
```

3 インスタンス化  
```lisp
(setf karas (make-instance 'bird :name "crow" :color 'black))
(setf jal (make-instance 'airplane :from 'tokyo :to 'los-angeles))
```

4 メソッド呼び出し
```lisp
(fly jal)
(look-for karas)
(fly karas)
(cry karas)
```