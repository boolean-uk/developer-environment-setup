# Windows Setup Instructions

## 3. Install NVM and NodeJS

[NodeJS](https://nodejs.org/en/) is a runtime environment for JavaScript. It allows us to build and run javascript applications. We shall make extensive use of this throughout the course.

We will use a tool called `nvm` to install NodeJS - [Link to GitHub Repository](https://github.com/nvm-sh/nvm)

1. Open a new `git bash` window by clicking it's icon in the Windows Taskbar - set up in step 1 above.
2. Paste the following command into the `git bash` window

   ```text
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

   ```

3. Once the above completes, close the current `git bash` window and open a new one before you continue.
4. Install the latest version of NodeJS

   `nvm install --lts`

   **Note**: it might take a few seconds before any output starts to appear in the terminal.

5. Restart terminal and run the final command.

   `nvm use --lts`

6. Confirm that you are using the latest version of Node and npm. Version 16 is the latest stable. If you installed version 17 for Node, that is also OK. `npm` should be version 8+.

   `node -v && npm -v`

Further reading on nvm: [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

| Previous | Next |
| ----- | ---------- |
| [Step 2 Install git & Git Bash](windows-setup-instructions-step-2) | [Step 4 Setup SSH Keys for Github](windows-setup-instructions-step-3)