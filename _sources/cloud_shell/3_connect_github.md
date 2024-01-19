# Connect GitHub to Cloud Shell

You will generate an SSH key on your Ubuntu Cloud Shell and add that key to your account on GitHub.com. This will allow you to securely interact with your remote repositories on GitHub.com without the need to enter a username and password.

(cloud_shell:connect_github:check)=
## Check for an Existing SSH Key

If you're used Cloud Shell in the past, you may have an existing SSH key. If so, you can skip much of the setup on this page.

1. Run the following command in the terminal:

```
cat ~/.ssh/id_ed25519.pub
```

If you see the message `No such file or directory`, continue to the {ref}`next section <cloud_shell:connect_github:create_ssh>`.

If you see output that ends with your email address, jump to the section {ref}`cloud_shell:connect_github:add_ssh_github`.

(cloud_shell:connect_github:create_ssh)=
## Generate an SSH Key

1. From the Cloud Shell terminal, use the built-in utility to create a new, local SSH key. **Make sure you replace the email address with the email address used when creating your GitHub.com account.**

```
ssh-keygen -t ed25519 -C "your_email@iu.edu"
```

2. When asked where to save the file, choose the default location.

3. You are then prompted to create a passphrase for your keyfile. You may do so, or just press Enter for no passphrase.

(cloud_shell:connect_github:add_ssh_agent)=
## Add SSH Key to the ssh-agent

You'll now store your key in the SSH Agent (the background process that manages all of your SSH keys).

1. At the terminal command prompt, enter the following:

```
eval "$(ssh-agent -s)"
```

This will respond with a message like "Agent pid 1111" (the number represents the process identifier and will be different for everyone).

2. Then add the key to the agent with this command: 

```
ssh-add ~/.ssh/id_ed25519
```
```{note}
If you chose a filename other than the default (`id_ed25519`) when you created the key, use the updated filename here.
```

(cloud_shell:connect_github:add_ssh_github)=
## Add SSH Key to GitHub

You will add the public key file for your SSH key to your GitHub.com account. This will allow your computer to authenticate with GitHub.com when you interact with a remote repository.

1. In the Cloud Shell terminal, use the following command to display the contents of your public key on the screen:

```
cat ~/.ssh/id_ed25519.pub
```
```{note}
Again: if you chose a filename other than the default when you created the key, use the updated filename here. Make sure you use the file with the `.pub` extension (this is your "public" key).
```

2. **COPY** the line that is returned in the command prompt. Ensure you do not select any additional whitespaces or extra lines. Your public key should look similar to the following: `ssh-ed25519 ZZZZZZZKDLDLDKksdjsd9093u2ndkksksdnjdn290DJHDGKDK903e9JD0HNeDKJ44k username@iu.edu`

3. In a web browser, log into your [GitHub.com](https://github.com) account.

4. In the upper-right corner of any page, click your profile photo and then click Settings.

```{image} img/userbar-account-settings.webp
:alt: The Settings menu in GitHub's navigation
:align: center
:width: 200px
```

5. In the "Access" section of the sidebar, click **SSH and GPG keys**.

6. Click **New SSH key** or **Add SSH key**.

7. In the "Title" field, add a descriptive label for the new key. For example, you might call this key "School Macbook".

8. Select **authentication** as your key type.

9. In the "Key" field, paste the public key that you copied previously. Ensure you do not accidentally add any additional whitespaces before or after the key.

10. Click **Add SSH key**

11. If prompted, confirm access to your account on GitHub.