<h1 align="center">
    <strong>VSCode Setup</strong>
</h1>
<h3 align="center">
    <i>____by Maung Pauk</i>
</h3>

---


## Visual Studio Code (VS Code)

I choose Visual Studio Code (VS Code) over other **Integrated Development Environment (IDE)** like Eclipse, IntelliJ IDEA, Sublime Text, Cursor, or Antigravity primarily due to its lightweight performance, extensive extensibility via a vast marketplace of extensions for virtually any programming language or tooling need, and strong support for collaborative development through built-in Git integration and remote development capabilities. Its adaptability across various operating systems, coupled with regular updates from the VS Code team, ensures you have access to cutting-edge features without sacrificing performance or stability—making it a versatile choice for developers of all skill levels in diverse environments.

## Setup VS Code

* Open **PowerShell as Administrator** and run:
```PowerShell
winget install Microsoft.VisualStudioCode
```

* Enter wsl and make a directory and change directory in it:

```bash
mkdir projects && cd projects
```

And then open **VS Code**:

```bash
code .
```
> *code (dot) means open VS Code in current directory*

When VS Code is opened, click extensions icon in the left-hand side or Ctrl+Shift+X. And find **'WSL'** extension and install it.

Then press `F1` and type `>WSL: Connect to wsl` in **Quick Access** bar and click to connect.

**Done !**

---

**[↑ Up](/README.md)** | **[← Previous](02-linux_setup_for_de.md)** | **[Next →](04-SQL.md)**