An [[Expression]] can have local name-[[Value]] bindings defined with the let special form. The following refers to Scheme.

(let _listofnameandvaluepairs [[Expression]]_)  
where _name and [[Value]] pairs_ is a list of pairs (_namevalue_) and [[Expression]] is returned in which each name is replaced with its [[Value]] in the list
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
- An [[Expression]] can have local _recursive_ [[function]] bindings defined with the letrec special form
- (letrec _listofnameandvaluepairs [[Expression]]_)
- where _name and [[Value]] pairs_ is a list of pairs (_namevalue_) and [[Expression]] is returned where each name is replaced with its [[Value]]
-   This allows a local [[function]] fact to refer to itself