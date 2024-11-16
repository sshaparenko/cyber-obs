---
date: 2024-10-20T15:50
tags:
  - "#linux"
cssclasses:
  - pen-purple
  - page-grid
---
#### Terminology
***
**Bootloader** - 

#### Philosophy
***

| Principle                                                       | Description                                                                                                                                                   |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Everything is a file**                                        | All configuration files for the various services running on the Linux OS are stored in one or more text files                                                 |
| **Small, single-purpose programs**                              | Linux offers many different tools that we will work with, which can be combined to work together                                                              |
| **Ability to chain programs together to perform complex tasks** | The integration and combination of different tools enable us to carry out many large and complex tasks, such as processing or filtering specific data results |
| **Avoid captive user interfaces**                               | Linux is designed to work mainly with the shell, which gives the user greater control over OS                                                                 |
| **Configuration data stored in a text file**                    | An example is `/etc/passwd` file, which stores all the registered users                                                                                       |

#### Components
***

| Component          | Description                                                                                                                                                                                                                               |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Bootloader**     | A piece of code that runs to guide the booting process to start the OS. Parrot Linux uses the GRUB Bootloader                                                                                                                             |
| **OS Kernel**      | The kernel is the main component that manages the resources of system’s I/O devices at the hardware level                                                                                                                                 |
| **Daemons**        | Background services are called “daemons“ in Linux. Their purpose is to ensure that key functions such as scheduling, printing and multimedia are working correctly. This small programs are loaded after we booted or log into the system |
| **OS Shell**       | OS Shell is the interface between the OS and the user. The most commonly used shells are `Bash`, `Tcsh/Csh`, `Ksh`, `Zsh` and `Fish`                                                                                                      |
| **Graphic server** | This provides a graphical sub-system called “X“ or “X-Server“ that allows graphical programs to run locally or remotely on the X-windowing system                                                                                         |
| **Window Manager** | Also known as GUI. There are many options including `GNOME`, `KDE`, `MATE`, `Unity` and `Cinnamon`                                                                                                                                        |
| **Utilities**      | Applications or utilities are programs that perform particular functions for the user or another program                                                                                                                                  |

### Linux Architecture
***

| Layer              | Description                                                                                                                                                                                                                                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Hardware**       | Peripheral devices such as system’s RAM, hard drive, CPU and others                                                                                                                                                                                                                |
| **Kernel**         | The core of the Linux OS whose function is to virtualize and control common computer hardware resources like CPU, allocated memory, accessed data and others. The kernel gives each process its own virtual resources and prevents/mitigates conflicts between different processes |
| **Shell**          | A command line interface also known as a shell that a user can enter commands into to execute the kernel’s functions                                                                                                                                                               |
| **System Utility** | Makes available to the user all of the operating system’s functionality                                                                                                                                                                                                            |

#### File System Hierarchy
***

| Path       | Description                                                                                                                                                                                                                                                               |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **/**      | root directory, that contains all of the files required to boot the OS before other filesystems are mounted, as well as the files required to boot other filesystems. After boot, all other filesystems are mounted at standard mount point as subdirectories of the root |
| **/bin**   | contains essential command binaries                                                                                                                                                                                                                                       |
| **/boot**  | contains the static bootloader, kernel executable and files required to boot the Linux OS                                                                                                                                                                                 |
| **/dev**   | contains device files to facilitate access to every hardware device attached to the system                                                                                                                                                                                |
| **/etc**   | local system configuration files. Configuration files for installed apps may be stored here as well                                                                                                                                                                       |
| **/home**  | each user on the system has a subdirectory here for storage                                                                                                                                                                                                               |
| **/lib**   | shared library files that are required for system boot                                                                                                                                                                                                                    |
| **/media** | external removable media devices such as USB Drivers are mounted here                                                                                                                                                                                                     |
| **/mnt**   | temporary mount point for regular filesystems                                                                                                                                                                                                                             |
| **/opt**   | Optional files such as third-party tools can be saved here                                                                                                                                                                                                                |
| **/root**  | the home dir for root user                                                                                                                                                                                                                                                |
| **/sbin**  | contains executables used for system administration (binary system files)                                                                                                                                                                                                 |
| **/tmp**   | OS and many programs use this dir to store temporary files. This dir is generally cleared upon system boot and may be deleted at other times without warning                                                                                                              |
| **/usr**   | contains executables, libraries, man files, etc.                                                                                                                                                                                                                          |
| **/var**   | contains variable data files such as log files, email in-boxes web application related files, cron files and more                                                                                                                                                         |
