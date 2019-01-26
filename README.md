# Blueberry

This is a (very) small-scale programming language I created to learn more about how interpreted languages work.

As time goes on I will be working more on this project to create a transpiler to compile programs to JavaScript.

# Basic Syntax

Basically the only pre-defined data structures are numbers, strings and booleans. The only built-in function is print(str), which as you might imagine just prints a string or number to the console.

> helloWorld = func() {
>     print("Hello world!");   
> };
>
> helloworld();

The semicolon after the } is required. I'm actually not sure exactly why, but I'm working on it.

As a side note, named functions like "func helloWorld() {}" *should* work. But they don't. They don't get added to the environment for whatever reason. I'll find a fix for it eventually.

# Primitives

Essentially, primitives can be defined in the interpreter the same way you would create any JS function(with some exceptions due to things like working with the filesystem and such). The primitives currently implemented are:

**print(str)** 

Prints the value of str to the console. 

**require(filename)**

Requires another Blueberry script.

## How to add a primitive

As mentioned before, its almost the same process as defining a normal JS function, just with the added syntax for the global environment and CPS callstack.

> globalEnv.def("sum", function(callback, x, y) {
>     callback(x + y);
> });

Basically what we're doing is defining the function "sum" in the global environment and passing a JavaScript function as its body. Instead of returning the value of x + y, we must pass the expression to the callback(the callback being the caller of the function in this case), and that will essentially "return" the sum to the caller(such as a print call or an operator).