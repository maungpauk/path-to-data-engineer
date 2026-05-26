<h1 align="center">
    <strong>Linux for Data Engineering</strong>
</h1>

<p align="center">
  <img width="30%" src="/images/linux_penguin.png" alt="linux penguin">
</p>

<h3 align="center">
    <i>____by Maung Pauk</i>
</h3>

---
Linux is the backbone of most data engineering environments—from local development to cloud infrastructure. Many production systems, including servers and containers, run on Linux, so knowing it gives you a practical edge.

## Why Linux matters:

- **Command-line efficiency**  
  The shell (e.g., Bash) lets you automate workflows, manipulate files, and process data quickly using tools like `grep`, `awk`, and `sed`.

- **Automation & scripting**  
  You can write shell scripts to automate ETL tasks, schedule jobs (via `cron`), and manage pipelines.

- **Environment consistency**  
  Most cloud platforms and data tools run on Linux, so developing in Linux reduces “it works on my machine” issues.

- **Tool compatibility**  
  Technologies like Docker, Apache Airflow, and Apache Spark are designed with Linux environments in mind.

- **Resource efficiency & control**  
  Linux gives better control over system resources, permissions, and networking—important when handling large-scale data workloads.

---

## Advantages of Using WSL (Linux on Windows)

WSL (Windows Subsystem for Linux) allows you to run a real Linux environment directly inside Windows without a virtual machine.

### Key advantages:

- **Native Linux experience without dual boot**  
  You can use Ubuntu or other distros alongside Windows—no need to switch operating systems.

- **Seamless integration with Windows tools**  
  Access Windows files from Linux and use editors like Visual Studio Code across both environments.

- **Lightweight compared to virtual machines**  
  WSL uses fewer resources than traditional VMs, making it faster to start and easier to manage.

- **Perfect for learning and development**  
  Practice Linux commands, run Python scripts, and build pipelines in a real Linux-like environment.

- **Great for containerization**  
  Works smoothly with Docker Desktop, enabling you to build and run containers just like in production.

---

## WSL Linux Setup on Windows 11

I am a Windows user and this is a step-by-step notes to install and configure Windows Subsystem for Linux (WSL 2) on Windows 11 for Data Engineering workflows.


### 1. Requirements

Before starting, ensure:

* Windows 11 (Build 22000 or later)
* Virtualization enabled in BIOS (usually enabled by default)
* In the Windows search bar, type 'features' to bring up the Turn Windows Features on and off dialog. Scroll down and check Windows Subsystem for Linux.
<p align="center">
  <img width="60%" src="https://code.visualstudio.com/assets/docs/remote/wsl-tutorial/windows-features.png" alt="windows features">
</p>
  Select OK and you will be prompted to restart Windows.

---

### 2. Install WSL

* Open **PowerShell as Administrator** and run:

  ```PoswerShell
  wsl --install
  ```
  When 'WSL' install is completed, restart computer

* **Verify WSL**
  In PowserShell:
  ```PowerShell
  wsl --version
  ```
  If **WSL** is installed successfully, the following message is appearing:
  ```
  WSL version: 2.6.3.0
  Kernel version: 6.6.87.2-1
  WSLg version: 1.0.71
  MSRDC version: 1.2.6353
  Direct3D version: 1.611.1-81528511
  DXCore version: 10.0.26100.1-240331-1435.ge-release
  Windows version: 10.0.26200.8246
  ```

---

### 3. Install Linux Distribution
  After **WSL** was installed successfully, **Linux Distribution** is needed to install.
  Checking **Linux Distributions** in PowerShell
  ```PowerShell
  wsl -l -o
  ```
  Many **Linux Distributions** are listed.
  I want to install **Ubuntu-24.04 LTS** destro.

  ```PowerShell
  wsl --install Ubuntu-24.04
  ```
  After installation completes, restart your system to apply changes.

---

### 4. Initial Linux Setup

After reboot, Ubuntu (or your chosen Linux distro) will launch.

You will be prompted to:

