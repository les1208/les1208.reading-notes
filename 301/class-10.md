## Read: 10 - The Call Stack and Debugging


#### Understanding the JavaScript call stack

<!-- https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/ -->
- At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

Let’s break down our definition:
LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

- The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.


```
 // Manage function invocation (call): The call stack maintains a record of the position of each stack frame. 
 // It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous. <br>

// Think of yourself standing on a queue, in a grocery store cash point. You can only be attended to after the person in front of you have been attended to. That’s synchronous. <br>

// This is what we mean by “manage function invocation”.
``` 







<!-- https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c -->








<!-- https://developer.mozilla.org/en-US/docs/Glossary/Call_stack -->