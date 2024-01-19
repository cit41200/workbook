# Create a Remote GitHub Repository

Create a remote repository on [GitHub.com](https://github.com) where you will store your program for backup and collaboration.

```{note}
You should have already connected your Google Cloud Shell to GitHub via SSH during class!
```

1. Go to [GitHub.com](https://github.com) and log in.

2. Click the "New repository" button on the page.

3. Give your repository a logical name. You'll end up with **many** repositories, so organizing them with meaningful names is a very good idea.
    * **DO NOT** check any of the additional options! You don't want to add a `README` or a `.gitignore` file in your remote repository. (You already have those locally and will create conflicts if you create them here.)

Once your repository is created, you will be taken to a page that provides next steps for you to perform.

4. **COPY** the instruction that begins with the command `git remote add origin...` You'll use this command in the next step.

(git:remote:connect)=
## Connect Your Remote and Local Repositories
Once you have created your local and remote repositories, you can connect them together so that you can read and write between them.

1. Return to the command line and ensure you are still in the directory where you created your local repository

2. Paste the command you copied from GitHub into the command line
    * This command does the following:
        * `git`: invokes the Git software
        * `remote`: issues a command related to a remote repository
        * `add`: create a connection to a remote repository
        * `origin`: this is the 'nickname' for this remote. You can connect your local repository to multiple remote repositories (each with their own nickname)
        * `url to repository`: the github resource address of your remote repository

Git will not acknowledge that you have made a connection. If it returns you to the command line with no message, you may assume the command worked.