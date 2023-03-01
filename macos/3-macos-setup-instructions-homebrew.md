# Install Homebrew

[Homebew homepage](https://brew.sh/)

Homebrew is a program that runs in the terminal that developers use to install other programs/software and libraries that we want to use for creating or running our own programs.

Homebrew simplifies installing dependencies.

Homebrew has the following [installation requirements](https://docs.brew.sh/Installation):

- macOS 10.15+ (older versions work)
- A 64-bit Intel CPU or Apple Silicon CPU
- Command Line Tools (CLT) for Xcode (from xcode-select --install or https://developer.apple.com/download/all/)

> Note: If you have macports installed already, please contact the afternoon teachers for support, don't install brew as it might cause conflicts with macports.

1. Launch the Terminal app
2. Paste the following command in the terminal (`CMD+V` or right-click -> paste)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

3. Press enter and wait for the command to complete the installation
4. Type the following command in the terminal and press enter. This will update homebrew

   ```bash
   brew update
   ```

5. You're good to go!

---

[Return to the table of comments at the top of the first page](1-macos-setup-instructions-terminal-setup.md#table-of-contents)

---
| Previous | Next |
| ----- | ---------- |
| [Step 2 Install Git](2-macos-setup-instructions-install-git.md) | [Step 4 Install VS Code](4-macos-setup-instructions-vscode-install.md) |
