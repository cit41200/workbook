# Create an HTTP-Triggered Cloud Function
Using the Google Cloud Shell as your development environment, you will create a Google Cloud Function that is triggered by an HTTP request.

We will first run this function locally using the Google Cloud Functions Framework.

(gcf:create_http:createdevenvironment)=
## Create a Local Development Environment
Each Google Cloud Function is its own individual Node application. Create a **local root folder** inside your Google Cloud Shell in which you will develop your function.

On the command line, enter the following:
```
cd 41200
mkdir gcf_hello_http
cd gcf_hello_http
touch index.js .gitignore
```

Open the `gcf_hello_http` directory in the Cloud Shell editor.

In the `.gitignore` file, input the following:

```
node_modules
```

In the `index.js` file, input the following:

```
// Create a basic arrow function
exports.hello = () => console.log(`Hello, HTTP!`);
```

You now have a JavaScript module with one function exported. When your Cloud Function is triggered, you will specify which exported function should be invoked.

(gcf:create_http:functions_framework)=
## Install the Functions Framework
The Functions Framework is a Node.js package that will allow you to run your Google Cloud Function locally (on your Cloud Shell) so that you can test your function prior to deployment.

Install the Functions Framework by entering the following on the command line:

```
npm install --save-dev @google-cloud/functions-framework
```