An [[expression]] can have local name-[[value]] bindings defined with the let special form. The following refers to Scheme.

(let _listofnameandvaluepairs [[expression]]_)  
where _name and [[value]] pairs_ is a list of pairs (_namevalue_) and [[expression]] is returned in which each name is replaced with its [[value]] in the list
-   Input:
	- (let ((a 3)  
	- (b 4)  
     )  
     (hypot a b)  
)
- Output: 5

A name can be bound to a [[function]] in let
-   Input:
- (let ((sqr (lambda (x) (* x x)))  
      (y 3)  
     )  
     (sqr y)  
)
- Output: 9

# Recursive Bindings
- An [[expression]] can have local _recursive_ [[function]] bindings defined with the letrec special form
- (letrec _listofnameandvaluepairs [[expression]]_)
- where _name and [[value]] pairs_ is a list of pairs (_namevalue_) and [[expression]] is returned where each name is replaced with its [[value]]
-   This allows a local [[function]] fact to refer to itself