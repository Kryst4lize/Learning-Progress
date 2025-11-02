- **Operating System (OS)**: Software that manages computer hardware and resources, allowing interaction to perform tasks.
    
- **Unix**: A family of operating systems originating in the 1960s at AT&T Bell Labs. Notable Unix-based systems include:
    
    - Oracle Solaris
    - FreeBSD
    - HP-UX
    - IBM AIX
    - Apple macOS
- **Linux**: A family of Unix-like operating systems developed as a free, open-source alternative to Unix. Key features include:
    
    - Free and open-source
    - Multi-user support
    - Multitasking capabilities
    - Portability across various hardware
- **History of Linux**:
    
    - 1980s: Development of GNU at MIT, which stands for "GNU's Not Unix."
    - 1991: Linus Torvalds created the Linux kernel.
    - 1992: Unification of GNU and the Linux kernel led to popular Linux distributions.
    - 1996: Introduction of Tux, the Linux mascot.
- **Current Use Cases for Linux**:
    - Billions of smartphones use Linux via Android.
    - Widely used in supercomputers for high-performance computing.
    - Dominates enterprise and cloud data centers.
    - Increasingly popular as a desktop OS for personal use.
---
## Distribution
- **Definition**: A Linux distribution (or "distro") is a specific version of the Linux operating system that includes the Linux kernel and a unique set of default utilities.
- **Differentiation**: Linux distros vary based on:
    
    - Default utilities and applications
    - Graphical user interface (GUI)
    - Supported shell commands
    - Levels of support (community-backed or commercial)
- **Popular Linux Distributions**:
    - **Debian**: Known for stability and reliability; widely used in server environments.
    - **Ubuntu**: Based on Debian; offers editions for desktop, server, and IoT.
    - **Red Hat Linux**: Focused on enterprise customers; known for stability and reliability.
    - **Fedora**: Actively developed with a strong community; known for security features.
    - **SUSE Linux Enterprise**: Supports various architectures; offers server and desktop editions.
    - **Arch Linux**: Highly customizable; requires strong Linux knowledge to use effectively.
--- 
## Linux Architecture
- **Linux System Architecture**:
    
    - Comprises five layers:
        1. **User Interface (UI)**: Allows user interaction via keyboard/mouse.
	        Allow user to interact with the machine
	        GUI (Graphic User Interface)
        1. **Application Layer**: Includes system daemons, shells, and user applications.
        2. **Operating System (OS)**: Manages system stability, job scheduling, and file management.
        3. **Linux Kernel**: Core component responsible for memory management, process management, and security.
        4. **Hardware Layer**: Physical components like CPU, RAM, and storage devices.
- **Linux Filesystem**:
    
    - Organized in a tree-like structure with the root directory (/) at the top.
    - Key directories include:
        - `/bin`: User binary files.
        - `/usr`: User programs.
        - `/home`: Personal working directory.
        - `/boot`: System boot files.
        - `/media`: Temporary media files.
---
## Terminal File Editor
- **Text Editors Overview**:
    
    - Two main categories: Command-line text editors and GUI text editors.
- **Popular Command-line Text Editors**:
    
    - **GNU Nano**:
        - User-friendly, modeless text editor.
        - Features: Undo/redo, search/replace, syntax highlighting, automatic indentation, line numbering, and multiple buffers.
        - To open a file:
            ```bash
            nano filename
            ```
    - **Vim**:
        - Powerful, traditional command-line editor.
        - Operates in two modes: Insert mode (for entering text) and Command mode (for other operations).
        - Basic commands:
            - Enter Insert mode: Press `i`
            - Save file: `:w filename`
            - Quit: `:q`
            - Quit without saving: `:q!`
- **Popular GUI Text Editor**:
    - **Gedit**:
        - Default editor in GNOME environment.
        - Features: Integrated file browser, undo/redo, search/replace, extensibility with plugins, and syntax color coding.
---
## Installing Software and Updates in Linux

**Overview of Packages and Package Managers**

- Software updates and installations in Linux are handled through packages, which are archive files containing the necessary components for software management.
- Package managers are tools that manage the download and installation of these packages, and they vary between different Linux distributions.

**Types of Packages**

- **Deb Packages (.deb)**: Used by Debian-based distributions such as Debian, Ubuntu, and Mint.
- **RPM Packages (.rpm)**: Used by Red Hat-based distributions like CentOS, RHEL, Fedora, and openSUSE.
- The contents of .deb and .rpm files can be converted using the **alien tool** if a package is only available in the other format.

**Benefits of Package Managers**

- Automatically resolve dependencies between packages.
- Notify users when updates are available.
- GUI-based package managers can check for security and software updates regularly.
- Allow users to select specific updates to install.

**Popular Package Managers**

- **GUI-based Managers**:
    
    - **Update Manager**: For deb-based systems, checks for updates daily and installs security updates automatically.
    - **PackageKit**: For RPM-based systems, checks for updates at configurable intervals and allows manual checks.
- **Command-Line Tools**:
    - **apt**: For deb-based systems.
        - Use `sudo apt update` to find available packages.
        - Use `sudo apt upgrade` to upgrade all installed packages.
        - Use `sudo apt install package_name` to install a specific package.
    - **yum**: For RPM-based systems.
        - Use `sudo yum update` to update all packages.
        - Confirms updates before downloading and installing.

**Example of Using Package Managers**

- For Python environments, package managers like pip can be used to install libraries.
    - Example command:
    ```python
    pip install pandas
    ```
---
