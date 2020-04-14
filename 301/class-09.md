## Read: 09 - Refactoring
<!-- https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa -->

## Functional Programming Concepts
- What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia
- Pure functions 
Here is a very strict definition of purity:
It returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects
- If our function reads external files, it’s not a pure function — the file’s contents can change.
- Random number generation
Any function that relies on a random number generator cannot be pure.
- It does not cause any observable side effects
Examples of observable side effects include modifying a global object or a parameter passed by reference.
- Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.
#### Immutability
- When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.
In Javascript we commonly use the for loop. This next for statement has some mutable variables.
- toLowerCase: converts the string to all lower case
- trim: removes whitespace from both ends of a string
- split and join: replaces all instances of match with replacement in a given string
We combine all these 4 functions and we can "slugify" our string.
#### Referential transparency
- Basically, if a function consistently yields the same result for the same input, it is referentially transparent.
pure functions + immutable data = referential transparency
With this concept, a cool thing we can do is to memoize the function. Imagine we have this function:
#### Functions as first-class entities
- The idea of functions as first-class entities is that functions are also treated as values and used as data.
Functions as first-class entities can:
refer to it from constants and variables
pass it as a parameter to other functions
return it as result from other functions
The idea is to treat functions as values and pass functions like data. This way we can combine different functions to create new functions with new behavior.
#### Higher-order functions
- When we talk about higher-order functions, we mean a function that either:
takes one or more functions as arguments, or
returns a function as its result
The doubleOperator function we implemented above is a higher-order function because it takes an operator function as an argument and uses it.
You’ve probably already heard about filter, map, and reduce. Let's take a look at these.
#### Filter
Given a collection, we want to filter by an attribute. The filter function expects a true or false value to determine if the element should or should not be included in the result collection. Basically, if the callback expression is true, the filter function will include the element in the result collection. Otherwise, it will not.
A simple example is when we have a collection of integers and we want only the even numbers.
Imperative approach
An imperative way to do it with Javascript is to:
create an empty array evenNumbers
iterate over the numbers array
push the even numbers to the evenNumbers array
#### Map
The idea of map is to transform a collection.
The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.
Let’s get the same people collection above. We don't want to filter by “over age” now. We just want a list of strings, something like TK is 26 years old. So the final string might be :name is :age years old where :name and :age are attributes from each element in the people collection.
#### Reduce
The idea of reduce is to receive a function and a collection, and return a value created by combining the items.
A common example people talk about is to get the total amount of an order. Imagine you were at a shopping website. You’ve added Product 1, Product 2, Product 3, and Product 4 to your shopping cart (order). Now we want to calculate the total amount of the shopping cart.
In imperative way, we would iterate the order list and sum each product amount to the total amount.

- 