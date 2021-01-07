CPS will help us to avoid an important recursion restriction.
callback provides the called function with the way to continue the process, hence the word continuation. <br >
If we simply allowed a function to throw  an error, it would be an implied return to the caller, and we don't want this. 
The way out of this is to provide an alternative callback (that is, a different continuation) to be used
```javascript
function doSomething(a, b, c, normalContinuation, errorContinuation) {
    let r = 0;
    // ... do some calculations involving a, b, and c,
    // and store the result in r
    // if an error happens, invoke:
    // errorContinuation("description of the error")
    // otherwise, invoke:
    // normalContinuation(r)
}
```
Using CPS can even allow you to go beyond the control structures that JavaScript provides,
but that would be beyond the objectives of this book, so I'll let you research that on your
own!