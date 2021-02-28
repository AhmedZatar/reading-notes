# Text
When creating a web page, you add tags
(known as markup) to the contents of the
page. These tags provide extra meaning
and allow browsers to show users the
appropriate structure for the page.

## Headings
HTML has six "levels" of
headings:
< h1 > is used for main headings
< h2 > is used for subheadings
If there are further sections
under the subheadings then the
< h3 > element is used, and so
on...
![1](https://www7.0zz0.com/2021/02/28/23/958550815.png)

## Paragraphs
To create a paragraph, surround
the words that make up the
paragraph with an opening < p >
tag and closing < /p > tag.

## Bold & Italic
< b > By enclosing words in the tags
< b > and < /b > we can make
characters appear bold.

By enclosing words in the tags
< i > and < /i > we can make
characters appear italic


## Superscript & Subscrip
The < sup > element is used
to contain characters that
should be superscript such
as the suffixes of dates or
mathematical concepts like
raising a number to a power 

 The < sub > element is used to
contain characters that should
be subscript. It is commonly
used with foot notes or chemical
formulas
![2](https://www11.0zz0.com/2021/02/28/23/712240617.png)

## Line Breaks & Horizontal Rules
As you have already seen, the
browser will automatically show
each new paragraph or heading
on a new line. But if you wanted
to add a line break inside the
middle of a paragraph you can
use the line break tag < br />.

To create a break between
themes — such as a change of
topic in a book or a new scene
in a play — you can add a
horizontal rule between sections
using the < hr /> tag.

![3](https://www10.0zz0.com/2021/02/28/23/171662241.png)

## Strong & Emphasis
The use of the < strong >
element indicates that its
content has strong importance.
For example, the words
contained in this element might
be said with strong emphasis.
By default, browsers will show
the contents of a < strong >
element in bold.

The < em > element indicates
emphasis that subtly changes
the meaning of a sentence.
By default browsers will show
the contents of an < em > element
in italic

## Quotations
The < q > element is used for
shorter quotes that sit within
a paragraph. Browsers are
supposed to put quotes around
the < q > element, however
Internet Explorer does not —
therefore many people avoid
using the < q > element.

## Abbreviations & Acronyms
If you use an abbreviation or
an acronym, then the < abbr >
element can be used. A title
attribute on the opening tag is
used to specify the full term.
![4](https://www3.0zz0.com/2021/02/28/23/730888365.png)

## Changes to Content
The < ins > element can be used
to show content that has been
inserted into a document, while
the < del > element can show text
that has been deleted from it.

The < s > element indicates
something that is no longer
accurate or relevant (but that
should not be deleted).
Visually the content of an < s >
element will usually be displayed
with a line through the center.
![5](https://www8.0zz0.com/2021/02/28/23/713104686.png)

# How To Add CSS
There are three ways of inserting a style sheet:

* External CSS
* Internal CSS
* Inline CSS

## External CSS
With an external style sheet, you can change the look of an entire website by changing just one file!

Each HTML page must include a reference to the external style sheet file inside the < link > element, inside the head section.

An external style sheet can be written in any text editor, and must be saved with a .css extension.

The external .css file should not contain any HTML tags.

![5](https://www7.0zz0.com/2021/03/01/00/503963105.png)

## Internal CSS
An internal style sheet may be used if one single HTML page has a unique style.

The internal style is defined inside the < style> element, inside the head section.

![6](https://www10.0zz0.com/2021/03/01/00/859314559.png)

## Inline CSS
An inline style may be used to apply a unique style for a single element.

To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property.

![7](https://www7.0zz0.com/2021/03/01/00/158852152.png)


# RULES FOR NAMING VARIABLES

1. The name must begin with
a letter, dollar sign ($),or an
underscore (_). It must not start
with a number. 

2. The name can contain letters,
numbers, dollar sign ($), or an
underscore (_). Note that you
must not use a dash(-) or a
period (.) in a variable name. 

3. You cannot use keywords or
reserved words. Keywords
are special words that tell the
interpreter to do something. For
example, var is a keyword used
to declare a variable. Reserved
words are ones that may be used
in a future version of JavaScript.

4. All variables are case sensitive,
so score and Score would be
different variable names, but
it is bad practice to create two
variables that have the same
name using different cases.

5. Use a name that describes the
kind of information that the
variable stores. For example,
fi rstName might be used to
store a person's first name,
l astNarne for their last name,
and age for their age. 

6. If your variable name is made
up of more than one word, use a
capital letter for the first letter of
every word after the first word.
For example, f i rstName rather
than fi rstnarne (this is referred
to as camel case). You can also
use an underscore between each
word (you cannot use a dash).

# ARRAYS
An array is a special type of variable. It doesn't
just store one value; it stores a list of values

Arrays are especially helpful
when you do not know how
many items a list will contain
because, when you create the
array, you do not need to specify
how many values it will hold.

# CREATING AN ARRAY
You create an array and give it
a name just like you would any
other variable (using the var
keyword followed by the name of
the array).

The values are assigned to the
array inside a pair of square
brackets, and each value is
separated by a comma. The
values in the array do not need
to be the same data type, so you
can store a string, a number and
a Boolean all in the same array.

![8](https://www7.0zz0.com/2021/03/01/00/356121922.png)

# Comparison Operators
Comparison operators are used in logical statements to determine equality or difference between variables or values.

![9](https://www.pylenin.com/img/comparison-operators/comparison-table-2.png)

## How Can it be Used
Comparison operators can be used in conditional statements to compare values and take action depending on the result:

![10](https://www5.0zz0.com/2021/03/01/00/409610466.png)

# Logical Operators
Logical operators are used to determine the logic between variables or values.

![11](https://programmingwithbabu.files.wordpress.com/2017/09/logical_operator_in_c.jpg?w=499)







