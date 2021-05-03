# Sending form data
Once the form data has been validated on the client-side, it is okay to submit the form. And, since we covered validation in the previous article, we're ready to submit! This article looks at what happens when a user submits a form — where does the data go, and how do we handle it when it gets there? We also look at some of the security concerns associated with sending form data.

## Client/server architecture
At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.

## On the client side: defining how to send the data
The < form> element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are action and method.

## The action attribute
The action attribute defines where the data gets sent. Its value must be a valid relative or absolute URL. If this attribute isn't provided, the data will be sent to the URL of the page containing the form — the current page

In this example, the data is sent to an absolute URL — https://example.com:

`<form action="https://example.com">`

Here, we use a relative URL — the data is sent to a different URL on the same origin:

`<form action="/somewhere_else">`

When specified with no attributes, as below, the <form> data is sent to the same page that the form is present on:

`<form>`

The names and values of the non-file form controls are sent to the server as name=value pairs joined with ampersands. The action value should be a file on the server that can handle the incoming data, including ensuring server-side validation. The server then responds, generally handling the data and loading the URL defined by the action attribute, causing a new page load (or a refresh of the existing page, if the action points to the same page).


How the data is sent depends on the method attribute.

## The method attribute

The method attribute defines how data is sent. The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods, the most common being the GET method and the POST method

To understand the difference between those two methods, let's step back and examine how HTTP works. Each time you want to reach a resource on the Web, the browser sends a request to a URL. An HTTP request consists of two parts: a header that contains a set of global metadata about the browser's capabilities, and a body that can contain information necessary for the server to process the specific request.

## The GET method

The GET method is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource." In this case, the browser sends an empty body. Because the body is empty, if a form is sent using this method the data sent to the server is appended to the URL.

Consider the following form:

![0](https://www2.0zz0.com/2021/05/03/21/968544569.png)

Since the GET method has been used, you'll see the URL www.foo.com/?say=Hi&to=Mom appear in the browser address bar when you submit the form.

![1](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data/url-parameters.png)

The data is appended to the URL as a series of name/value pairs. After the URL web address has ended, we include a question mark (?) followed by the name/value pairs, each one separated by an ampersand (&). In this case we are passing two pieces of data to the server:

* say, which has a value of Hi
* to, which has a value of Mom

The HTTP request looks like this:

`GET /?say=Hi&to=Mom HTTP/2.0`
`Host: foo.com`

## The POST method

The POST method is a little different. It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP request: "Hey server, take a look at this data and send me back an appropriate result." If a form is sent using this method, the data is appended to the body of the HTTP request.

Let's look at an example — this is the same form we looked at in the GET section above, but with the method attribute set to POST.

![2](https://www10.0zz0.com/2021/05/03/21/302688917.png)

When the form is submitted using the POST method, you get no data appended to the URL, and the HTTP request looks like so, with the data included in the request body instead:

![3](https://www10.0zz0.com/2021/05/03/21/659052844.png)

The Content-Length header indicates the size of the body, and the Content-Type header indicates the type of resource sent to the server. We'll discuss these headers later on.

## Viewing HTTP requests

HTTP requests are never displayed to the user (if you want to see them, you need to use tools such as the Firefox Network Monitor or the Chrome Developer Tools). As an example, your form data will be shown as follows in the Chrome Network tab. After submitting the form:

1. Open the developer tools.
2. Select "Network"
3. Select "All"
4. Select "foo.com" in the "Name" tab
5. Select "Headers"

You can then get the form data, as shown in the image below.

![4](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data/network-monitor.png)

The only thing displayed to the user is the URL called. As we mentioned above, with a GET request the user will see the data in their URL bar, but with a POST request they won't. This can be very important for two reasons:

1. If you need to send a password (or any other sensitive piece of data), never use the GET method or you risk displaying it in the URL bar, which would be very insecure.
2. If you need to send a large amount of data, the POST method is preferred because some browsers limit the sizes of URLs. In addition, many servers limit the length of URLs they accept.

## Summary 
As we'd alluded to above, sending form data is easy, but securing an application can be tricky. Just remember that a front-end developer is not the one who should define the security model of the data.It's possible to perform client-side form validation, but the server can't trust this validation because it has no way to truly know what has really happened on the client-side.

If you've worked your way through these tutorials in order, you now know how to markup and style a form, do client-side validation, and have some idea about submitting a form.

# References

> https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data#summary