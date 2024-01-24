# Add, Commit, and Push

You now have an empty remote repository and an empty local repository that are connected together and ready for writing.

When working with Git, you will create "commits" as you progress. Think of a commit like a checkpoint in a video game or a bookmark in a book – you are taking a snapshot of your program at a specific point in time, and you can always return to that snapshot precisely as it was when you made the commit.

Creating this breakpoint requires two steps (`add`, `commit`) and has a third, optional step that moves your code from your local repository to the remote (`push`).

(git:add_commit_push:add)=
## Add Files to Your Local Repository

When you are ready to take a snapshot of your project, you must tell Git which files you want to include. In general, you'll include all of your files *except* those specified in the `.gitignore` file.

1. Add any files or directories that you DO NOT want to include to your `.gitignore`
    * This might be files that contain sensitive information (passwords, test data, etc.)

2. Save your `.gitignore` file

3. Tell Git to track all of the other files in your directory and subdirectories with the following command:

```
git add .
```

The `.` ensures that Git adds all files in all directories in your project's root folder.

(git:add_commit_push:commit)=
## Make a Commit

After adding the files, you're able to make a commit.

Each commit you make should have a meaningful message that describes *why* you are choosing to create a commit at this point. You might explain the state of the program (e.g., "Finished login script") or what you did since the last commit (e.g., "Fixed a bug in the database connection.").

When you are ready, execute the following command:

```
git commit -m "Commit message goes here"
```

Put your message in the double quotes.

(git:add_commit_push:push)=
## (Optional) Push Your Local Repository to the Remote

If you want to move your latest work to the remote repository, do the following:

```
git push origin --all
```

This will move all branches of your local repository to the remote. If you want to move just a single branch, you can do that too. For example, if you want to move your `main` branch, you can run this command:

```
git push origin main
```

You do not need to move your code to GitHub if you do not want to. (It's a good practice, though!)

You also do not need to `push` your code after every commit. Your entire commit history will by synced to your remote repository when you execute a `push` command, so you can make several commits and then push them all at once.