There are two ways to process the comments: Iterate manually with imperative code, or map over
them with declarative code. If you chose to iterate manually, there are some disadvantages you
should be aware of:
• The imperative approach is more code. The iterateComments() function below doesn’t need
to exist at all if we map, instead. More code = more surface area for bugs to hide in = more
bugs.
• If the list of comments is very large, you have to wait for the entire list to arrive from the server
before you can even begin to draw the comments to the screen. If you had used map, instead,
you could swap out the array for a streaming data type and you wouldn’t need to change the
UI component at all.

### Abstraction & Composition
How to Do More with Less Code
1. Composable - The ability to compose simple functions to form more complex functions.
2. Reusable
3. Independent
4. Concise
5. Simple


### Functors & Categories
Functors data types are things we can map over. You can think of them as containers which can
have functions applied to their contents to produce a new container with the results inside.
A functor data type is something you can map over.
functor data structure as a box, and map as a way to apply a function to each item
contained inside the box, which creates a new box containing the outputs.
In [category theory](https://habr.com/ru/company/cit/blog/313254/), a functor is a structure preserving map from category to category, where
“structure preserving” means that the relationships between objects and morphisms are retained.
The point of a functor is to apply a given function to
values contained within the context of the structure.
functor.map = Functor(a) ~> (a => b) => Functor(b)
You can read the signature as functor.map, beginning with a functor of a, take a function from a to
b, and return a functor of b.
Why Functors?
Functors are great for several reasons:
• The details of the underlying data structure implementation are abstracted away. Users don’t
need to know if iteration is required, or how it’s handled if it is. You can map over arrays,
streams, trees, or anything else.
• Functors hide the types of the data they contain, which allows you to act on the containers
using generic functions, without caring about what you’re storing inside them. You don’t need
special arrays for numbers, and special arrays for strings. Instead, you pass functions into map()
that can deal with the type contained inside the functor.
• Mapping over an empty functor is the same as mapping over a functor containing many items.
Switching logic is not needed in the case of an empty collection, and there’s no need to keep
track of iteration state if the data structure enumerates over a collection of items.
• Most importantly, functors allow you to easily compose functions over the data inside.