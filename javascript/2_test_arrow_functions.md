# Test JavaScript Functions in Cloud Shell

Test your JavaScript functions by using `Node.js` as the runtime to execute your JavaScript code.

You created a root directory, `41200`, in a previous chapter. Now you'll create a subdirectory where you can create and execute some JavaScript code.

In your Cloud Shell terminal, do the following:

```
cd ~ # This takes you to the home directory of your VM
cd 41200 # This takes you into your root directory for this course
mkdir arrow_functions
cd arrow_functions
touch helloCloud.js README.md
```

The above code moved your working directory to the `home` directory of the Cloud Shell VM. You then moved into your `41200` directory, created a new directory named `arrow_functions`, moved into that new directory, and created two empty files.

The `README.md` file is an overview document for your Git repository. You can add any information about the project there.

The `helloCloud.js` file is an empty file where we can add JavaScript commands.

(javascript:test_functions:write_code)=
## Write Code in Your JavaScript File

In the Cloud Shell Editor (the top half of your Cloud Shell screen), choose `File > Open Folder...` Navigate to your `arrow_functions` directory and open it. You will see your two empty files in the Explorer tab on the left.

Add the following code to your `helloCloud.js` file:

```
const helloCloud = () => 'Hello, cloud!';

console.log(helloCloud());
```

The file is saved automatically, but you can Save it if you'd like.

(javascript:test_functions:execute)=
## Execute Your JavaScript File

Run your file by entering the following command in the terminal:

```
node helloCloud.js
```

You should see the output, `Hello, cloud!` in the terminal window. (This is where `console.log` statements will appear in the Cloud Shell.)

(javascript:test_functions:write_arrow_functions)=
## Write Arrow Functions in a JavaScript File

For practice, let's create another JavaScript file that demonstrates the evolution of a JavaScript function from "basic" to "arrow".

At the command line, create a new file:

```
touch milesToKM.js
```

You'll see the new file appear in the editor at the top left of the screen. Select it to open it in the editor.

Add the following code to your `milesToKM.js` file:

```
let inputMiles = 100;

function milesToKM(miles) {
    return miles * 1.60934;
}

console.log(milesToKM(inputMiles));
```

Note that we declared a variable (`inputMiles`) internally in this file. This is not a best practice, but will work for our demonstration.

Run your file by entering the following command in the terminal:

```
node milesToKM.js
```

You should see the output, `160.934` in the terminal window.

**Replace** the existing code in the `milesToKM.js` file with this new version:

```
let inputMiles = 100;

function milesToKM(miles) {
    return miles * 1.60934;
}

const milesToKMExpression = function(miles) {
    return miles * 1.60934
}

console.log(milesToKM(inputMiles));
console.log(milesToKMExpression(inputMiles));
```

When you execute your code, you'll see `160.934` appear twice in the console (once for each function).

Finally, **replace** the existing code one last time in the `milesToKM.js` file with this new version:

```
let inputMiles = 100;

function milesToKM(miles) {
    return miles * 1.60934;
}

const milesToKMExpression = function(miles) {
    return miles * 1.60934
}

const milesToKMArrow = miles => miles * 1.60934;

console.log(milesToKM(inputMiles));
console.log(milesToKMExpression(inputMiles));
console.log(milesToKMArrow(inputMiles));
```

Note that `160.934` appears in the console **3** times. You've written the same function 3 different ways and can see that it's produced the same output.