# Windows Setup Instructions

## Install NVM and NodeJS

>[NodeJS](https://nodejs.org/en/) is a runtime environment for JavaScript. It allows us to build and run javascript applications. We shall make extensive use of this throughout the course.

We will use a tool called `nvm` to install NodeJS - [Link to GitHub Repository](https://github.com/nvm-sh/nvm)

- [ ] Open a new `git bash` window by clicking it's icon in the Windows Taskbar - set up in [Step 1 Install git & Git Bash](windows-setup-instructions-step-1/### Open git Bash
)

- [ ] Paste the following command into the `git bash` window

   ```text
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
   ```

- [ ] Once the above completes, close the current `git bash` window and open a new one before you continue.
- [ ] Install the latest version of NodeJS

   ```js
   nvm install --lts
   ```

   **Note**: it might take a few seconds before any output starts to appear in the terminal.


- [ ] Restart terminal and run the final command.
   ```js
   nvm use --lts
   ```

- [ ] Confirm that you are using the latest version of Node and npm. Version 16 is the latest stable. If you installed version 17 for Node, that is also OK. `npm` should be version 8+.
   ```js
   node -v && npm -v
   ```

> Further reading on nvm: [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

---

[Return to the table of comments at the top of this page](#table-of-contents)

---
| Previous | Next |
| ----- | ---------- |
| [Step 2 Install git & Git Bash](2-windows-setup-instructions-vscode-install.md) | [Step 4 Setup SSH Keys for Github](4-windows-setup-instructions-setup-ssh.md)