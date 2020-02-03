# February 8,2020
### Forms
- Adding text: Text input(single-line) used for a single line of text such as email addresses and names. Password input like a single line text box but it masks the characters entered. Text area(multi-line) for longer areas of text, such as messages and comments.
- A user fills in a form and then presses a button to submit the info to the server. A form may have several form controls, each gathering different info. The server needs to know which piece of inputted data corresponds with which form element. 
- < form > controlls live inside a form element. This element should always carry the action attribute andn will usually have a method and id attribute too.
- information from a form is sent in name/value pairs
- each form control is given a name, and the text the user types in or the values of the options they select are sent to the server.

### Lists, Tables, & Forms
- List markers can be given different appearances using the list-style type and list-style image properties.
- table cells can have different borders and spacing in different browsers, but there are properties you can us to control them and make them more consistent.
- Forms are easier to use if the form controls are vertially alignrf using CSS.
- Forms benefit from styles that make them feel mor interactive.

### Events
- When you browse the web, your browser registers different types of events. Its the browsers way of saying, hey this just happened. Your script can then respond to these events. Scripts often respond to these events by updating the content of the web page via the DOM which makes the page feel more interactive.
- Interactions create events. Events occur when users click or tap on a link, hover, or swipe over an element.
- Binding is the process of stating which event you are waiting to happen upon.
- When an event occurs on an element, it can trigger a JavaScript function. When this function then changes the web page in some way, it feels interactive because it has reponded to the user.
- You can use event delegation to monitor events that happen on all of the children of an element.
- The most commonly used events are w3w DOM events, although there are others in the html5 specification as well as browser-specific events.