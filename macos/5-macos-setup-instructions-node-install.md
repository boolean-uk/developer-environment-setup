# Install NodeJS

>[NodeJS](https://nodejs.org/en/) is a runtime environment for JavaScript. It allows us to build and run javascript applications. We shall make extensive use of this throughout the course.

We are following the instructions [from this guide](https://www.taniarascia.com/setting-up-a-brand-new-mac-for-development/#nodejs) to install NodeJS on our machine. The summary of the instructions is below.

> **DO NOT** install Node via the NodeJS website. If you are are getting an error in your terminal following the steps in this guide use the support channel and ask for help
---
## Install NVM

   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
   ```

   If you get an error that `curl` is not installed, you can run 
   ```bash
   brew install curl
   ```

   You might get a message telling you the installation could not complete because of a missing configuration file:

   ```bash
   ... more output
   => Profile not found. Tried ~/.bashrc, ~/.bash_profile, ~/.zshrc, and ~/.profile.
   => Create one of them and run this script again
   OR
   => Append the following lines to the correct file yourself:
   ... more output
   ```

   If the above occurs, run the command 
   ```bash
   touch ~/.bashrc
   ``` 
   then repeat the `curl` command of step 1 to re-run the `nvm` installation.

   

- [ ] Quit the terminal completely and relaunch it.
- [ ] Type `nvm -v` in the terminal. You should see an output with some version ex. `1.1.10`
- [ ] If the above does not work go to Troubleshoot guide, else if it displays a version go to next section
### Troubleshoot if nvm does not work

> **IMPORTANT NOTE** If the above command returns an output saying `command not found: nvm`
> In this case we need to define if our terminal is using `bash` or `zsh`.

Type in the terminal

```bash
which $SHELL
```

There are 2 possible outcomes from the above command

bash:

```text
   /usr/bin/bash
```

zsh:

```text
   /bin/zsh
```

Open the file based on the terminal that you have based on the above output

bash:

```bash
   touch ~/.bashrc
```

```bash
   code ~/.bashrc
```

zsh:

```bash
   touch ~/.zshrc
```

```bash
   code ~/.zshrc
```
Add the following code in the end of that file, without touching anything else in there
```text
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

---
## Install the latest version of NodeJS

   ```bash
   nvm install --lts
   ```
---
- [ ] Restart terminal and run the final command.

   ```bash
   nvm use --lts
   ```

- [ ] Confirm that you are using the latest version of Node and npm. Version 16 is the latest stable. If you installed version 17 for Node, that is also OK. `npm` should be version 8+.

   ```bash
   node -v && npm -v
   ```

Further reading on nvm: [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

---

[Return to the table of comments at the top of this page](#table-of-contents)

---
| Previous | Next |
| ----- | ---------- |
| [Step 4 Install VS Code](4-macos-setup-instructions-vscode-install.md) | [Step 6 Setup SSH Keys for Github](6-macos-setup-instructions-setup-ssh.md) |