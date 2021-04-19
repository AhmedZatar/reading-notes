# Templating with Mustache

## Javascript Templating
Javascript templating is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. The template is HTML markup, with added templating tags that will either insert variables or run programming logic.

The template engine then replaces variables and instances declared in a template file with actual values at runtime, and convert the template into an HTML file sent to the client.

## Mustache

![1](https://miro.medium.com/max/700/1*P9q0tkeaRY2l1JOXaVKAig.png)

Mustache is a logic-less template syntax. It can be used for HTML, config files, source code — anything. It works by expanding tags in a template using values provided in a hash or object.

It is often referred to as “logic-less” because there are no if statements, else clauses, or for loops. Instead, there are only tags. Some tags are replaced with a value, some nothing, and others a series of values.

mustache.js is an implementation of the mustache template system in JavaScript. It is often considered the base for JavaScript templating. And, since mustache supports various languages, we don’t need a separate templating system on the server side.

![2](https://www4.0zz0.com/2021/04/19/22/564361874.png)

In the above, we see two braces around {{ name }}. This is Mustache syntax to show that it is a placeholder. When Mustache compiles this, it will look for the ‘name’ property in the object we pass in, and replace {{ name }} with the actual value, e,g, “Sherlynn”.

![2](https://miro.medium.com/max/700/1*LbqYj87xlazySm6wE0Q2lA.png)

## Mustache-Express
mustache-express. Mustache Express lets you use Mustache and Express together easily.
To install:

* With Yarn:
$ yarn add mustache-express

* with NPM: $ npm install mustache --save

Configure mustache-express in your server.js/app.js/index.js file:

![3](https://miro.medium.com/max/700/1*ES10lxr7tdRFVEKcRAgLEw.png)

Create a views folder and add some html view templates (e.g. hello.html):

![4](https://miro.medium.com/max/494/1*zwYE8a5rvAVZcBl9v1oqfA.png)

![5](https://miro.medium.com/max/700/1*FRcL9NQHI7Cvi2ELLmzJGQ.png)

Then in the router configuration, use res.render(TEMPLATE_NAME, JSON_DATA). Example:

>res.render('hello', {"name": "Sherlynn"})


Whereby the first parameter ‘hello’ refers to the hello.html file (no need to include the extension (e.g. hello.html) as it has been previously set as html.

The second parameter would be the JSON data itself. We can also pass in a variable representing the data, for example:

>var nameObject = {"name": "Sherlynn"}
res.render('hello', nameObject)

Final output:

![6](https://miro.medium.com/max/700/1*YaJ1vtsuwRMhfi8parlHOA.png)

# Flexbox

## Properties for the Parent (flex container)

![7](https://css-tricks.com/wp-content/uploads/2018/10/01-container.svg)

### display
This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

>.container {
  display: flex; /* or inline-flex */
}

### flex-direction

![8](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.
>.container {
  flex-direction: row | row-reverse | column | column-reverse;
}

* row (default): left to right in ltr; right to left in rtl
* row-reverse: right to left in ltr; left to right in rtl
* column: same as row but top to bottom
* column-reverse: same as row-reverse but bottom to top

### flex-wrap

![9](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

> .container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}

* nowrap (default): all flex items will be on one line
* wrap: flex items will wrap onto multiple lines, from top to bottom.
* wrap-reverse: flex items will wrap onto multiple lines from bottom to top.

## Properties for the Children (flex items)

![10](https://css-tricks.com/wp-content/uploads/2018/10/02-items.svg)

### order

![11](https://css-tricks.com/wp-content/uploads/2018/10/order.svg)

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

> .item {
  order: 5; /* default is 0 */
}

### flex-grow

![12](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least)

> .item {
  flex-grow: 4; /* default 0 */
}

### flex-shrink
> .item {
  flex-shrink: 3; /* default 1 */
}

This defines the ability for a flex item to shrink if necessary.