* Create a Linux username
* Set a Linux password

> Note: This is separate from mu Windows login.

---

### 5. Verify Installation

I run the following command in PowerShell or Windows Terminal:

```bash
wsl -l -v
```

I saw the output like this:

```
  NAME            STATE           VERSION
* Ubuntu-24.04    Running         2
```

And then, enter to wsl like this:
```PowerShell
wsl
```

Now, Linux (Ubuntu) is working well inside WSL terminal:


### 6. Update Linux Packages

Inside the WSL terminal, run:

```bash
sudo apt update && sudo apt upgrade -y
```

---

### 7. Install Essential Data Engineering Tools

Install commonly used tools:

```bash
sudo apt install -y python3 python3-pip git curl wget unzip
```

Optional build tools:

```bash
sudo apt install -y build-essential
```

---

### 8. Install VS Code Integration

Install Visual Studio Code and the **Remote - WSL** extension.

See more details about [*Visual Studio Code (VSCode) installation](03-vscode_setup.md)

Then open WSL projects directly in VS Code:

```bash
code .
```

---

### 9. Docker Integration (Optional but Recommended)

Install Docker Desktop on Windows and enable WSL integration.

This allows running containers directly inside Linux environment.

---

### 10. Set WSL 2 as Default (If Needed)

```bash
wsl --set-default-version 2
```

---

### Best Practices for Data Engineering

* Store projects inside Linux filesystem:

  ```
  /home/your-username/projects
  ```

  (Faster than Windows-mounted drives)

* Use Git inside WSL for production-like workflows

* Keep environment reproducible using requirements files or Docker

---

## Learn and Practice Linux

I red many books about **Linux** and learned lessons.
The followings are essential **Linux skills** for Data Engineers:
- **File System Navigation and Management:** Proficiency in using commands like `ls`, `cd`, `cp`, `mv`, and `rm`
to navigate directories and manage files efficiently. Understanding file permissions (`chmod`) and ownership
(`chown`) is also crucial.

- **Text Processing with Tools like `grep`, `sed`, and `awk`:** These tools are indispensable for data
manipulation, filtering logs, and processing large datasets. Mastery of regular expressions enhances their
effectiveness in searching and transforming text data.

- **Shell Scripting:** Ability to write shell scripts (using bash or similar shells) to automate repetitive tasks
such as backups, data transformations, or deployment pipelines. This skill reduces manual effort and increases
reliability.

- **Process Management with `ps`, `top`, and `htop`:** Understanding how to monitor system processes (`ps`), view
active processes in real-time (`top`/`htop`), and manage services (using `systemctl`) is vital for maintaining
server health and performance.

- **Networking Fundamentals:** Knowledge of basic networking concepts like IP addressing, subnetting, DNS
resolution, and using tools such as `ping`, `traceroute`, and `netstat` to diagnose connectivity issues. This
skill helps in troubleshooting data pipeline failures or service interruptions.

- **Package Management with `apt`, `yum`, and `dnf`:** Familiarity with package managers specific to your Linux
distribution (e.g., `apt` for Debian/Ubuntu, `yum` for Red Hat/CentOS, `dnf` for Fedora) ensures that you can
install, update, or remove software packages efficiently.

- **Security Practices:** Awareness of basic security practices such as using SSH keys for secure connections,
understanding SELinux/AppArmor policies, and implementing file system encryption (e.g., LUKS). These skills
protect data integrity and confidentiality in data engineering environments.

---

### References
- [**How to install Linux on Windows with WSL**](https://learn.microsoft.com/en-us/windows/wsl/install)
- [**The Linux commandline for begnners**](https://documentation.ubuntu.com/desktop/en/latest/tutorial/the-linux-command-line-for-beginners/)
- [**Ubuntu Linux For You** -by Ei Maung](https://eimaung.com/ubuntu-for-you/) - Myanmar Language



---

**[↑ Up](/README.md)** | **[← Previous](01-de_core_concepts_and_theories.md)** | **[Next →](03-vscode_setup.md)**
