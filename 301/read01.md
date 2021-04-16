# Responsive Overview
Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop. Responsive web design is focused around providing an intuitive and gratifying experience for everyone. Desktop computer and cell phone users alike all benefit from responsive websites.

## Responsive vs. Adaptive vs. Mobile
For some the term responsive may not be new, and others might be even more acquainted with the terms adaptive or mobile. Which may leave you wondering what exactly is the difference between all of them.

Responsive and adaptive web design are closely related, and often transposed as one in the same. Responsive generally means to react quickly and positively to any change, while adaptive means to be easily modified for a new purpose or situation, such as change. With responsive design websites continually and fluidly change based on different factors, such as viewport width, while adaptive websites are built to a group of preset factors. A combination of the two is ideal, providing the perfect formula for functional websites. Which term is used specifically doesn’t make a huge difference.

Mobile, on the other hand, generally means to build a separate website commonly on a new domain solely for mobile users. While this does occasionally have its place, it normally isn’t a great idea. Mobile websites can be extremely light but they do come with the dependencies of a new code base and browser sniffing, all of which can become an obstacle for both developers and users.

Currently the most popular technique lies within responsive web design, favoring design that dynamically adapts to different browser and device viewports, changing layout and content along the way. This solution has the benefits of being all three, responsive, adaptive, and mobile.

## Relative Viewport Lengths
CSS3 introduced some new relative length units, specifically related to the viewport size of the browser or device. These new units include vw, vh, vmin, and vmax. Overall support for these new units isn’t great, but it is growing. In time they look to play a large roll in building responsive websites.

* vw : Viewports width
* vh : Viewports height
* vmin : Minimum of the viewport’s height and width
* vmax : Maximum of the viewport’s height and width


## Media Queries
Media queries were built as an extension to media types commonly found when targeting and including styles. Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example. Being able to apply uniquely targeted styles opens up a world of opportunity and leverage to responsive web design


## Initializing Media Queries

There are a couple different ways to use media queries, using the @media rule inside of an existing style sheet, importing a new style sheet using the @import rule, or by linking to a separate style sheet from within the HTML document. Generally speaking it is recommend to use the @media rule inside of an existing style sheet to avoid any additional HTTP requests.

