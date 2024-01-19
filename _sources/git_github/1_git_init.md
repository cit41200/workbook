# Create a Local Git Repository

(git:init)=
## Create a New Local Repository
To manage your project with Git, you must create a *local Git repository*. You only create the repository **once** for each project and will then continually update the repository as needed.

1. Use the command line to navigate *into* the top level directory of the project you wish to store with Git.

2. On the command line, create a new, empty repository with the following command:

```
git init
```

You should receive a message that a new, empty repository was created.

3. (If you have not already done so), add supporting files to your repository with the following command:

```
touch README.md .gitignore
```

```{note}
You can also use the command `code README.md .gitignore` to create and open those files directly in the VS Code editor.
```

(git:init:readme)=
## Write a README.md File
The `README.md` file will be packaged with your repository and allows you to explain the purpose and structure of your code.

This is a good place to write documentation, notes to your viewers, and any other "plain English" information about your project that you would like to share.

1. In the `README.md` file, use [Markdown](https://www.markdownguide.org/basic-syntax/) to write any instructions or information you'd like.

(git:init:gitignore)=
## Add Files to your .gitignore File
The `.gitignore` tells Git to ignore specific local files and subdirectories from your *local repository* (therefore they will not be transferred to your remote repository).

In general, you want to exclude compiled versions of your programs and external libraries that should be reinstalled if your program is run on a different system. You also want to exclude any files that have sensitive information (passwords, connection strings, etc.).

GitHub provides a [standard Node `.gitignore` template](https://github.com/github/gitignore/blob/main/Node.gitignore) that you can copy and modify as needed.

1. Visit the [GitHub Node .gitignore template](https://github.com/github/gitignore/blob/main/Node.gitignore).

2. Copy the Raw contents of the file from GitHub.

3. Paste the contents into your local `.gitignore` file.

4. Add any additional files or subdirectories as needed, and save the file.