## Read: 06 - Node, Express, and API
<!-- https://www.sitepoint.com/an-introduction-to-node-js/ -->
- Node is built on the V8 engine, we don’t mean that Node programs are executed in a browser. They aren’t. Rather, the creator of Node (Ryan Dahl) took the V8 engine and enhanced it with various features, such as a file system API, an HTTP library, and a number of operating system–related utility methods.
- NodeJS has excellent support for moder js syntax
- In addition to being the package manager for JavaScript, npm is also the world’s largest software registry. There are over 1,000,000 packages of JavaScript code available to download, with billions of downloads per week
#### Installing a Package Globally
Open your terminal and type the following:

npm install -g jshint
This will install the jshint package globally on your system. We can use it to lint the index.js file from the previous example:

jshint index.js
You should now see a number of ES6-related errors. If you want to fix them up, add /* jshint esversion: 6 */ to the top of the index.js file, re-run the command and linting should pass.

#### Installing a Package Locally
We can also install packages locally to a project, as opposed to globally, on our system. Create a test folder and open a terminal in that directory. Next type this:

npm init -y
This will create and auto-populate a package.json file in the same folder. Next, use npm to install the lodash package and save it as a project dependency:

npm install lodash --save
Create a file named test.js and add the following:

const _ = require('lodash');

const arr = [0, 1, false, 2, '', 3];
console.log(_.compact(arr));
Finally, run the script using node test.js. You should see [ 1, 2, 3 ] output to the terminal.
- Working with the package.json File
If you look at the contents of the test directory, you’ll notice a folder entitled node_modules. This is where npm has saved lodash and any libraries that lodash depends on. The node_modules folder shouldn’t be checked in to version control, and can, in fact, be re-created at any time by running npm install from within the project’s root.

If you open the package.json file, you’ll see lodash listed under the dependencies field. By specifying your project’s dependencies in this way, you allow any developer anywhere to clone your project and use npm to install whatever packages it needs to run.

If you’d like to find out more about npm, be sure to read our article A Beginner’s Guide to npm — the Node Package Manager.

#### What Is Node.js Used For?
Now that we know what Node and npm are and how to install them, we can turn our attention to the first of their common uses: installing (via npm) and running (via Node) various build tools — designed to automate the process of developing a modern JavaScript application.

These build tools come in all shapes and sizes, and you won’t get far in a modern JavaScript landscape without bumping into them. They can be used for anything from bundling your JavaScript files and dependencies into static assets, to running tests, or automatic code linting and style checking.

#### The Node.js Execution Model

- Node.js, however, is single-threaded. It’s also event-driven, which means that everything that happens in Node is in reaction to an event. For example, when a new request comes in (one kind of event) the server will start processing it. If it then encounters a blocking I/O operation, instead of waiting for this to complete, it will register a callback before continuing to process the next event. When the I/O operation has finished (another kind of event), the server will execute the callback and continue working on the original request. Under the hood, Node uses the libuv library to implement this asynchronous (that is, non-blocking) behavior.

Node’s execution model causes the server very little overhead, and consequently it’s capable of handling a large number of simultaneous connections. The traditional approach to scaling a Node app is to clone it and have the cloned instances share the workload. Node.js even has a built-in module to help you implement a cloning strategy on a single server.
<img src="images/nodeloop.png">