# Install git (Command Line Tools)

`git` is a program that allows developers to create snapshots of their code (backups) so that it is very easy to go back to a previous version in case we make some big mistakes in our code, or collaborate with other developers, when we end up writing code in the same files.

On macOS, `git` is installed with the `Command Line Tools` package for `XCode`, which is a required tool to install Homebrew (step 3.)

1. Launch the terminal app
2. Type this command and press enter

   ```bash
   xcode-select --install
   ```

   If you have Command Line Tools already installed, the above command will return an error. You can jump to step 7.

3. If you don't have the tools already installed, a popup will appear. Choose the option `Install`.
4. Wait for the package to download and install.
5. Quit the terminal completely
6. Open the terminal again
7. Check that git is installed by typing the following command

   ```bash
   git --version
   ```

   The above should produce something similar to:

   ```bash
   > git --version
   git version 2.24.3 (Apple Git-128)
   ```

---
| Previous | Next |
| ----- | ---------- |
| [Step 1 Terminal Setup](1-macos-setup-instructions-terminal-setup) | [Step 3 Install Homebrew](3-macos-setup-instructions-homebrew) |
