## Read: 03 - Flexbox and Templating
- Javascript templating is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. The template is HTML markup, with added templating tags that will either insert variables or run programming logic.

### Mustache 
<!-- https://github.com/janl/mustache.js -->
- Mustache is a logic-less template syntax. It can be used for HTML, config files, source code — anything. It works by expanding tags in a template using values provided in a hash or object.
<!-- Mustache.render(“Hello, {{name}}”, { name: “Sherlynn” });
// returns: Hello, Sherlynn -->
 {{ name }}. This is Mustache syntax to show that it is a placeholder. 
 it will look for the ‘name’ property in the object we pass in, and replace {{ name }} with the actual value, e,g, “Sherlynn”

 ### Flexbox
 <!-- https://www.w3.org/TR/css-flexbox/ -->
 - The Flexbox Layout (Flexible Box) module (a W3C Candidate Recommendation as of October 2017) aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and/or dynamic (thus the word "flex").
 Items will be laid out following either the main axis (from main-start to main-end) or the cross axis (from cross-start to cross-end).

* main axis - The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the flex-direction property (see below).
* main-start | main-end - The flex items are placed within the container starting from main-start and going to main-end.
* main size - A flex item's width or height, whichever is in the main dimension, is the item's main size. The flex item's main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
* cross axis - The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
* cross-start | cross-end - Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
* cross size - The width or height of a flex item, whichever is in the cross dimension, is the item's cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension. <br>
<b>flex-start:<b> Items align to the left side of the container.
<b>flex-end:<b> Items align to the right side of the container.
<b>center:<b> Items align at the center of the container.
<b>space-between:<b> Items display with equal spacing between them.
<b>space-around:<b> Items display with equal spacing around them.