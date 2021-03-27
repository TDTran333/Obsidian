Link: [Stackoverflow](https://stackoverflow.com/questions/11653127/what-does-the-function-invisible-do)

While invisible() makes its content temporary invisible and is often used instead of return() it should rather be used in combination with return() and not as its replacement.

While return() will stop function execution and return the value put into it, invisible() will do no such thing. It only makes its content invisible for a while.

invisible()'s use cases are e.g. to prevent function return values that would produce page after page of output or when a function is called for its side effect and the return value is e.g. only used to give further information 

R prints a lot of stuff implicitly. I would consider such printing a side effect and that invisible() makes it not do that.