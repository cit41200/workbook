# Test an HTTP-Triggered Cloud Function
Now that you have a Cloud Function defined, you can use the **Functions Framework** to test the function prior to deployment to the Google Cloud Platform.

(gcf:test_http:invoke_function_local_1)=
## Invoke the Function Locally
From the command line, use the Functions Framework to invoke your function locally. 

Enter the following on the command line:

```
FUNCTION_TARGET=hello npx @google-cloud/functions-framework
```

The above command tells the Function Framework to invoke the `hello()` function. It knows to look for the function in a file named `index.js` by default.

To see the function run, use the **Web Preview** button in Cloud Shell Editor to invoke the function. Note that the Cloud Shell terminal shows the output of your `console.log` statement.

(gcf:test_http:update_function_1)=
## Add HTTP Request and Response Objects to the Function
An HTTP-triggered Cloud Function is an Express module using the Node.js runtime that can respond to an HTTP *request* object. We can add parameters to our exported function that allows us to read the *request* object and provide a *response* object at the conclusion of the function's logic.

Edit the `index.js` file that includes the code for your Cloud Function. **You should comment out the original code** and then add a new implementation of the `hello()` function as shown below.

```
// Create a basic function that sends a response via HTTP
exports.hello = (req, res) => {
    console.log(`Hello, HTTP!`);
    res.send(`Hello, HTTP!`);
};
```

From the command line, use the Functions Framework to invoke your function locally. 

Enter the following on the command line:

```
FUNCTION_TARGET=hello npx @google-cloud/functions-framework
```

To see the function run, use the **Web Preview** button in Cloud Shell Editor to invoke the function. You will see the plain text response of `Hello, HTTP!` in the browser window, and will continue to see the output of your `console.log` statement in the terminal window.

(gcf:test_http:update_function_2)=
## Read HTTP Request Parameters in the Function
HTTP can transmit information to the function via the `request` object. Data can be transferred via the `request` **body** or the **querystring** of the `request`. You will update the function to read information from the querystring and use the output as part of the `response` that is sent from the function.

Edit the `index.js` file that includes the code for your Cloud Function. **You should comment out the original code** and then add a new, *third* implementation of the `hello()` function as shown below.

```
// Create a function that reads a request parameter and sends a response via HTTP
exports.hello = (req, res) => {
    let username = req.query.username;
    console.log(`Hello, ${username} from HTTP!`);
    res.send(`Hello, ${username} from HTTP!`);
};
```

From the command line, use the Functions Framework to invoke your function locally. 

Enter the following on the command line:

```
FUNCTION_TARGET=hello npx @google-cloud/functions-framework
```

To see the function run, use the **Web Preview** button in Cloud Shell Editor to invoke the function. You will see the plain text response of `Hello, undefined from HTTP!` in the browser window, and will continue to see the output of your `console.log` statement in the terminal window.

You see the value `undefined` in the output because JavaScript expects a value for the `username` variable in the code above. To see the function operate properly, we must provide a value for the `username` variable in the querystring.

In the browser, view the URL that appeared in the toolbar. 

1. If it has a querystring (if there **is** a `?` in the URL), you can append to the end of the querystring by adding the following at the end of your URL in the browser

```
&username=abcd
```

2. If there is **no** querystring (there is **not** a `?` in the URL), you can add one by pasting the following at the end of the URL

```
?username=abcd
```

Press enter in the browser address bar to invoke the Cloud Function a second time. You should now see output that contains the value of the variable in the querystring: `Hello, abcd from HTTP!`. You should also see updated output in the log statement in the terminal.