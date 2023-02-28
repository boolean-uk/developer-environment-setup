# Windows Setup Instructions

There are 4 steps in this guide:

1. Install git & Git Bash
2. Install Visual Studio Code

   2.1 Install VSCode Extensions
   2.2 Set Default Terminal in VSCode to Git Bash

3. Install NVM and NodeJS
4. Setup SSH Keys for GitHub

   4.1 Add SSH Keys to GitHub
   4.2 Check SSH & GitHub Setup
   4.3 Add Your Identity Details for Git Operations

## 1. Install git & Git Bash
---
> `git` is a program that allows developers to create snapshots of their code (backups) so that it is very easy to go back to a previous version in case we make some big mistakes in our code, or collaborate with other developers, when we end up writing code in the same files.

1. Browse to the [Git Download for Windows page](https://git-scm.com/download/win) and select the `Standalone Installer (64-bit Git)` download - unless you have a `32-bit version of Windows`.

2. Once the download is complete, run it from your browser's download bar.

   1. **Select defaults for all options during the installation**.

   2. When the installation is complete, press the `<Windows>` key and type `git` into the search box to find the `git bash` app

      ![Find git bash](images/find-git-bash.png)

   3. Right click on the `git bash` app and click `Pin to taskbar` so you can start it quickly from the Taskbar.

      ![Pin git bash](images/pin-git-bash.png)

   4. Click the `git bash` icon in the Taskbar to run it

      1. Type the following text in the `git bash` window and then `<Enter>`

         ```bash
         touch .bashrc
         ```

         >If you get **an error stating** that you don't have permissions to create the file, then it is likely `git bash` did not launch from the correct folder. Make sure you followed steps 2 and 3 above, if not seek support.

      2. Type `exit` then `<Enter>` to close this window

   5. Now click the `git bash` icon in the Taskbar to run it again

      1. This time you should see some messages like `missing setup message related to .bash_profile`

         ![Bash warnings](images/bashrc-warning.png)

      2. The warning message tells us `git bash` is now set up properly and we are ready for the next steps.

   5. Exit the `git bash` window by typing `exit` and then `<Enter>`.
   6. Open a new `git bash` window by clicking on it's icon in the Windows Taskbar. This time, you should not see the warning above.

      1. At the `$` prompt in the new window, type `git --version` and then `<Enter>` to check `git` is correctly installed. You should see something like the following text displayed:

         ```text
         git version 2.35.1.windows.1

         user@PC-NAME MINGW ~
         $
         ```

      2. Finally type `exit` and then `<Enter>` to close the window.

| Previous | Next |
| ----- | ---------- |
| - | [Step 2 Install VSCode](windows-setup-instructions-step-2) |
