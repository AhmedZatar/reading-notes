# Heroku 
Heroku cloud application platform to turn the local server into a world wide server.

We will use Node.js for our project. Node.js is an open source, cross-platform runtime environment, which allows you to build server-side and networking applications. It's written in JavaScript and can be run within the Node.js runtime on any platform. First of all, of course, you need to install it. You'd better check the download page for more details. I'll wait until you finish, so don't worry. Is it done? Great! Now you can create your first web server. And it will be one of the easiest tasks in your life.

First of all, we need to create a JavaScript file. Let's name it server.js:

![1](https://www9.0zz0.com/2021/04/21/21/984727131.png)

It's simple. It's tiny. But it's a server! Let's make sure it's working. Run at your terminal:

`node server.js`

Then check it in your browser. Your new server's address, as you may guess, is http://localhost:3000/ 

![2](https://www2.0zz0.com/2021/04/21/21/846282151.png)

Now, to be sure it's a web server and not just a piece of code that returns a single line of text, we'll use it as a server! You can check it with your smartphone. Let's suppose, your laptop's IP address within your local network is 192.168.1.101. You can connect to your server through the 3000th port 

![3](https://www3.0zz0.com/2021/04/21/21/980447325.png)

Well, it is a server! And we have evidence. What you got here is your own client-server model, which can fit in your bag! Take it any place you want! It will be a good idea to deploy our server online, so everyone could see it.

## Make it worldwide

Works fine. But it works locally. WWW is for "World Wide Web" and we will turn your local server into a world wide server. We'll use Heroku cloud application platform for this. Heroku is a cloud platform as a service (cool long-bearded programmer guys call such type of things "PaaS"). It allows you to deploy your web server, so everyone could see how awesome you are as a web developer. First of all, you need to create an account on developer's site and install Heroku. This is not so hard. Just follow the instructions. There is also instruction on Heroku's site that can explain you how to run your first simple web server, which returns you the "Hello, World!" string. You can try it, but I think that it will be more interesting if we build our own web server from scratch. 

First step after Heroku installation is to log in to the system from your computer

`heroku login`

We will leave Heroku for now. But we'll need it soon after we build our server.

Now, the creation. It will be a simple blog with basic functionality. It will show you requested web pages and the error page in case of an error.

Create your project directory. And then create the server.js file inside of it.

![4](https://www13.0zz0.com/2021/04/21/21/874668533.png

)

The first one will give you the key to Node's HTTP functionality. The second one is for possibility to interact with the file system. The third one allows you to handle file paths. The last one allows you to determine a file's MIME-type. And it's not a part of Node.js, so we need to install third-party dependencies before using it. We need to create the package.json file for that purpose. It will contain project related information, such as name, version, description, and so on. For our project we will use MIME-types recognition, because it's not enough to just send the contents of a file when you use HTTP. You also need to set the Content-Type header with proper MIME-type. That's why we need this plug-in.

Create the package.json file and fill it with proper information.

![5](https://www14.0zz0.com/2021/04/21/21/111757089.png)

There are "name", "version", "description", and "dependencies" fields in it. The syntax is simple, as you can see. We added our "mime" plug-in and now it's time to download it. We'll use built-in Node Package Manager. Just run:

` npm install `

t will create node_modules folder and place all the files inside of it. So, we resolve our dependencies and can return to our code.

We will now create send404() function. It will handle the sending of 404 error, which usually appears when requested file doesn't exist:

![6](https://www13.0zz0.com/2021/04/21/21/373923758.png)

Nothing sophisticated with this one. It returns plain text when server can't find a page.

Now we will define sendPage() function. It first writes the header and then sends the contents of the file:

![7](https://www7.0zz0.com/2021/04/21/21/445951229.png)

Notice the way we handle the MIME-types.

Now we'll define how our server will handle responses. This function will return the content of the requested file or the 404 error otherwise:


![8](https://www5.0zz0.com/2021/04/21/21/655413111.png)

And now it's time to create the HTTP server:

![9](https://www14.0zz0.com/2021/04/21/21/459937870.png)

Now we need to start our server. And here's the tricky part. Do you remember how we told the server to listen to the 3000th port in our first example? No? I'll remind you:

`http.createServer(< some code here>).listen(3000)
`
Here you can see how the main page looks like:

![10](https://www10.0zz0.com/2021/04/21/21/152477339.png)

To start your server locally run:

`node server.js`

And then click the first link:

![11](https://www7.0zz0.com/2021/04/21/21/234095697.png)

Then return to the main page and check the second one:

![12](https://www5.0zz0.com/2021/04/21/21/425208529.png)

Here's our 404 page.

We tested our simple server locally and now is time to deploy it.

Open your terminal within your project folder.


Then run:

`heroku create`

Heroku will generate a random name for your application. In my case it's enigmatic-citadel-9298. Don't worry. You can change it later.

Now we can deploy our project. Every Heroku app starts with no branches and no code. So, the first time we deploy our project, we need to specify a remote branch to push to:

`git push heroku master`

The application is now deployed. Ensure that at least one instance of the app is running:

`heroku ps:scale web=1`

And now, before we open it, it's time to choose a proper name for our first creation.

`heroku apps:rename myfirstserver`

Everything is done. You can try it now:

`Everything is done. You can try it now:`

This command will open your Heroku project in your web browser. In this particular case, server address is https://myfirstserver.herokuapp.com/. Now you can share your first web application with any person you want.

# References

> https://howtonode.org/deploy-blog-to-heroku

