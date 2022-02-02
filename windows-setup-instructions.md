# Windows Setup Instructions

There are 5 steps in this guide:

1. Install git & Git Bash
2. Install Visual Studio Code

   3.1 Install VSCode Extensions

3. Install NodeJS
4. Setup SSH Keys for GitHub

   4.1 Add SSH Keys to GitHub
   4.2 Check SSH & GitHub Setup

## 1. Install git & Git Bash

`git` is a program that allows developers to create snapshots of their code (backups) so that it is very easy to go back to a previous version in case we make some big mistakes in our code, or collaborate with other developers, when we end up writing code in the same files.

1. Browse to the [Git Download for Windows page](https://git-scm.com/download/win) and select the `Standalone Installer (64-bit Git)` download - unless you have a `32-bit version of Windows`.
2. Once the download is complete, run it from your browser's download bar.
   1. Select defaults for all options during the installation.
   2. When the imstallation is complete, press the `<Windows>` key and type `git` into the search to find the `git bash` app

      ![Find git bash](images/find-git-bash.png)

   3. Right click on the `git bash` app and click `Pin this program to the taskbar` so you can start it quickly.

      ![Pin git bash](images/pin-git-bash.png)

   4. Click the `git bash` icon in the Taskbar to run it
      1. Type the following text in the `git bash` window and then `<Enter>`
      2. Type `exit` then `<Enter>` to close this window
   5. Now click the `git bash` icon in the Taskbar to run it again
      1. This time you should see some messages like `missing setup message related to .bash_profile`
      2. `git bash` is now set up and ready for the next steps
   6. Exit the `git bash` window by typing `exit` and then `<Enter>`
   7. Open a new `git bash` window by clicking on it's icon in the Windows Taskbar

      1. At the `$` prompt in the new window, type `git --version` and then `<Enter>` to check `git` is correctly installed. You should see something like the following text displayed:

        ```text
        git version 2.35.1.windows.1

        user@PC-NAME MINGW ~
        $
        ```

      2. Finally type `exit` and then `<Enter>` to close the window.

## 2. Install VSCode

[Visual Studio Code](https://code.visualstudio.com) is a code editor. It allows us to manage the files in a project and to edit the code that we write. It comes with a large number of very useful features that make development faster and easier. We can also improve its functionality by installing many extensions.

1. Visit [VSCode's download page](https://code.visualstudio.com/download) and select the `User Installer 64 bit` download - unless you have a `32 bit version of Windows`.
2. Once the download is complete, run it from your browser's download bar.

### 2.1 Install VSCode Extensions

Now follow the instructions for setting up the extensions for VS Code.

[Setup VSCode Extensions](vscode-setup-instructions.md)

## 4. Install NodeJS

[NodeJS](https://nodejs.org/en/) is a runtime environment for JavaScript. It allows us to build and run javascript applications. We shall make extensive use of this throughout the course.

We will use a tool called `nvm` to install NodeJS - [Link to GitHub Repository](https://github.com/nvm-sh/nvm)

1. Open a new `git bash` window by clicking it's icon in the Windows Taskbar - set up in step 1 above.
2. Paste the following command into the `git bash` window

   ```text
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
   ```

## 4. Setup SSH Keys for Github

An SSH key is an access credential for the SSH (secure shell) network protocol. This authenticated and encrypted secure network protocol is used for remote communication between machines on an unsecured open network. SSH is used for remote file transfer, network management, and remote operating system access.

We will need SSH Keys in order to push our code to GitHub.

### 4.1. Adding SSH Keys onto Github account

### 4.2 Check that SSH & Github are setup correctly

In your terminal, run the following command:

`ssh -T git@github.com`

If everything is correctly setup, you should see the following message:

`Hi <YOUR_GITHUB_USERNAME>! You've successfully authenticated, but GitHub does not provide shell access.`
