# Setup SSH Keys for Github

>An SSH key is an access credential for the SSH (secure shell) network protocol. This authenticated and encrypted secure network protocol is used for remote communication between machines on an unsecured open network. SSH is used for remote file transfer, network management, and remote operating system access.

> GitHub have a [detailed guide for you to follow](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), although we have summarised some of the key steps here.

We will need SSH Keys in order to push our code to GitHub.

----
## Generate SSH keys 
- [ ] Open `git bash` by clicking the `git bash` icon in the Taskbar to run it
- [ ] Run the following command (will create a hidden folder called `.ssh`, if it doesn't exist already)

   ```bash
   mkdir .ssh
   ```
   
   If you see an error `cannot create directory ".ssh": Permission Denied` then run the command: `cd` + press enter and then try the command above again.

- [ ] Run the following command to move into the newly created directory

   ```bash
   cd .ssh
   ```

   Make sure you are in the `.ssh` folder. Run the command `pwd` and you should expect to see this output:
   
   `/c/Users/<YOUR_USERNAME>/.ssh`

- [ ] Now we run the following command to generate a new SSH key and save it to our machine. Make sure you replace *your_email@example.com* with your email - this is just a name for the key and it allows you to recognise it.

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
   Once you press enter, you will be asked to choose a filename (you can go for `githubkeys`).

   **NOTE** When asked for a passphrase and then again to confirm, please simply press enter to skip this step.

   Once you have followed the instructions, you should see an output similar to this:

   ![SSH Keygen](../images/macOS-ssh-keygen.png)

- [ ] Now we need to update the configuration for SSH so that it knows to use the newly created key when you attempt to authenticate with github. Make sure you are in

   Make sure you are in the `.ssh` folder. Run the command `pwd` in your Terminal and you should expect to see this output:
   `/c/Users/<YOUR_USERNAME>/.ssh`

   Now we try to create an empty `config` file, if it doesn't exist already by running:
   ```bash
   touch config
   ```

   Now run the command `code ./config` which will open the empty (or existing) `config` file directly in Visual Studio Code.

   You now want to add the following configuration at the bottom of your `config` file and **save**:

   ```text
   Host github.com
     HostName github.com
     PreferredAuthentications publickey
     IdentityFile ~/.ssh/githubkeys
   ```

   **NOTE:** you will have to replace `~/.ssh/githubkeys` with the key filename that you chose in step 4.

## Adding SSH Keys onto Github account

Once you have generated SSH Keys on your machine, we need to add the public key to our github account so that github can authenticate your machine and allow you to push code to github.

- [ ] Click on the `git bash` icon in the Taskbar to run it.
- [ ] Open the public SSH key file that you created earlier by running

   ```bash
   code ~/.ssh/YOUR_GITHUB_SSH_KEY.pub
   ```

   Replace `YOUR_GITUBH_SSH_KEY` with the filename of the SSH key that you generated earlier.

   The file should look something like:

   ```
   ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDHFR60xwGFKN5DHVaMKy7t6mwV0qFDHtLUkxQlUoMCN5Pmn3VXkiUminNDDVtYdDT0BQ70UTPXi6Q6GbinaYNvlOjKDeHnZoMltLcyqSK9EFjZVaUj8zXgX8dARgU+tROjNA6gj3gsO59zO5vqhrJZxWLtYisU3vuuUx2eKwwwIekzMMfoU6lej5l7VIKZ6l6cpxNnPvNKdPB8/cZHJqgVkXoJf+yx7Na5oC/LjEL3Ud4kRnKuEY5PkDYfKYsVQXcja+lgIKPswK5FwFXE5GyAXhlJOBW0EVkatqwXOD6XT6kcUnNsgmezUNbvvhJgV5oez4Y59jPVUWhwgO+eKrT6mKNthVWDddACClVpnN1iMSTgo+W5nfIL2yUOEZ+IvS5RvyUxLe5R4n5sHQDx1FF1oq8UXTquVmQyp1nmagPze7S7qezYsiTSDXTjZxlurhDeva0rLJZ8jD4fL/By4Hldp4zj4YEdw4VORzaQTNXHFL/QDcQfXzPUoDfFB3TUvEG4vqrkfjypkIWpzxCfjFBJqRwLqc+ri9Xtvv4mOBd9M0D1pSbToj6ubvbw1nrTgSyNQ5m9PPQa2ppWrps0N7y2fAjLVScjXUj897OJZehb9V0yM03UosRUNRjdiEA8usOqR+NInISXYH97jw+hILuewaSOb443aKfuDHAu48O1Bw== your_email@example.com
   ```

- [ ] Select _all_ the text with `<Ctrl-A>` and copy it to clipboard with `<Ctrl-C>`
- [ ] Visit your [Github settings](https://github.com/settings/profile) page (requires login, then find your profile icon and the dropdown next to it will take you to the Settings page).
- [ ] From your Github Settings page, you will find the SSH and GPG Keys section in the left sidebar (alternatively, visit [https://github.com/settings/keys](https://github.com/settings/keys))
- [ ] Click the green `New SSH Key` button.
- [ ] Choose a title and paste the key you copied earlier with `<Ctrl-C>` (see the screenshot below)

   ![Github SSH Key](../images/github-add-ssh-key.png)

   **NOTE**: make sure that when you paste, you are not pasting whitespace (new lines, spaces).

- [ ] Click `Add SSH Key`

## Check that SSH & Github are setup correctly

In your terminal, run the following command:
```bash
ssh -T git@github.com
```

If everything is correctly setup, you should see the following message:

`Hi <YOUR_GITHUB_USERNAME>! You've successfully authenticated, but GitHub does not provide shell access.`

## Add Your Identity Details For Git Operations

Before you can use Git, you need to paste the following commands into a `git bash` window - you can open one by clicking on the `git bash` icon in the Taskbar.

```text
git config --global user.email "your_email@address"
git config --global user.name "Your Name"
```

This ensures any changes you make are tagged with you name. You will see this when you look at changes in GitHub, VSCode or using `git` commands.

---

[Return to the table of comments at the top of the first page](1-windows-setup-instructions-git-install.md#table-of-contents)

---
| Previous | Next |
| ----- | ---------- |
| [Step 3 Install Install NVM and NodeJS](3-windows-setup-instructions-node-install.md) | Congratulations! You are done! |