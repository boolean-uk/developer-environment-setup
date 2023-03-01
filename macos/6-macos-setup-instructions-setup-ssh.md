# Setup SSH Keys for Github

> An SSH key is an access credential for the SSH (secure shell) network protocol. This authenticated and encrypted secure network protocol is used for remote communication between machines on an unsecured open network. SSH is used for remote file transfer, network management, and remote operating system access.

We will need SSH Keys in order to push our code to GitHub.

> GitHub have a [detailed guide for you to follow](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), although we have summarised some of the key steps here.

## Generate your SSH keys
- [ ] Open Terminal app
- [ ] Run the following command (will create a hidden folder called `.ssh`, if it doesn't exist already)

   ```bash
   mkdir .ssh
   ```

- [ ] Run the following command to move into the newly created directory

   ```bash
   cd .ssh
   ```

   Make sure you are in the `.ssh` folder. Run the command `pwd` and you should expect to see this output:

   `/Users/YOUR_USERNAME/.ssh`

- [ ] Now we run the following command to generate a new SSH key and save it to our machine. Make sure you replace *your_email@example.com* with your email - this is just a name for the key and it allows you to recognise it.
   
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
   > **NOTE:** You will need to keep the quotes in the above command line and enter your email between the quotes

   Once you press enter, you will be asked to choose a filename (you can go for `githubkey`) and then a password. Make sure to note this down safely, you will need it later.

   Once you have followed the instructions, you should see an output similar to this:

   ![SSH Keygen](../images/macOS-ssh-keygen.png)

- [ ] Add the SSH key to your keychain

   ```bash
   ssh-add --apple-use-keychain ~/.ssh/[your-private-key]
   ```
   > **NOTE:** Replace the [your-private-key] including the square brackets []

   If you used the suggested private key name, `githubkey` then the command will be 
   ```bash
   ssh-add --apple-use-keychain ~/.ssh/githubkey
   ```

- [ ] Now we need to update the configuration for SSH so that it knows to use the newly created key when you attempt to authenticate with github. Make sure you are in

   Make sure you are in the `.ssh` folder. Run the command `pwd` in your Terminal and you should expect to see this output:

   `/Users/YOUR_USERNAME/.ssh`

   Now we try to create an empty `config` file, if it doesn't exist already by running:

   ```bash
   touch config
   ```

   Now run the command 
   ```bash
   code ./config
   ``` 
   which will open the empty (or existing) `config` file directly in Visual Studio Code.

   You now want to add the following configuration at the bottom of your `config` file and save:

   ```text
   Host *
     AddKeysToAgent yes
     UseKeychain yes
     IdentityFile ~/.ssh/[your-private-key]
   ```

   >**NOTE:** you will have to replace `~/.ssh/[your-private-key]` with the key filename that you chose in step 4, so if you used the suggested file name, `githubkey`, this will be `~/.ssh/githubkey`

### 6.1. Adding SSH Keys onto Github account

Once you have generated SSH Keys on your machine, we need to add the public key to our github account so that github can authenticate your machine and allow you to push code to github.

1. Open the Terminal app
2. Open the public SSH key file that you created earlier by running

   ```bash
   code ~/.ssh/YOUR_GITHUB_SSH_KEY.pub
   ```

   Replace `YOUR_GITUBH_SSH_KEY` with the filename of the SSH key that you generated earlier.

   The file should look something like:

   ```text
   ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDHFR60xwGFKN5DHVaMKy7t6mwV0qFDHtLUkxQlUoMCN5Pmn3VXkiUminNDDVtYdDT0BQ70UTPXi6Q6GbinaYNvlOjKDeHnZoMltLcyqSK9EFjZVaUj8zXgX8dARgU+tROjNA6gj3gsO59zO5vqhrJZxWLtYisU3vuuUx2eKwwwIekzMMfoU6lej5l7VIKZ6l6cpxNnPvNKdPB8/cZHJqgVkXoJf+yx7Na5oC/LjEL3Ud4kRnKuEY5PkDYfKYsVQXcja+lgIKPswK5FwFXE5GyAXhlJOBW0EVkatqwXOD6XT6kcUnNsgmezUNbvvhJgV5oez4Y59jPVUWhwgO+eKrT6mKNthVWDddACClVpnN1iMSTgo+W5nfIL2yUOEZ+IvS5RvyUxLe5R4n5sHQDx1FF1oq8UXTquVmQyp1nmagPze7S7qezYsiTSDXTjZxlurhDeva0rLJZ8jD4fL/By4Hldp4zj4YEdw4VORzaQTNXHFL/QDcQfXzPUoDfFB3TUvEG4vqrkfjypkIWpzxCfjFBJqRwLqc+ri9Xtvv4mOBd9M0D1pSbToj6ubvbw1nrTgSyNQ5m9PPQa2ppWrps0N7y2fAjLVScjXUj897OJZehb9V0yM03UosRUNRjdiEA8usOqR+NInISXYH97jw+hILuewaSOb443aKfuDHAu48O1Bw== your_email@example.com
   ```

3. Select _all_ the text with `CMD+A` and copy it to clipboard with `CMD+C`
4. Visit your [Github settings](https://github.com/settings/profile) page (requires login, then find your profile icon and the dropdown next to it will take you to the Settings page).
5. From your Github Settings page, you will find the SSH and GPG Keys section in the left sidebar (alternatively, visit [https://github.com/settings/keys](https://github.com/settings/keys))
6. Click the green `New SSH Key` button.
7. Choose a title and paste the key you copied earlier with `CMD+V` (see the screenshot below)

   ![Github SSH Key](../images/github-add-ssh-key.png)

   **NOTE**: make sure that when you paste, you are not pasting whitespace (new lines, spaces).

8. Click `Add SSH Key`

### 6.2 Check that SSH & Github are setup correctly

In your terminal, run the following command:

`ssh -T git@github.com`

If everything is correctly setup, you should see the following message:

`Hi YOUR_GITHUB_USERNAME! You've successfully authenticated, but GitHub does not provide shell access.`

### 6.3 Add Your Identity Details For Git Operations

Before you can use Git, you need to paste the following commands into a git bash window - you can open one by clicking on the git bash icon in the Taskbar.

```bash
git config --global user.email "your_email@address"

git config --global user.name "Your Name"
```
> **NOTE:** You will need to keep the quotes in the above command line and enter your email between the quotes

This ensures any changes you make are tagged with you name. You will see this when you look at changes in GitHub, VSCode or using git commands.
---
| Previous | Next |
| ----- | ---------- |
| [Step 5 Install Install NVM and NodeJS](5-macos-setup-instructions-node-install) | [Step 7 Change macOS Settings](7-macos-setup-instructions-change-settings)