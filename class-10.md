# February 11, 2020

### Error Handling & Debugging

- JS interpreter uses the concept of execution contexts. There is one global execution context; plus each function creates a new execution context. They correspond to variable scope.

- Execution context every statement in a script lives in one of three execution contexts: -global context (code that is in the script, but not in a funciton. There is only one global context in any page.)
- Function context- code that is being run within a function. Each function has its own function context.
- Eval Context- Text is executed like code in an internal function called eval() 

- Variable Scope, the first two execution contexts correspond with the notion of scope: -global scope: if a variable is declared outside a funciton, it can be used anywhere because it has global scope. If you do not use the var keyword when creating a variable, it is placed in global scope  -function-level scope: when a variable is declared within a function, it can only be used within that function. This is because it has funcition level scope.
- The Stack <br>
The JS interpreter processes one line of code at a time. When a statement needs data from another function, it stacks ((or piles)) the new function on top of the current task.<br>
When statement has to call some other code in order to do its job, the new task gors to the top of the pile of things to do. 
- Each time a script enters a new execution context, there are two phases of activuty: Preprare & Execute <br>
Prepare: The new scope is created -Variables, functions, and arguments are created. The value of the this keyword is determined. <br>
Execute: Now it can assign values to variables. Reference functions and run their code. Execute statements
- Debugging is the process of finding errors. It involves a process of deduction.
- JS has 7 different types of errors. Each creates its own object, which can tell you its line number and description of the error.


