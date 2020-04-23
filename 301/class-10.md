## Read: 10 - The Call Stack and Debugging


#### Understanding the JavaScript call stack

<!-- https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/ -->
- At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

Let’s break down our definition:
LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

- The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.


- Manage function invocation (call): The call stack maintains a record of the position of each stack frame. 
It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous. <br>

- Think of yourself standing on a queue, in a grocery store cash point. You can only be attended to after the person in front of you have been attended to. That’s synchronous. 

- In summary
The key takeaways from the call stack are:
1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.



#### JavaScript error messages && debugging
<!-- https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c -->
Types of error messages
- Reference errors
This is as simple as when you try to use a variable that is not yet declared you get this type os errors.
``` 
console.log(foo) // Uncaught ReferenceError: foo is not defined 
```
- Syntax errors
I know it’s in the name of the errors, but like it says itself, this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.
````
JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1
````
- Range errors
Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.
````
var foo= []
foo.length = foo.length -1 // Uncaught RangeError: Invalid array length 
````
An array for instance cannot have a negative length, why would you mess with the array length? Some people use it to set an array to empty.
- Type errors
Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.
```` 
var foo = {}
foo.bar // undefined
foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined
````
This is probably the most frequent error in JS, trying to access a property/method thinking that bar is of the type object when in reality, since it hasn’t been declared yet, it’s undefined which doesn’t have any baz available.
The fix is simple, just make sure that bar exists before trying to access it, either by creating bar or by checking for undefined.
 - Debugging
 To debug your JS code, the easiest and maybe the most common way its to simply console.log() the variables you want to check or, by using chrome developer tools, open your page with your JS code (press cmd+o in macOS or Ctrl+o in Windows) and choose your file to debug, click the line you wanna debug and refresh your page again (F5). <br>
If the line you selected was run you will be able to see what has happened before that point and you can try and evaluate the next lines to check if everything is outputting what you are expecting.



####  https://developer.mozilla.org/en-US/docs/Glossary/Call_stack 
- A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.