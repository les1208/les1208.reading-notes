# February 4,2020
### Chapter 15 Layouts
- Css treates HTML element as if it is in its own box. This box will either be a block-level box or inline box. <br>
Block-level boxes start on a new line and acts as the main building blocks of any layouts, while inline boxes flow between surrounding text. You control how much space each box  takes up by setting the width of the boxes. To seperate boxes you can use borders,margins, padding, and background colors. <br>
 examples of block-level elements are h1, p, ul, li.
 - Inline elements flow in between surrounding text. examples img, b, i.
 - Containing elements <br>
 if one block-level element then the outer box is known as the containing or parent element. <br>
 It is common to group a number of elements together inside a div. A box may be nested inside several other block-level elements. The containing element is always the direct parent of that element. 
 ## CSS positioning schemes
 - css allows you to control the layout of the page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the position property. You can also use float elements using float property. <br>
<b> Normal flow: <b> Every block-level element appears on a new line, causing each item to appear lower down the oage than the previous one. Even if you specify width of the boxes and there is space for two elements to sit side by side, they will not appear next to each other.
<b>Relative Positioning: <b> This moves an element from th position it would be normal flow, shigting it to the top, right, bottom, or left of where is would have been places. This does not affect the position of surrounding elements; they stay in the position they would be in normal flow.
<b>Absolute Positioning:<b> This positions the element in relation to its containing element, it is taken out of normal flow, meaning that it does not affect the position of any surrounding elements( as they simply ignore the space it would have taken). Absolutely positioned elements move as users scroll up and down the page. 
- To indicate where a box should be positioned, you may also need to use box offset properties to tell the browser how far from the top or bottom and left or right it should be placed.
<b>Fixed Positioning:<b> This is a form of absolute positioning that positions the element in relation to the browseer window, as opposed to the containing element. Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user scrolls up or down the page. <br>
<b>Floating Elements:<b> Floating elements allows you to take that element out of normal flow and position it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.
- When you move any element from normal flow, boxes can overlap. The z index property allows you to control which box appears on top.
- Pages can be fixed width or liquid stretchy layouts.
- You can include multiple css files in one page.
