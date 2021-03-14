# CHART JS
Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. They’re easier to look at and convey data quickly, but they’re not always easy to create.

A great way to get started with charts is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.

## Setting up
The first thing we need to do is download Chart.js. Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script:

![0](https://www13.0zz0.com/2021/03/14/22/590901566.png)

## Drawing a line chart

To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart. So add this to the body of our HTML page:

![1](https://www11.0zz0.com/2021/03/14/22/820158501.png)

Next, we need to write a script that will retrieve the context of the canvas, so add this to the foot of your body element:

![2](https://www11.0zz0.com/2021/03/14/22/243315459.png)

Inside the same script tags we need to create our data, in this instance it’s an object that contains labels for the base of our chart and datasets to describe the values on the chart. Add this immediately above the line that begins ‘var buyers=’:

![3](https://www11.0zz0.com/2021/03/14/22/542640349.png)


## Drawing a pie chart
Our line chart is complete, so let’s move on to our pie chart. First, we need the canvas element:

![4](https://www14.0zz0.com/2021/03/14/22/288155192.png)

Next, we need to get the context and to instantiate the chart:

![5](https://www14.0zz0.com/2021/03/14/22/723376358.png)


Next we need to create the data. This data is a little different to the line chart because the pie chart is simpler, we just need to supply a value and a color for each section:

![6](https://www14.0zz0.com/2021/03/14/22/720688028.png)

Now, immediately after the pieData we’ll add our options:

![7](https://www14.0zz0.com/2021/03/14/22/163615159.png)

These options do two things, first they remove the stroke from the segments, and then they animate the scale of the pie so that it zooms out from nothing.

# Basic usage of canvas

At first sight a < canvas > looks like the < img > element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the < canvas > element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. The element can be sized arbitrarily by CSS, but during rendering the image is scaled to fit its layout size: if the CSS sizing doesn't respect the ratio of the initial canvas, it will appear distorted.

The id attribute isn't specific to the < canvas > element but is one of the global HTML attributes which can be applied to any HTML element (like class for instance). It is always a good idea to supply an id because this makes it much easier to identify it in a script.

The < canvas > element can be styled just like any normal image (margin, border, background…). These rules, however, don't affect the actual drawing on the canvas. We'll see how this is done in a dedicated chapter of this tutorial. When no styling rules are applied to the canvas it will initially be fully transparent.

## What is HTML Canvas?
The HTML < canvas > element is used to draw graphics, on the fly, via JavaScript.

The < canvas>  element is only a container for graphics. You must use JavaScript to actually draw the graphics.

Canvas has several methods for drawing paths, boxes, circles, text, and adding images.

## Canvas Examples

A canvas is a rectangular area on an HTML page. By default, a canvas has no border and no content.
The markup looks like this:

![8](https://www14.0zz0.com/2021/03/14/22/546488110.png)

Here is an example of a basic, empty canvas:

![9](https://www13.0zz0.com/2021/03/14/23/716339632.png)

## Add a JavaScript
After creating the rectangular canvas area, you must add a JavaScript to do the drawing.
Here are some examples:

1. Draw a Line

![10](https://www10.0zz0.com/2021/03/14/23/347307401.png)

2. Draw a Circle

![10](https://www10.0zz0.com/2021/03/14/23/247222963.png)

3. Draw a Text

![11](https://www10.0zz0.com/2021/03/14/23/264041671.png)

4. Stroke Text

![12](https://www10.0zz0.com/2021/03/14/23/674717689.png)

5.Draw Linear Gradient

![13](https://www10.0zz0.com/2021/03/14/23/927670722.png)

6. Draw Circular Gradient

![14](https://www10.0zz0.com/2021/03/14/23/942862064.png)

7. Draw Image

![15](https://www10.0zz0.com/2021/03/14/23/224313426.png)


# References

> https://www.w3schools.com/html/html5_canvas.asp

> https://developer.mozilla.org/

>https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/

