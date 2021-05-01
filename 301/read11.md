# EJS

## What is EJS?

What is the "E" for? "Embedded?" Could be. How about "Effective," "Elegant," or just "Easy"? EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. No religiousness about how to organize things. No reinvention of iteration and control-flow. It's just plain JavaScript.

EJS is a template system. You define HTML pages in the EJS syntax and you specify where various data will go in the page. Then, your app combines data with the template and "renders" a complete HTML page where EJS takes your data and inserts it into the web page according to how you've defined the template. For example, you could have a table of dynamic data from a database and you want EJS to generate the table of data according to your display rules. It saves you from the drudgery of writing code to dynamically generate HTML based on data.

EJS is compatible with Express for back-end use as it hooks into the View engine architecture that Express provides and lets you render web pages to the client with res.render() in Express.

FYI, there are dozens of competing template systems for use in node.js. EJS is a popular one and people typically choose one based on features that match your needs, how their layout language fits what you want to use, what seems easiest to you to use, etc... I've used Pug, Handlebars, Nunjucks and EJS. Nunjucks is my current favorite.

EJS (along with all the other competing template engines) allows you to generate full-blown HTML pages which certainly enables a "proper front-end".

EJS is a tool for generating web pages that can include dynamic data and can share templated pieces with other web pages (such as common headers/footers). It is not a front-end framework. While EJS can be used by client-side Javascript to generate HTML on the client-side, it is more typically used by your back-end to generate web pages in response to some URL request. EJS is not a client-side framework like Angular or React and does not dictate what client-side framework you do or don't use (if any). It is mostly covers a separate solution space.


## Features
1. Fast compilation and rendering
2. Simple template tags: <% %>
3. Custom delimiters (e.g., use [? ?] instead of <% %>)
4. Sub-template includes
5. Ships with CLI
6. Both server JS and browser support
7. Static caching of intermediate JavaScript
8. Static caching of templates
9. Complies with the Express view system

# Get Started

## Install

It's easy to install EJS with NPM.

`$ npm install ejs`

## Use

Pass EJS a template string and some data. BOOM, you've got some HTML.

![0](https://www3.0zz0.com/2021/05/01/20/492319102.png)

## CLI
Feed it a template file and a data file, and specify an output file.

`ejs ./template_file.ejs -f data_file.json -o ./output.html` 

## Browser support

Download a browser build from the latest release, and use it in a script tag.

![1](https://www5.0zz0.com/2021/05/01/20/233730169.png)

## Docs
Example

![2](https://www2.0zz0.com/2021/05/01/20/349874210.png)

Usage

![3](https://www2.0zz0.com/2021/05/01/20/395311898.png)

Options

* cache Compiled functions are cached, requires filename
* filename Used by cache to key caches, and for includes
* root Set project root for includes with an absolute path (e.g, /file.ejs). Can be array to try to resolve include from multiple directories.
* views An array of paths to use when resolving includes with relative paths.
* context Function execution context
* compileDebug When false no debug instrumentation is compiled
* client Returns standalone compiled function
* delimiter Character to use for inner delimiter, by default '%'
* openDelimiter Character to use for opening delimiter, by default '<'
* closeDelimiter Character to use for closing delimiter, by default '>'
* debug Outputs generated function body
* strict When set to `true`, generated function is in strict mode
* _with Whether or not to use with() {} constructs. If false then the locals will be stored in the locals object. (Implies `--strict`)
* localsName Name to use for the object storing local variables when not using with Defaults to locals
* rmWhitespace Remove all safe-to-remove whitespace, including leading and trailing whitespace. It also enables a safer version of -%> line slurping for all scriptlet tags (it does not strip new lines of tags in the middle of a line).
* escape The escaping function used with <%= construct. It is used in rendering and is .toString()ed in the generation of client functions. (By default escapes XML).
* outputFunctionName Set to a string (e.g., 'echo' or 'print') for a function to print output inside scriptlet tags.
* async When true, EJS will use an async function for rendering. (Depends on async/await support in the JS runtime.

## Tags

* <% 'Scriptlet' tag, for control-flow, no output
* <%_ ‘Whitespace Slurping’ Scriptlet tag, strips all whitespace before it
* <%= Outputs the value into the template (HTML escaped)
* <%- Outputs the unescaped value into the template
* <%# Comment tag, no execution, no output
* <%% Outputs a literal '<%'
* %> Plain ending tag
* -%> Trim-mode ('newline slurp') tag, trims following newline
* _%> ‘Whitespace Slurping’ ending tag, removes all whitespace after it

## Includes
Includes are relative to the template with the include call. (This requires the 'filename' option.) For example if you have "./views/users.ejs" and "./views/user/show.ejs" you would use <%- include('user/show'); %>.

You'll likely want to use the raw output tag (<%-) with your include to avoid double-escaping the HTML output.

![4](https://www3.0zz0.com/2021/05/01/20/978619830.png)

## CLI
EJS ships with a full-featured command-line interface. Options are similar to those used in JavaScript code:

* cache Compiled functions are cached, requires filename
* -o / --output-file FILE Write the rendered output to FILE rather than stdout.
* -f / --data-file FILE Must be JSON-formatted. Use parsed input from FILE as data for rendering.
* -i / --data-input STRING Must be JSON-formatted and URI-encoded. Use parsed input from STRING as data for rendering.
* -m / --delimiter CHARACTER Use CHARACTER with angle brackets for open/close (defaults to %).
* -p / --open-delimiter CHARACTER Use CHARACTER instead of left angle bracket to open.
* -c / --close-delimiter CHARACTER Use CHARACTER instead of right angle bracket to close.
* -s / --strict When set to `true`, generated function is in strict mode
* -n / --no-with Use 'locals' object for vars rather than using `with` (implies --strict).
* -l / --locals-name Name to use for the object storing local variables when not using `with`.
* -w / --rm-whitespace Remove all safe-to-remove whitespace, including leading and trailing whitespace.
* -d / --debug Outputs generated function body
* -h / --help Display this help message.
* -V/v / --version Display the EJS version

# References

> https://ejs.co/
