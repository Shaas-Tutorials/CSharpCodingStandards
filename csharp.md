[Back](README.md)

# C# Guidelines

These are guidelines for C# language constructs.

* Favor higher-order parallel constructs over lower-order ones. For example, use capability in the `System.Threading.Tasks` namespace and `await`/`async` constructs when possible rather than using mutexes, semaphores, and other low-level locking mechanisms.
* Do not use `var` for variable declarations when the type is obvious. Save `var` for LINQ queries where the return type of a given expression is complicated and non-obvious.

It is acceptable to start to use these somewhat newer C# language features

* async/await
* Auto-property enhancements including read-only and initializers
* String interpolation
* Out variables
* Is-expressions with patterns
* Tuples
* Expression bodied class members
* Null-conditional operators
* Exception filters
* nameof()

Be wary of using the following:

* Ref returns


See the following for details on new language features:

* [What's New in C# 6.0](https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-6)
* [What's New in C# 7.0](https://blogs.msdn.microsoft.com/dotnet/2016/08/24/whats-new-in-csharp-7-0/)
