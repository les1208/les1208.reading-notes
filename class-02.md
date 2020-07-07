## Read: Unit Tests & Documentation

#### Unit Testing Best Practices 
- Unit tests isolate and exercise specific units of your code.
- In C#, you can think of a unit as a method.  You thus write a unit test by writing something that tests a method.  Oh, and it tests something specific about that method in isolation.
- you should shoot for one assert per test method.
- Think of reading the output of the test in the test runner.  If you assert 20 things, you still only see a single failure.
- Each test should handle its own setup and tear down.  The test runner will execute your stuff in whatever order it pleases and, depending on the specific runner you use (advanced topic), it might even execute them in parallel.
- Resist the impulse to abstract test setup (the “arrange”) to other classes, and especially resist the impulse to abstract it into a base class.
- Tests carry a maintenance weight, just like production code.  You thus want to avoid unwieldy tests like the plague — they’ll break and make you and everyone else hate them.  So instead of going nuts on the setup, take a critical look at your design.
#### xUnit Documentation
- xUnit.net is a free, open source, community-focused unit testing tool for the .NET Framework.
- Unit testing ofr C#, F#, VB.NET
- It works with ReSharper, CodeRush, TestDriven.NET and Xamarin
-It is part of the .NET Foundation
- Create the unit test project: An xUnit.net test project for .NET Core, just like other xUnit.net test projects for .NET, starts with a class library. From the command line, create a folder for your test project, change into it, and then create the project:
#### Art of README
- A README is a module consumer's first -- and maybe only -- look into your creation. The consumer wants a module to fulfill their need, so you must explain exactly what need your module fills, and how effectively it does so.

- Your job is to

* tell them what it is (with context)
* show them what it looks like in action
* show them how they use it
* tell them any other relevant details
- This is your job. It's up to the module creator to prove that their work is a shining gem in the sea of slipshod modules. Since so many developers' eyes will find their way to your README before anything else, quality here is your public-facing measure of your work.

` Your documentation is complete when someone can use your module without ever having to look at its code. This is very important. This makes it possible for you to separate your module's documented interface from its internal implementation (guts). This is good because it means that you are free to change the module's internals as long as the interface remains the same.
`

> Remember: the documentation, not the code, defines what a module does. -- Ken Williams