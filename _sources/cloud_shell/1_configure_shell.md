# Configure Google Cloud Shell

(cloud_shell:configure:root_directory)=
## Create a Root Directory

You should create a root directory for this course. All project files for this course will go inside this directory.

Enter the following command at the terminal prompt:
```
mkdir 41200
```

(cloud_shell:configure:git)=
## Configure Git on Cloud Shell

Configure Git so it can automatically add your user details to the commits you will make to your repositories. 

1. Input the following commands on the MacOS Terminal command line, replacing the information as needed with your personal details.

```
git config --global user.name "Your Name"
```

You will *not* see any kind of feedback from the command prompt after you issue this command.

2. Use your school email address here (@iupui.edu or @iu.edu):

```
git config --global user.email "youremail@iu.edu"
```

Again, the command prompt will be empty after this command.