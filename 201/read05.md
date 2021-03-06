# Images
A picture can say a thousand words, and great
images help make the difference between an
average-looking site and a really engaging one.

## Storing Images on Your Site
If you are building a site from scratch, it is good
practice to create a folder for all of the images
the site uses.

## Adding Images

* < img > 

chapter-05/adding-images.html HTML
To add an image into the page
you need to use an <img>
element. This is an empty
element (which means there is
no closing tag). It must carry the
following two attributes:
1. src 

This tells the browser where
it can find the image file. This
will usually be a relative URL
pointing to an image on your
own site.

2. alt

This provides a text description
of the image which describes the
image if you cannot see it.

* title

You can also use the title
attribute with the <img> element
to provide additional information
about the image. Most browsers
will display the content of this
attribute in a tootip when the
user hovers over the image.

![1](https://www12.0zz0.com/2021/03/06/14/455769491.png)

## Height & Width of Images

* height

This specifies the height of the
image in pixels.

* width

This specifies the width of the
image in pixels.

![2](https://www5.0zz0.com/2021/03/06/14/320821604.png)


## Where to Place Images in Your Code

1. before a paragraph
The paragraph starts on a new
line after the image.
2. inside the start of a
paragraph
The first row of text aligns with
the bottom of the image.
3. in the middle of a
paragraph
The image is placed between the
words of the paragraph that it
appears in.

![3](https://www7.0zz0.com/2021/03/06/14/773611942.png)

![4](https://www10.0zz0.com/2021/03/06/14/549541393.png)

## Aligning Images Horizontally

The align attribute was
commonly used to indicate how
the other parts of a page should
flow around an image. It has
been removed from HTML5
and new websites should use
CSS to control the alignment of
images

![5](https://www8.0zz0.com/2021/03/06/14/971577049.png)
![6](https://www8.0zz0.com/2021/03/06/14/373173559.png)

## Aligning Images Vertically
1. top :
This aligns the first line of the
surrounding text with the top of
the image.
2. middle :
This aligns the first line of the
surrounding text with the middle
of the image.
3. bottom :
This aligns the first line of the
surrounding text with the bottom
of the image.

![7](https://www10.0zz0.com/2021/03/06/14/160375891.png)
![8](https://www10.0zz0.com/2021/03/06/14/423730553.png)

## Three Rules for Creating Images

1. Save images in the right format

2. Save images at the right size

3. Use the correct resolution

# Color
## Foreground Color 
The color property allows you
to specify the color of text inside
an element. You can specify any
color in CSS in one of three ways:

1. RGB Values 

These express colors in terms
of how much red, green and
blue are used to make it up. For
example: rgb(100,100,90)

2. HEX Codes

These are six-digit codes that
represent the amount of red,
green and blue in a color,
preceded by a pound or hash #
sign. For example: #ee3e80

3. Color Names

There are 147 predefined color
names that are recognized
by browsers. For example:
DarkCyan

![9](https://www4.0zz0.com/2021/03/06/14/927631897.png)

## Background Color

CSS treats each HTML element
as if it appears in a box, and the
background-color property
sets the color of the background
for that box.
You can specify your choice of
background color in the same
three ways you can specify
foreground colors: RGB values,
hex codes, and color names,
If you do not specify a
background color, then the
background is transparent.
By default, most browser
windows have a white
background, but browser users
can set a background color for
their windows, so if you want
to be sure that the background
is white you can use the
background-color property on
the < body > element.

![10](https://www4.0zz0.com/2021/03/06/14/819943402.png)

## Contrast
When picking foreground and background
colors, it is important to ensure that there is
enough contrast for the text to be legible.

Text is harder to read when
there is low contrast between
background and foreground
colors. 

Text is easier to read when
there is higher contrast between
background and foreground
colors.

If you want people to read a lot
of text on your page, however,
then too much contrast can
make it harder to read, too.

You can reduce contrast by
using dark gray text on a white
background or an off-white text
on a dark background.

# Text
## Typeface Terminology
![11](https://www7.0zz0.com/2021/03/06/15/571496615.png)

## Size of Type

The font-size property enables
you to specify a size for the
font. There are several ways to
specify the size of a font. The
most common are:

1. pixels

Pixels are commonly used
because they allow web
designers very precise control
over how much space their text
takes up. The number of pixels is
followed by the letters px.

2. percentages

The default size of text in
browsers is 16px. So a size of
75% would be the equivalent of
12px, and 200% would be 32px.

3. ems

An em is equivalent to the width
of a letter m.

![12](https://www9.0zz0.com/2021/03/06/15/512116613.png)

## Bold 
The font-weight property
allows you to create bold text.
There are two values that this
property commonly takes:

1. normal :
This causes text to appear at a
normal weight.
2. bold : This causes text to appear bold.

![13](https://www4.0zz0.com/2021/03/06/15/162517830.png)

## Italic
If you want to create italic text,
you can use the font-style
property. There are three values
this property can take:

1. normal : This causes text to appear in a
normal style (as opposed to italic
or oblique).
2. italic : This causes text to appear italic.

3. oblique : This causes text to appear
oblique.

## UpperCase & LowerCase

1. uppercase : This causes the text to appear
uppercase.
2. lowercase : This causes the text to appear
lowercase.
3. capitalize : This causes the first letter of
each word to appear capitalized

## Underline & Article
The text-decoration property
allows you to specify the
following values:

1. none : This removes any decoration
already applied to the text.
2. underline : This adds a line underneath the
text.
3. overline : This adds a line over the top of
the text.
4. line-through : This adds a line through words
5. blink :This animates the text to make it
flash on and off

# JPEG vs PNG vs GIF 
## which image format to use and when?

## TL;DR
Use JPEG format for all images that contain a natural scene or photograph where variation in colour and intensity is smooth. Use PNG format for any image that needs transparency or for images with text & objects with sharp contrast edges like logos. Use GIF format for images that contain animations.

## Compression 
Almost all forms of data that we see on the internet — text, image, video etc. — are compressed to reduce the size of data and ensure faster transmission. Choosing the correct format and compression is a major factor that determines image size.

1. JPEG 

 is a lossy compression specification that takes advantage of human perception. It can achieve compression ratios of 1:10 without any perceivable difference in quality. Beyond this, the compression artefacts become more prominent. Because JPEG compression works by averaging out colours of nearby pixels , JPEG images are best suited for photographs and paintings of natural scenes where the variations in colour and intensity are smooth. However, if an image contains text or lines, where a sharp contrast between adjacent pixels is desired to highlight the proper shape, this lossy compression technique does not yield good results.

 2. PNG 

 is a lossless image format using DEFLATE compression. No data is lost during compression and no compression artefacts are introduced in the image. For this reason, a PNG image would retain higher quality than an image than JPEG and would look a lot sharper, it would also occupy more space on the disk. This makes it unsuitable for storing or transferring high-resolution digital photographs but a great choice for images with text, logos and shapes with sharp edges.

 3. GIF  
 is also a lossless image format that uses LZW compression algorithm. It was favoured over PNG for simple graphics in websites in its early days because the support of PNG was still growing. Given that PNG is now supported across all major devices and that PNG compression is about 5–25% better than GIF compression, GIF images are now mainly used only if the image contains animations.

 ## Transparency
 In a simple form, transparency indicates something that is completely invisible. Logos and icons often need to be placed on backgrounds with variable colours. Hence it is desirable, that the background of these logos and icons is made transparent so that a single image can be used over multiple background variations.

 1. JPEG

 images don’t support transparency and are hence not usable for such cases.

 2. PNG 

 images support transparency in two ways — inserting an alpha channel that allows partial transparency or by declaring a single colour as transparent. Partial transparency makes the edges blend smoothly into the background. PNG8 images can support only index transparency whereas PNG24 images can support alpha channel transparency.

 3. GIF 

 images support transparency by declaring a single colour in the colour palette as transparent. Because of absence of partial transparency, the edges get a poor jagged effect. Though this can be solved to some extent using dithering, with improved PNG support, GIF is unsuitable for images with transparent backgrounds.

 ## Colours
 There is a significant difference in the number of colours that can be supported by these 3 formats.

 JPEG images can support around 16 million colours. This is what makes them suitable for storing images of natural scenes.


NG images mainly have two modes — PNG8 and PNG24. PNG8 can support upto 256 colours whereas PNG24 can handle upto 16 million colours like a JPEG image. Use PNG8 for simple shapes with fewer colours and PNG24 for high quality, complex logos and shapes with rounded corners on a transparent background.

GIF images are limited to 256 colours. If index transparency is used, then one of these 256 colours is assigned as transparent and the remaining 255 are used for other colours.

## Animation

Animation, in this case, refers to any change or movement in the image. It doesn’t necessarily have to have frame rates like an animated video, but essentially a part or the entire image changes with time.

Of these 3 formats, only GIF supports animation. This capability makes GIF format suitable for delivering engaging ads and banners. Of late, with the advent of companies Tumblr, 9Gag, Giphy etc. the use of GIF format for memes has picked up.

# References

> HTML & CSS
Design and Build Websites
Jon Ducket

> from https://blog.imagekit.io/jpeg-vs-png-vs-gif-which-image-format-to-use-and-when-c8913ae3e01d
