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