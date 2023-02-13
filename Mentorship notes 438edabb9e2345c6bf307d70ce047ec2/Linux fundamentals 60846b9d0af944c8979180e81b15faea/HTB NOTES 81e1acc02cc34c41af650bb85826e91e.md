# HTB NOTES

| Principle | Decription |
| --- | --- |
| Everything is a file | All configuration files for the various services running on the Linux operating system are stored in one or more text files. |

## **Architecture**

[Untitled](HTB%20NOTES%2081e1acc02cc34c41af650bb85826e91e/Untitled%20Database%205a36d5d91b2846fbaaa2d0abdbde7911.csv)

## **File System**

| Path | Description |
| --- | --- |
| / | The top-level directory is the root filesystem and contains all of the files required to boot the operating system before other filesystems are mounted as well as the files required to boot the other filesystems. After boot, all of the other filesystems are mounted at standard mount points as subdirectories of the root. |
| /bin | Contains essential command binaries. |
| /boot | Consists of the static bootloader, kernel executable, and files required to boot the Linux OS. |
| /dev | Contains device files to facilitate access to every hardware device attached to the system. |
| /etc | Local system configuration files. Configuration files for installed applications may be saved here as well. |
| /home | Each user on the system has a subdirectory here for storage. |
| /lib | Shared library files that are required for system boot. |
| /media | External removable media devices such as USB drives are mounted here. |
| /mnt | Temporary mount point for regular filesystems. |
| /opt | Optional files such as third-party tools can be saved here. |
| /root | The home directory for the root user. |
| /sbin | This directory contains executables used for system administration (binary system files). |
| /tmp | The operating system and many programs use this directory to store temporary files. This directory is generally cleared upon system boot and may be deleted at other times without any warning. |
| /usr | Contains executables, libraries, man files, etc. |
| /var | This directory contains variable data files such as log files, email in-boxes, web application related files, cron files, and more. |

## **command for System Infomation**

| Command | Description |
| --- | --- |
| whoami | Displays current username. |
| id | Returns users identity. |
| hostname | Sets or prints the name of current host system. |
| uname | Prints operating system name. |
| pwd | Returns working directory name. |
| ifconfig | The ifconfig utility is used to assign or to view an address to a |
| ip | Ip is a utility to show or manipulate routing, network devices, |
| netstat | Shows network status. |
| ss | Another utility to investigate sockets. |
| ps | Shows process status. |
| who | Displays who is logged in. |
| env | Prints environment or sets and executes command. |
| lsblk | Lists block devices. |
| lsusb | Lists USB devices |
| lsof | Lists opened files. |
| lspci | Lists PCI devices. |

### **Systemctl**

The main command used to introspect and control systemd is **systemctl**. Some of its uses are examining the system state and managing the system and services. See systemctl(1) for more details.

### **Background Proccess**

Sometimes it will be necessary to put the scan or process we just started in the background to continue using the current session to interact with the system or start other processes. As we have already seen, we can do this with the shortcut [Ctrl] + Z. As mentioned above, we send the SIGTSTP signal to the kernel, which suspends the process.

### **Foreground Proccess**

After that, we can use the jobs command to list all background processes. Backgrounded processes do not require user interaction, and we can use the same shell session without waiting until the process finishes first. Once the scan or process finishes its work, we will get notified by the terminal that the process is finished.

### **Execute Multiple Commands**

There are three possibilities to run several commands, one after the other. These are separated by:

- Semicolon (;)
- Double ampersand characters (&&)
- Pipes (|)

### **wget**

An alternative to curl is the tool wget. With this tool, we can download files from FTP or HTTP servers directly from the terminal and serves as a good download manager. If we use wget in the same way, the difference to curl is that the website content is downloaded and stored locally.

### **cURL**