![1](https://www7.0zz0.com/2021/04/16/22/532186256.png)

## Logical Operators in Media Queries

Logical operators in media queries help build powerful expressions. There are three different logical operators available for use within media queries, including and, not, and only.


1- Using the and logical operator within a media query allows an extra condition to be added, making sure that a browser or devices does both a, b, c, and so forth. Multiple individual media queries can be comma separated, acting as an unspoken or operator. The example below selects all media types between 800 and 1024 pixels wide.

![2](https://www9.0zz0.com/2021/04/16/22/520013641.png)

2- The not logical operator negates the query, specifying any query but the one identified. In the example below the expression applies to any device that does not have a color screen. Black and white or monochrome screens would apply here for example.

![3](https://www9.0zz0.com/2021/04/16/22/583816715.png)

3- The only logical operator is a new operator and is not recognized by user agents using the HTML4 algorithm, thus hiding the styles from devices or browsers that don’t support media queries. Below, the expression selects only screens in a portrait orientation that have a user agent capable of rending media queries.

![4](https://www9.0zz0.com/2021/04/16/22/960357137.png)


## Height & Width Media Features
One of the most common media features revolves around determining a height or width for a device or browser viewport. The height and width may be found by using the height and width media features. Each of these media features may then also be prefixed with the min or max qualifiers, building a feature such as min-width or max-width.

![5](https://www14.0zz0.com/2021/04/16/22/994279619.png)


## Orientation Media Feature
The orientation media feature determines if a device is in the landscape or portrait orientation. The landscape mode is triggered when the display is wider than taller, and the portrait mode is triggered when the display is taller than wider. This media feature plays a large part with mobile devices.


## Aspect Ratio Media Features
The aspect-ratio and device-aspect-ratio features specifies the width/height pixel ratio of the targeted rendering area or output device. The min and max prefixes are available to use with the different aspect ratio features, identifying a ratio above or below that of which is stated.

## Resolution Media Feature
The resolution media feature specifies the resolution of the output device in pixel density, also known as dots per inch or DPI. The resolution media feature does accept the min and max prefixes. Additionally, the resolution media feature will accept dots per pixel (1.3dppx), dots per centimeter (118dpcm), and other length based resolution values.

## Mobile First
One popular technique with using media queries is called mobile first. The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.

The operating belief behind mobile first design is that a user on a mobile device, commonly using a smaller viewport, shouldn’t have to load the styles for a desktop computer only to have them over written with mobile styles later. Doing so is a waste of bandwidth. Bandwidth that is precious to any users looking for a snappy website.

The mobile first approach also advocates designing with the constraints of a mobile user in mind. Before too long, the majority of Internet consumption will be done on a mobile device. Plan for them accordingly and develop intrinsic mobile experiences.

A breakout of mobile first media queries might look at bit like the following.

![6](https://www5.0zz0.com/2021/04/16/22/945742010.png)

Additionally, downloading unnecessary media assets can be stopped by using media queries. Generally speaking, avoiding CSS3 shadows, gradients, transforms, and animations within mobile styles isn’t a bad idea either. When used excessively, they cause heavy loading and can even reduce a device’s battery life.

![7](https://www5.0zz0.com/2021/04/16/22/920043301.png)

## Mobile First Demo

Adding media queries to our previous example, we overwrote a handful of styles in order to have a better layout on viewports under 420 pixels wide. Rewriting this code to use the mobile styles first by default then adding media queries to adjust for viewports over 420 pixels wide we build the following:

![8](https://www3.0zz0.com/2021/04/16/22/761868373.png)

## Viewport

Mobile devices generally do a pretty decent job of displaying websites these days. Sometimes they could use a little assistance though, particularly around identifying the viewport size, scale, and resolution of a website. To remedy this, Apple invented the viewport meta tag.

![9](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/without-viewport.png)


## Viewport Height & Width

Using the viewport meta tag with either the height or width values will define the height or width of the viewport respectively. Each value accepts either a positive integer or keyword. For the height property the keyword device-height value is accepted, and for the width property the keyword device-width is accepted. Using these keywords will inherit the device’s default height and width value

![10](https://www3.0zz0.com/2021/04/16/22/356510624.png)

![11](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/with-viewport.png)

## Combining Viewport Values

The viewport meta tag will accept individual values as well as multiple values, allowing multiple viewport properties to be set at once. Setting multiple values requires comma separating them within the content attribute value. One of the recommended viewport values is outlined below, using both the width and initial-scale properties.

![12](https://www13.0zz0.com/2021/04/16/22/974187629.png)

![13](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/with-viewport.png)


# Floats

## What is “Float”?

Float is a CSS positioning property. To understand its purpose and origin, we can look to print design. In a print layout, images may be set into the page such that text wraps around them as needed. This is commonly and appropriately called “text wrap”. Here is an example of that.

![14](https://css-tricks.com/wp-content/uploads/2021/03/web-text-wrap.png)

There are four valid values for the float property. Left and Right float elements those directions respectively. None (the default) ensures the element will not float and Inherit which will assume the float value from that elements parent element.

## What are floats used for?
Aside from the simple example of wrapping text around images, floats can be used to create entire web layouts.

![15](https://css-tricks.com/wp-content/uploads/2021/03/web-layout.png)

## Clearing the Float

Float’s sister property is clear. An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float. Again an illustration probably does more good than words do.

![16](https://css-tricks.com/wp-content/uploads/2021/03/unclearedfooter.png)

In the above example, the sidebar is floated to the right and is shorter than the main content area. The footer then is required to jump up into that available space as is required by the float. To fix this problem, the footer can be cleared to ensure it stays beneath both floated columns.

![17](https://css-tricks.com/wp-content/uploads/2021/03/clearedfooter.png)

Clear has four valid values as well. Both is most commonly used, which clears floats coming from either direction. Left and Right can be used to only clear the float from one direction respectively. None is the default, which is typically unnecessary unless removing a clear value from a cascade. Inherit would be the fifth, but is strangely not supported in Internet Explorer. Clearing only the left or right float, while less commonly seen in the wild, definitely has its uses.

![18](https://css-tricks.com/wp-content/uploads/2021/03/directionalclearing.png)

## The Great Collapse

One of the more bewildering things about working with floats is how they can affect the element that contains them (their “parent” element). If this parent element contained nothing but floated elements, the height of it would literally collapse to nothing. This isn’t always obvious if the parent doesn’t contain any visually noticeable background, but it is important to be aware of.

![19](https://css-tricks.com/wp-content/uploads/2021/03/collapse.png)

As anti-intuitive as collapsing seems to be, the alternative is worse. Consider this scenario:

![20](https://css-tricks.com/wp-content/uploads/2021/03/whywecollapse.png)

## Techniques for Clearing Floats 

 you are in a situation where you always know what the succeeding element is going to be, you can apply the clear: both; value to that element and go about your business.


 # References

> https://learn.shayhowe.com/advanced-html-css/responsive-web-design/

> https://css-tricks.com/all-about-floats/