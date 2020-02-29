## Class 201 Reading Notes

### This is where my reading/notes for class 201 will be.

- https://learn.shayhowe.com/advanced-html-css/css-transforms/
- https://learn.shayhowe.com/advanced-html-css/transitions-animations/
- https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users/
- https://codepen.io/retyui/pen/ByoaXV
- https://codepen.io/akshaychauhan/pen/oAfae
- https://codepen.io/kieranfivestars/pen/MYdQxX
- https://codepen.io/dp_lewis/pen/gCfBv

- 1/11 Introductory HTML and JavaScript

- 1/14 
# HTML Text, CSS Introduction, and Basic JavaScript Instructions
**Headings**
- h1 is for main headings
- h2 is a subheadings
- anything after thar it's h3 up until h6 (which is the smallest)
- < b > element can make characters appear bold
- < i > element makes them appear italic
> < sup > element is used to contain characters that should be superscript.
- CSS works by associating rules with HTML elements. 
A CSS rule contains two parts: a selector and a declaration.
- CSS declarations sit inside curly brackets and each is made up of two parts: a property and a value, seperated by a colon. 
<<<<<<< HEAD
=======

- 1/18
# Read: 03 - HTML Lists, CSS Boxes, JS Control Flow
### Lists
- Ordered lists are list where each item in the list is numbered. < ol > element
- Unoredred lists are list that begin with a bulled point.
- Definition lists are made up of a set of terms along with the definitons for each of those terms. Inside the < dl > element you will usually see pairs of < dt > and < dd > elements. < dt > is used to cotain the term being defined (the definiton term). < dd > this is used to contain the definiton.
- Each item in the list is placed between an opening < li > tag and a closing tag.
- Lists can be nested inside one another.
### Boxes
- The most popular way to specify the size of a bx are to use pixels, percentages, or ems. When you use percentages the size of the box is relative to size of browser window or, if the box is encased within another box, it is . percentage of the size of the containing box.
- Every box has three available properties that can be adjusted to control its appearance: * Border: every box has a border. The border seperated the edge of one box from another.
* Margin: Margins sit outside the edge of the border. You can set the width of a margin to create a gap between the borders of two adjacent boxes.
* Padding: padding is the space between the border of a box and any content contained within it. Adding padding can increase the readability of its contents.
- Border-width propert is used to cotrol the width of a border. The value of this property can either be given in pixels or using one of the following values: thin, medium, thick
-You can control the individual size of borders using four seperate properties: top-width, right-width, bottom-width, and left-width.
- Block-level boxes can be made into inline boxes, and inline boxes made into block-level boxes.
### Decisions & Loops
- Conditional statements allow your code to make decisions about what to do next.
- All values evaluate to either truthy or falsy.
- There are three types of loop: for, while, and do...while. Each repeats a set of statements.

# Janurary 21, 2020
## Links
- Links are created using the < a > element. You specify which page you wanted to link to using the href attribute. The text between < a > tag and closing is known as the link text.
- URL stands for uniform resource locator. When linking to other pages within your site, you don't need to speciify the domain name. If all pages of the site are in the same folder, then the value of the href attribute is just name of the file.
- You can create linka to open email programs with an email address in the "to" field.

## Layouts
- CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or inline box. Block level boxes start on a new line and act as the main building blocks of ay layout, while inline boxes flow between surrounding text.
- Block level elements start on a new line < h1 > < p > < ul > < li >
- Inline elements flow in between surrounding text < img > < b > < i >
- < div > elements are often used as containing elements to group together sections of a page.
- Browsers display pages in normal flow unless you specify relative, absolute, or fixed positioning. 
- The float property moves content to the left or right of the page and can be used to create multi-column layouts. Designers keep pages within 960-1000 pixels wide, and indicate what the site is about within the top 600 pixels.
- Grids help create professional and flexible designs.

## Functions, Methods, and Objects
- Functions consist of a series of statements that have been grouped together because they perform a specific task. A method is the same as a function, except methods are created inside (and are part of) an object.
- Objects are made up of properties and methods.

# January 25, 2020
## Images

- < img > element is used to add images to a web page and it must carry the two following attributes: 
src tells the browser where it can find the image file. 
- alt  provides a text description of the image which describes the image if you cannot see it. 
You can use title attribute with img element to provide additional information about image. 
- img element will also use two other attributes that specify the size: height and width which specify size in pixels.
- Where you place the img in the code is important because browsers show HTML elements in on of two ways: 
- block elements always appear on a new line. ex: h1 and p elements.
- inline elements sit within a block level element and do not start on a new line. ex: b, em, and img elements.
- three rules to remember when you are creating images. Save images in the right format, save images at the right size, and use the correct resolution.
- Photographs are best saved as JPEGs.

## Color

- You can specify color in CSS one of three ways:
RGB values, hex codes, and color names. 
- When picking foreground and background colors, ensure that there is enough contrast for text to be legible.
-CSS3 has introduces an extra value for RGB colors to indicate opacity, known as RGBA.

## Text

- The font family property allows you to specify the typeface that should be used for any text inside the element(s) to which a CSS rule applies. 
- The font size property enables you to specify a size for the font.
- You can control the space between lines of text, individual letters, and words, text can also be aligned to the left, right, and center, or justified. It can also be indented. 
- You can use pseudo-classes to change the style of an element when a user hovers over.
