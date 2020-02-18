# February 18, 2020

### Docs For HTML
- canvas has only two attributes, width and height. They are optional and can be set up using DOM properties. With no width and height attributes specified, the canvas will initially be 300px wide and 150px height. <br>
- Element can be sized arbitrarily through CSS, but during rendering the img is scaled to fit its layout.
- The canvas element can be styled just like any normal img (margin, border, background, and etc.) <br>
The canvas element has a method called getContext used to obtain the rendering context its drawing functions. getContext takes one parameter, the type of context.

- The fillRect() function draws a large black square 100px on each side. The clearRect function then erases a 60x60px square from the center, and then strokeRect is called to create a rectangular outline 50x50px withing the cleared square.

- A path is a list of points, connected by segments of lines that can be of different shapes, curved, or not, of different width and of different color. A path or even a subpath can be closed. 
- To make shapes using paths, we take some extra steps. <br>
First, create the path. <br>
Then you use drawing commands to draw into the path <br>
Once the path has been created, you can stroke or fill the path to render it. <br>
Here are the functions used to perform these steps <br>
beginPatt(): creates a new path. Once created, future drawing commands are directed into the path and used to build the path up. <br>
Path methods: methods to set different paths for objects. <br>
closePath(): Adds a straight  line to the path, going to the start of the current sub-path. <br>
stroke(): Draws the shape by getting its outline. <br>
fill(): Draws a solid shape by filling the path's content area. <br>
The first step to create a path is to call the beginPath, every time this method is called, the list is reset and we can start drawing new shapes. Second step is calling the methods that actually specify the paths to be drawn. Third and optional step is to call closePath. This method tries to close the shape by drawing a straight line from the current point to the start.

- To draw straight lines use the lineTo() method. This method takes two arguments, x and y. Which are the coordinates of the lines end point

### Applying Styles and Colors
- There are two important properties we can use to apply colors: fillStyle and strokeStyle. <br>
fillStyle = color sets the style used when filling shapes.<br>
strokeStyle = color sets the style for shapes' outline
- Color is a string representing a CSS color 

### Line styles
- lineWidth = value sets the width of lines drawn in the future.
- lineCap = type Sets the appearance of the ends og lines.
- lineJoin = type Sets the appearace of the corners where lines meet. 
- miterLimit = value Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
- getLineDash() Returns the current line dash pattern array containing an even number of non-negative numbers.
- setLineDash(segments) Sets the current line dash pattern.
- lineDashOffset = value Specifies where to start a dash array on a line