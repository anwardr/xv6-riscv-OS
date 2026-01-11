# How to compile & run xv6-riscv on Ubuntu

To compile and run xv6-riscv on Ubuntu 24.04 LTS (we only test this version), follow these steps:

1. Install the necessary dependencies: Open a linux terminal and execute the following commands to update your package list and install the required packages:
```bash
sudo apt update
sudo apt install -y build-essential gcc-riscv64-linux-gnu qemu-system-riscv64 gdb-multiarch
```
These packages include essential build tools, the RISC-V cross-compiler, QEMU for RISC-V emulation, and GDB for debugging.

2. Build xv6-riscv: The xv6-riscv source code is already available in your GitHub repository. Copy the Git clone link of your repository and issue the Git clone command as:

```bash
git clone <repository-url>
cd <os-repository>
make clean
make qemu
```

After running make qemu, you should see the following output indicating that the xv6 kernel is booting, which completes the OS installation.
```bash
xv6 kernel is booting
hart 2 starting
hart 1 starting
init: starting sh
```

# How to compile and run xv6-riscv on Windows

To compile and run xv6-riscv on Windows, you need to use the Windows Subsystem for Linux (WSL) with Ubuntu.

## Step 1: Install WSL

Open PowerShell as an administrator and run the following command:
```bash
wsl --install
```
Follow the on-screen instructions to complete the installation. This will automatically install Ubuntu on your machine. You may need to restart your computer after installation.

Now type the following:

```bash
wsl
sudo apt update
sudo apt install -y build-essential gcc-riscv64-linux-gnu qemu-system-riscv64 gdb-multiarch

```

## Step 2: Clone the repository inside WSL

Go to WSL terminal and clone the repository as the following:

Open the Ubuntu terminal (search for "Ubuntu" in the Start menu) and clone the repository:

```bash
git clone <repository-url>
cd <os-repository>
make clean
make qemu
```



## Step 3: Open the repository in VS Code

From the WSL terminal, navigate to the repository directory and open it in VS Code:
```bash
code .
```
This will launch VS Code with OS files.

## Step 4: Use the correct terminal in VS Code

> **Important:** The default terminal in VS Code on Windows is PowerShell, which will not work for compiling xv6-riscv. You must use the WSL terminal instead.

To switch to the WSL terminal in VS Code:
1. Open the terminal in VS Code (`Ctrl + `` ` ``)
2. Type `wsl` in the terminal and press Enter to switch to Ubuntu

## Step 5: Compile and run xv6-riscv

Follow the steps outlined in the "How to compile & run xv6-riscv on Ubuntu" section above to install dependencies and compile xv6-riscv.

# How to compile and run xv6-riscv on macOS

To compile and run xv6-riscv on macOS, you can use Homebrew to install the necessary dependencies. Follow these steps to set up xv6-riscv on macOS:

1. Install Homebrew: Open a terminal and run the following command to install Homebrew, a package manager for macOS:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Follow the on-screen instructions to complete the installation.

2. Install the necessary dependencies: Run the following command in the terminal to install the required packages using Homebrew:
```bash
brew install riscv-gnu-toolchain qemu
```
3. Follow the steps outlined in the "How to compile & run xv6-riscv on Ubuntu" section above to compile and run xv6-riscv on macOS.
