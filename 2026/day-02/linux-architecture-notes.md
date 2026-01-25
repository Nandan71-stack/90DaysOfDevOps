What is Linux:

Open source Software, Developed by Linus Torwalds 1n 1991.
Notes:
A. Everything in linux is either a file or directory.
B. Everything starts with a process.


syntax for Linux command help.

man <command_name>
man mkdir

bin --> binaries.
sbin--> system binaries.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Linux Architecture:
A --> Application
S --> Shell
K --> Kernel
H -->  Hardware

Applications
A. Description: These are the software programs that users interact with directly, such as web browsers, text editors, or graphical user interfaces (GUIs).
B. Function: Applications run in "user mode" and rely on the shell, system libraries, and the kernel to access hardware resources and perform tasks. 

Shell
A. Description: The shell is an interface that surrounds the kernel and acts as an intermediary between the user and the kernel.
B. Function: It takes human-readable commands from the user (via a command-line interface like Bash or Zsh) and interprets them into instructions that the kernel can understand and execute. 

Kernel
A. Description: The kernel is the core component of the operating system. It sits directly on top of the hardware layer.
B. Function: It acts as the bridge between the hardware and the software. The kernel is responsible for managing system resources, including memory management, process scheduling, and device management (via device drivers). It runs in a privileged "kernel mode" with full access to all system resources to protect the system's integrity. 


Hardware
A. Description: This is the lowest or innermost layer, consisting of the physical components of the computer system.
B. Function: It includes tangible devices like the CPU (Central Processing Unit), RAM (memory), hard disk drives, and other peripheral input/output devices like printers or terminals. 

Utilities
A. Description: Utilities are specialized programs that perform individual, system-level tasks.
B. Function: These are tools that users and administrators use for system management and maintenance, such as file management commands (ls, cp, rm), network configuration tools, and package managers. 


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


How Processes are Created and Managed
Processes in Linux are instances of running programs that the kernel manages. Each has a unique PID. 
Creation (fork() and exec()): New processes are typically created using a two-step mechanism:

1. fork(): A running process makes a fork() system call to create an almost identical child process. Both parent and child run the same code from the point of the call, but with different return values from the fork() function, allowing their execution to diverge.
2. exec(): Immediately after fork(), the child process typically uses an exec() system call to load a new program into its memory space, replacing its original image with the new executable. The PID remains the same, but the running program changes.

Management: The kernel's process scheduler manages which process gets CPU time. The parent process often uses the wait() system call to pause its own execution until its child process finishes. Processes can communicate using signals (e.g., kill sends a termination signal)


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Linux Commands and processes.


1-->

Process Creation Flow
You type a command:

nginx

The shell calls fork() → creates a copy of the current process
Then exec() replaces it with the new program
Kernel assigns:
• PID (Process ID)
• Memory space
• CPU time

2-->

What systemd Does & Why It Matters
systemd manages everything that runs in the background.
🔹 What systemd Controls
• Web servers (nginx, apache)
• Databases (mysql, postgres)
• Docker
• SSH
• Cron timers
• Networking

Each service is defined by a unit file:

5 linux commands.
A. cd (change directories)
B. mkdir (make directories)
C rm (remove files)
D. mv (mv old_name new_name, mv filename <path>)
E. touch (touch file_name.txt)