cURL is a tool that allows us to transfer files from the shell over protocols like HTTP, HTTPS, FTP, SFTP, FTPS, or SCP. This tool gives us the possibility to control and test websites remotely. Besides the remote servers’ content, we can also view individual requests to look at the client’s and server’s communication. Usually, cURL is already installed on most Linux systems.

### **npm, Node Package Manager**

npm is a package manager for the JavaScript programming language.My understanding is npm is knida like git, apt or dkpg, as they are all package manager tools.

npm is the default package manager for the JavaScript runtime environment Node.js. It consists of a command line client, also called npm, and an online database of public and paid-for private packages, called the npm registry. The registry is accessed via the client, and the available packages can be browsed and searched via the npm website. The package manager and the registry are managed by npm, Inc.

### **3 way to start http-server**

Below shows 3 very quick and different ways that you can start up a HTTP Web Server from the terminal on your local machine:

- PHP
- Python
- NodeJs

## **Navigation & Files**

### **which**

One of the common tools is **which**. This tool **returns the path to the file or link that should be executed**. This allows us to determine if specific programs, like cURL, netcat, wget, python, gcc, are available on the operating system. Let us use it to search for Python in our interactive instance.

If the program we search for does not exist, no results will be displayed.

### **find**

Another handy tool is find. Besides the function to find files and folders, this tool also contains the function to filter the results. We can use filter parameters like the size of the file or the date. We can also specify if we only search for files or folders.

| Option | Description |
| --- | --- |
| -type f | Hereby, we define the type of the searched object. In this case, ‘f’ stands for ‘file’. |
| -name *.conf | With ‘-name’, we indicate the name of the file we are looking for. The asterisk (*) stands for ‘all’ files with the ‘.conf’ extension. |
| -user root | This option filters all files whose owner is the root user. |
| -size +20k | We can then filter all the located files and specify that we only want to see the files that are larger than 20 KiB. |

### **locate**

It will take much time to search through the whole system for our files and directories to perform many different searches. The command locate offers us a quicker way to search through the system. In contrast to the find command, **locate works with a local database that contains all information about existing files and folders**. We can update this database with the following command.You will find that this search produces results **much faster** than using find.

### **head**

Sometimes we will only be interested in specific issues either at the beginning of the file or the end. If we only want to get the first lines of the file, we can use the tool head. **By default, head prints the first ten lines** of the given file or input, if not specified otherwise.

### **tail**

Opposite to head, which returns the last ten lines.

### **sort**

Depending on which results and files are dealt with, they are rarely sorted. Often it is necessary **to sort the desired results alphabetically or numerically to get a better overview**. For this, we can use a tool called sort.

### **grep**

More often, we will only search for specific results that contain patterns we have defined. One of the most used tools for this is grep, which offers many different features.

### **cut**

Specific results with different characters may be separated as delimiters. Here it is handy to know how to remove specific delimiters and show the words on a line in a specified position. One of the tools that can be used for this is cut. Therefore we use the option “-d” and set the delimiter to the colon character (:) and define with the option “-f” the position in the line we want to output.

### **tr**

Another possibility **to replace certain characters** from a line with characters defined by us is the tool tr. As the first option, we define which character we want to replace, and as a second option, we define the character we want to replace it with. In the next example, we replace the colon character with space.

### **column**

Since such results can often have an unclear representation, the tool column is well suited to **display such results in tabular form using the “-t”**.

### **awk**

Awk **is a scripting language** used for manipulating data and generating reports. **Mostly used for pattern scanning** and processing. It searches one or more files to see if they contain lines that matches with the specified patterns and then performs the associated actions.

### **sed**

This is the **stream editor** called sed. One of the **most common uses of this is substituting text**. Here, sed looks for patterns we have defined in the form of **regular expressions** (regex) and replaces them with another pattern that we have also defined. Let us stick to the last results and say we want to replace the word “bin” with “HTB.”

### **wc**

To avoid counting the lines or characters manually, we can use the tool wc. With the “-l” option, we specify that only the lines are counted.