
https://github.com/fantasyland/fantasy-land/
## :: 
The function name is written first, and then ::, which can be read as is of type or has type.
You should read:
foo :: a
as "the name foo is a value of type a". When you write:
run :: a -> b
this means:
You are declaring the name run.
This name will refer to a value that have type a -> b,
The type a -> b is the type of a function which takes a value of type a and returns another value of type b.


a fat arrow, as shown in the following code:
// compareFunction :: Sortable a ⇒ (a, a) → Number

String.repeat:: String ~> Number -> String