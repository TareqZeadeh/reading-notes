# ANIMATED CHARTS
## Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. 
## A great way to get started with charts is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.
### -Setting up: The first thing we need to do is download Chart.js. Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script: 
``` <!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <title>Chart.js demo</title>
        <script src='Chart.min.js'></script>
    </head>
    <body>
    </body>
</html>  
```
### -Drawing a line chart: To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart. So add this to the body of our HTML page:
``` 
<canvas id="buyers" width="600" height="400"></canvas> 
```
### -Next, we need to write a script that will retrieve the context of the canvas, so add this to the foot of your body element:
```
<script>
    var buyers = document.getElementById('buyers').getContext('2d');
    new Chart(buyers).Line(buyerData);
</script>
```


### -Inside the same script tags we need to create our data, in this instance it’s an object that contains labels for the base of our chart and datasets to describe the values on the chart. Add this immediately above the line that begins ‘var buyers=’:
```
var buyerData = {
	labels : ["January","February","March","April","May","June"],
	datasets : [
		{
			fillColor : "rgba(172,194,132,0.4)",
			strokeColor : "#ACC26D",
			pointColor : "#fff",
			pointStrokeColor : "#9DB86D",
			data : [203,156,99,251,305,247]
		}
	]
}
```
#### **for more information read this article on the Chart.js API. in  [SQUARESPACE](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/). site**

### -At first sight a (canvas) looks like the (img) element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the (canvas) element has only two attributes, width and height.
### -The id attribute isn't specific to the (canvas) element but is one of the global HTML attributes which can be applied to any HTML element (like class for instance).
### -Drawing shapes with canvas: You can drow shapes using canvas, just like 
#### Drawing rectangles:<canvas> only supports two primitive shapes: rectangles and paths (lists of points connected by lines). All other shapes must be created by combining one or more paths.
#### First let's look at the rectangle. There are three functions that draw rectangles on the canvas:
1. fillRect(x, y, width, height) Draws a filled rectangle.
2. strokeRect(x, y, width, height) Draws a rectangular outline.
3. clearRect(x, y, width, height) Clears the specified rectangular area, making it fully transparent. 
#### Rectangular shape example:
```  function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.fillRect(25, 25, 100, 100);
    ctx.clearRect(45, 45, 60, 60);
    ctx.strokeRect(50, 50, 50, 50);
  }
} 
 ```

#### **for more information read Drawing shapes with canvas in  [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes). site**

### -Applying styles and colors
#### Colors: Up until now we have only seen methods of the drawing context. If we want to apply colors to a shape, there are two important properties we can use: fillStyle and strokeStyle. 
1. fillStyle = color (Sets the style used when filling shapes).
2. strokeStyle = color (Sets the style for shapes' outlines.) 
#### The valid strings you can enter should, according to the specification, be CSS <color> values. Each of the following examples describe the same color.
```
// these all set the fillStyle to 'orange'

ctx.fillStyle = 'orange';
ctx.fillStyle = '#FFA500';
ctx.fillStyle = 'rgb(255, 165, 0)';
ctx.fillStyle = 'rgba(255, 165, 0, 1)';
```

#### A fillStyle example : we once again use two for loops to draw a grid of rectangles, each in a different color. The resulting image should look something like the screenshot. There is nothing too spectacular happening here. We use the two variables i and j to generate a unique RGB color for each square, and only modify the red and green values. The blue channel has a fixed value. By modifying the channels, you can generate all kinds of palettes. By increasing the steps, you can achieve something that looks like the color palettes Photoshop uses.
``` 
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  for (var i = 0; i < 6; i++) {
    for (var j = 0; j < 6; j++) {
      ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                       Math.floor(255 - 42.5 * j) + ', 0)';
      ctx.fillRect(j * 25, i * 25, 25, 25);
    }
  }
} 
 ```

#### **To see the result of the example and for more information read Applying styles and colors in  [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors). site**


### -Drawing text: The canvas rendering context provides two methods to render text:

1. fillText(text, x, y [, maxWidth])
Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
2. strokeText(text, x, y [, maxWidth])
Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

#### **for more information read Drawing text in  [MDN Web Docs](https://canvas.instructure.com/courses/2767664/assignments/21767068?module_item_id=45820439). site**