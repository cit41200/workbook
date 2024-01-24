# Create a Cloud Function

Using the Google Cloud Shell as your development environment, you will create a Google Cloud Function that is triggered by an HTTP request.

We will first run this function locally using the Google Cloud Functions Framework.

(gcf:local:createdevenvironment)=
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
exports.hello = () => console.log('Hello, HTTP!');
```

You now have a JavaScript module with one function exported. When you call your Cloud Function, you will specify which exported function should be invoked.

(gcf:local:functions_framework)=
## Install the Functions Framework
The Functions Framework is a Node.js package that will allow you to run your Google Cloud Function locally (on your Cloud Shell) so that you can test your function prior to deployment.

Install the Functions Framework by entering the following on the command line:

```
npm install --save-dev @google-cloud/functions-framework
```

(gcf:local:invoke_function_local_1)=
## Invoke the Function Locally
From the command line, use the Functions Framework to invoke your function locally. Enter the following on the command line:

```
FUNCTION_TARGET=hello npx @google-cloud/functions-framework
```

The above command tells the Function Framework to invoke the `hello()` function. It knows to look for the function in a file named `index.js` by default.

To see the function run, use the **Web Preview** button in Cloud Shell Editor to invoke the function. Note that the Cloud Shell terminal shows the output of your `console.log` statement.