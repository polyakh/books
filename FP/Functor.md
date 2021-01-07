##Functional Data Types
Containers and functors
Consider what we need from this wrapper. There are two basic requirements:
We must have a map() method.
We need a simple way to wrap a value.
In true functional style, when we apply a mapping to a wrapped  value, 
the result will be another wrapped value that we can keep working on.
Instead of map(), this operation is sometimes called fmap(), standing for
functorial map. The rationale for the name change was to avoid expanding
the meaning of map(). (However, since we are working in a language that
supports reusing the name, we can keep it.)
More requirements for functors. <br />
First, the contained values may be polymorphic (of any type), just like arrays. 
Second, a function must exist whose mapping produces the same contained value—x => x does this for us. 
Finally, applying two consecutive mappings must produce the same result as applying their composition. 
This means that container.map(f).map(g) must be the same as container.map(compose(g,f)).
```javascript
    // functor.map = Functor(a) ~> (a => b) => Functor(b)
```
Roughly speaking, a functor is some kind of container that allows us to apply map() to its contents, 
producing a new container of the same type, and if this sounds familiar, it's because you already know a functor:
arrays! When you apply map() to an array, the result is a new array containing
transformed (mapped) values.


