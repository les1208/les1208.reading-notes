# January 28,2020

## Chapter Three: Object Literals
- objects group together a set of variables and functions to create a model of something. <br>
In an object: if a variable is part of an object, it is called a property. Properties tell us about the object, such as the name of a hotel or the number of rooms it has. <br>
In an object: if a function is part of an object, it is called a method. Methods represent tasks that are associated with the object. ex: you can check how many rooms are available by subtracying the number of booked rooms from total of rooms.
- Properties and methods have a name and a value. I an object have two keys with the same name. This is because keys are used to access their corresponding value. <br>
The value of a property can be a string, number, Boolean, array, or even another object. The value of a method is always a function. <br>

### Creating an object: Literal Notation
- Literal notation is the easiest and mot popular way to create objects. When setting properties, treat the values like you would do for variables: strings live in quotes and arrays live in square brackets. <br>

- You access the properties or methods of an object using dot notation. You can also access properties using square brackets.

- To access a property or method of an object you use the name of the object, followed by a period, then the name of the property or method you want to access. This is known as dot notation. <br>
The period is known as the member operator. The property or method on its right is a member of the object on its left. 

## Chapter Five: Document Object Model
- The document object model ( DOM ) specifies how browsers should create a model of an HTML page and how JS can access and update the contents of a web page while it is in the browser window. <br>
The DOM is neither part of HTML or JS; it is a seperate set of rules.
- The DOM specifies the way in which the browser should structure this model using a DOM tree. The DOM is called an object model because the model is the made of objects. <br>
The DOM also defines methods and properties to access and update each object in this model. 
- The DOM tree is a model of a web page and has four types of nodes: document, element, attribute and text nodes. <br>
As a browser loads a web page, it creates a model of that page. The model is called a DOM tree, and it is stored in the browsers memory. It consists of four main type of nodes.
- Every element, attribute, and piece of text in the HTML is represented by its own DOM NODE. 
- HTML elements describe the structure of an HTML page. 
- From an element node, you can access and update its content using properties such as textContent and innerHTML or using DOM manipulation techniques.
- An element node can contain multiple text nodes and child elements that are siblings of each other.
- Each node is an object with methods and properties. Scripts access and update this dom tree. Any changes made to the dom tree are reflected in the browser.

## Class Lecture 
- // template literals: `The sum of ${a} and ${b} is ${sum}.`;