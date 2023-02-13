# Bandit solutions

# level 0

- Command `man ssh`tells us about ssh.

an address - *bandit.labs.overthewire.org*, port - *2220*, username - *bandit0* and password – *bandit0*. The option `-p` is tell the port to connect and the general command to connect is `ssh username@address -p port`

So the command to connect to bandit server is :

`ssh bandit0@bandit.labs.overthewire.org -p 2220`

# level 0-1

- `ls`command is used to see list of files and subdirectories

`cat`  used to view the content of a file.

There is a file *readme*
 in the current working directory which is */home/bandit0*
. The *readme* file stores the password for level 1.

# level 1-2

- Command to connect remote host : `ssh bandit1@bandit.labs.overthewire.org -p 2220`

In UNIX and Linux, a filename can start with – (dash) or can be just – (dash). Above it is given that the file is called – (dash).

But content of the file – can not be displayed using command `cat –` because it reads from standard input and it is waiting for us to type something.

So to view the content of the file - , the path to the file is prefixed with the filename.

`cat ./-`

The password for the next level is `****` .

# level 2-3

- 

Command to connect remote host : `ssh bandit2@bandit.labs.overthewire.org -p 2220` password is `****` .

When we run the `ls` command we find that the name of the file is *spaces in this filename* means there are spaces in the filename.

When there are spaces in a filename use **\** after every word.

“A non-quoted backslash (\) is the escape character. It preserves the literal value of the next character that follows, with the exception of `<newline>`.”

The command is

`cat spaces\ in\ this\ filename`

Since in that directory there is only file we can also use *tab button*, after typing s, which writes the full name of file which starts with s.

The password for the next level is `****` .

# level 3-4

Command to connect remote host : `ssh bandit3@bandit.labs.overthewire.org -p 2220` password is `****` .

`cd` command is used to change our current working directory. `cd` is followed by the pathname of the desired working directory.

Our current working directory is */home/bandit3* and our desired working directory is */home/bandit3/inhere* . So we can either use command `cd inhere/` or `cd /home/bandit3/inhere/`

It is given that the password is stored in the hidden file and after running command `ls` we do not find any file in the directory. Files whose name starts with a period (**.**) are hidden file and command `ls -a` list all files, even those with names that begin with a period, which are normally not listed (i. e., hidden). So the name of the file is *.hidden* and command `cat .hidden` is used to see the content of the file. The password to the next level is `****` .

# level 4-5

- 

Command to connect remote host : `ssh bandit4@bandit.labs.overthewire.org -p 2220` password is `****` .

`file` command is used to determine a file’s type or what file contains.

In *inhere* directory, there are 10 files *-file00, -file01, …, -file09*. The human-readable file means the content of that file is ASCII and we can find the type of content of a file by running command

`file ./-file00`

`file ./-file01`

…

`file ./file07`

We found that *-file07* contains ASCII text.

Instead of checking each file we can use `find` and `xargs` command.

`find` program searches a given directory (and its subdirectories) for files based on a variety of attributes.

Command `find . -type f` searches all regular files in the current directory. Current directory is specified by . (dot).

The `xargs` command performs an interesting function. It accepts input from standard input and converts it into an argument list for a specified command.

Command `find . -type f | xargs file` finds all the regular files in the current directory and `xargs` constructs an argument list for `file` command and then executes it.

The password for the next level is `****` .

# level 5-6

- Command to connect remote host : `ssh bandit5@bandit.labs.overthewire.org -p 2220` password is `****` .

In manual pages of `find` command it is mentioned that option `-size` is used to specify size of the file and `c` is used for bytes. `-executable` matches the executable files, so `! -executables` matches the non executable files. We then pipe this output to `xargs` command which tells the content of the file found. Command is

`find . -type f -size 1033c ! - executable | xargs file`

The password for the next level is `****` .

# level 6-7

- 

Command to connect remote host : `ssh bandit6@bandit.labs.overthewire.org -p 2220` password is `****` .

Since the password is stored *somewhere on the server*. Lets go to the root directory by running command `cd ..` two times.

From manual page of `find` command :

- `user` *uname*File is owned by user uname (numeric user ID allowed).`size` *n[cwbkMG]*File uses n units of space, rounding up. The following suffixes can be used:‘c’ for bytes`group` *gname* File belongs to group gname (numeric group ID allowed).

From the given, `uname` is *bandit7*, `gname` is *bandit6* and `n` is *33c*.

We want file with ASCII content and `xargs file` will tell us about that.

So the command is :

`find -user bandit7 -group bandit6 -size 33c | xargs file`

The password for the next level is `****` .

# level 7-8

- 

Command to connect remote host : `ssh bandit7@bandit.labs.overthewire.org -p 2220` password is `****` .

Here we can use `grep` program. `grep` is used to find text patterns within file. The text we have to find is *millionth* and the password for next level is next to it.

The command is :

`cat data.txt | grep millionth`

The password for next level is `****` .

# level 8-9

- 

Command to connect remote host : `ssh bandit8@bandit.labs.overthewire.org -p 2220` password is `****` .

We will use command `sort` to sort all texts in the file. Command `uniq` with option `u` i.e. `uniq -u` only prints unique lines. So the command is :

`sort data.txt | uniq -u`

and password is `****` .

# level 9-10

- 

Command to connect remote host : `ssh bandit9@bandit.labs.overthewire.org -p 2220` password is `****` .

Command `strings` print the sequences of printable characters in files and `grep =` will print lines with ‘=’ in it. The command is :

`strings data.txt | grep =`

and the password for next level is `****` .

# level 10-11

- Command to connect remote host : `ssh bandit10@bandit.labs.overthewire.org -p 2220` password is `****` .

Command `base64` with option `-d` decodes the file. So the command is

`base64 -d data.txt`

and the password is `****` .

# level 11-12

- Command to connect remote host : `ssh bandit11@bandit.labs.overthewire.org -p 2220` password is `****` .

Command `tr` is used to translate character. Since characters are rotated by 13 positions means *a* becomes *n* and *n* becomes *a*, *b* becomes *o* and *o* becomes *b* and so on. The command is

`cat data.txt | tr "[a-zA-Z]" "[n-za-mN-ZA-M]"`

and the password for the next level is `****` .

# level 12-13

- Command to connect remote host : `ssh bandit12@bandit.labs.overthewire.org -p 2220` password is `****` .

As mentioned in question make a new directory in /tmp and rename the file.

`xxd` program is used to make a hexdump or to do the reverse. Option `-r` convert hexdump into the binary. File `myfile.txt` is a hexdump and convert it into a binary file `myfile1.bin` using command

`xxd -r myfile.txt > myfile1.bin`

Using command `file myfile1.bin` , we found that `myfile1.bin` is a *gzip compressed data*.

`zcat` is a program supplied with `gzip` and is used to decompress *gzip compressed files*.

`zcat myfile1.bin > myfile2`

Again using `file` command on `myfile2`, we found that it is *bzip2 compressed data*.

`bzcat` program is supplied with `bzip2` and is used to decompress *bzip2 compressed files*.

`bzcat myfile2 > myfile3`

`myfile3` is *gzip compressed file* so use `zcat` program to decompress it in `myfile4`. `myfile4` is a POSIX tar archive.

`tar` program is used for archiving file and options `x` is used to extract an archive, `f` is used to specify name of the tar archive and `v` is used for more detailed listing.

`tar -xvf myfile4`

This command outputs file `data5.bin` which is again a *tar archive*. Again use `tar` program on `data5.bin` which outputs `data6.bin`. `data6.bin` is a *bzip2 compressed file* and use `bzcat` program to decompress it to `myfile7`.

`myfile7` is a *tar archive* and use tar program which outputs `data8.bin`. `data8.bin` is a *gzip compressed file* and use `zcat` to decompress it to file `myfile9`.

`myfile9` contains *ASCII text* and `cat myfile9` tells the password for the next level.

The password for the next level is `****` .

# level 13-14

- Command to connect remote host : `ssh bandit13@bandit.labs.overthewire.org -p 2220` password is `****` .

To access password we need to login as bandit14 and for that the host is localhost. In the directory */home/bandit13* file sshkey.private contains SSH key to login into bandit14.

`ssh` command is used to login and execute commands on a remote machine. Option `-i` selects a file from which the identity (private key) for RSA or DSA authentication is read and the file `sshkey.private`. The command is

`ssh -i sshkey.private bandit14@localhost`

The password is stored in */etc/bandit_pass/bandit14*.

The command is `cat /etc/bandit_pass/bandit14` and the password is `****` .

# level 14-15

- Command to connect remote host : `ssh bandit14@bandit.labs.overthewire.org -p 2220 password` is `****` .

`netcat` is a simple unix utility which reads and writes data across network connections, using TCP or UDP protocol.

`nc` host port creates a TCP connection to the given port on the given target host. Your standard input is then sent to the host, and anything that comes back across the connection is sent to your standard output. The command is

`nc localhost 30000`

and then enter password of this level. The password for the next level is `****` .

# level 15-16

- Command to connect remote host : `ssh bandit15@bandit.labs.overthewire.org -p 2220` password is `****` .

OpenSSL comes with a client tool that you can use to connect to a secure server. The tool is similar to telnet or nc, in the sense that it handles the SSL/TLS layer but allows you to fully control the layer that comes next.

To connect to a server, you need to supply a hostname and a port. For example: `$ openssl s_client -connect www.feistyduck.com:443`

So our command is

`openssl s_client -connect localhost:30001`

and then enter password for the current level. The password for the next level is `****` .

# level 16-17

- Command to connect remote host : `ssh bandit16@bandit.labs.overthewire.org -p 2220` password is `****` .

Nmap (“Network Mapper”) will help us to scan for ports. Option `-p` provides the port ranges to the tool. So our command is

`nmap localhost -p31000-32000`

We found two ports and port 31790 is open. Open port means server on that port is listening.

Now to connect to port 31790 we will use `openssl` with `s_client` tool, which we have done in previous challenge.

`openssl s_client -connect localhost:31790`

In level 13 we login using a ssh private key. We will try to do it here with command

`ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220`

But we received *warning: unprotected private key file* because file was readable to group and to the world and writable by the owner. We change to read-only mode to the owner using command

`sudo chmod 400 bandit17.key`

Now we can login into bandit17.

# level 17-18

- Command to login `ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220`

`diff` program compare files line by line and option `--normal` output a normal diff.

Command to find difference between passwords.new and passwords.old

`diff --normal passwords.new passwords.old`

and the difference in passwords.new is `****` .

# level 18-19

- After logging with command `ssh bandit18@bandit.labs.overthewire.org -p 2220` password `****` .

We receive Byebye ! as the output. In the question it is mentioned that someone has modified **.bashrc** to log you out when you log in with SSH.

With option `-t` in `ssh` command we can force psuedo-tty allocation.

“Pseudo Terminals” emulates Terminal hardware, handling input and output in the same way a physical device would so that the software connected is not aware there’s not a real device attached.

We have forced a psuedo terminal and we know that password is in the readme file, so we can view password using command.

`ssh -t bandit18@bandit.labs.overthewire.org -p 2220 cat readme`

and the password for the next level is `***` .

# level 19-20

- Command to connect remote host : `ssh bandit19@bandit.labs.overthewire.org -p 2220` password is `****` .

**Setuid**, which stands for set user ID on execution, is a special type of file permission in Unix and Unix-like operating systems such as Linux and BSD. It is a security tool that permits users to run certain programs with escalated privileges.

When an executable file’s setuid permission is set, users may execute that program with a level of access that matches the user who owns the file.

When viewing a file’s permissions with the `ls -l` command, the setuid permission is displayed as an “**s**” in the “user execute” bit position.

Here setuid is set for the binary file (`-rwsr-x--`) and the user is *bandit20*. So if execute `./bandit20-do` it will run as user *bandit20* and password for *bandit20* is stored in */etc/bandit_paas/bandit20* which is only accessible through user *bandit20*.

The command is

`./bandit20-do cat /etc/bandit_pass/bandit20`

and the password is `****` .

# level 20-21

- Command to connect remote host : `ssh bandit20@bandit.labs.overthewire.org -p 2220` password is `****` .

First lets see how to create a TCP listener connection on our local machine. For this purpose we will use netcat program and option `-l` specify that `nc` should listen for an incoming connection rather than initiate a connection to a remote host. We will open two terminal and in first terminal the command is `nc -l localhost -p 5000`. The netcat server is listening to port 5000. `-p` specifies the source port `nc` should use.

Now in second terminal netcat client establishes connection to the server on port 5000. The command to do that is `nc -v localhost 5000`
. Option `-v`
 give more verbose output.

Now login to a remote machine as user bandit20.

Binary file *suconnect* has escalated privilege as user *bandit21*. After running command `./suconnect` it shows how to use command i.e. *Usage: ./suconnect*

It also shows “*This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back*”.

First we have to establish a TCP connection like we did above. We can connect on any port for eg. port 12345. Then we pass the password of current level (bandit20). And if the password is correct, it will display password for level 21.

In terminal 1 server will listen on port 12345 and password of the current level is passed. Command is

In terminal 2 binary file suconncet will connect to server on port 12345 and if password matches, password for next level is displayed on the terminal 1. Command is

`./suconnect 12345`

and the password is `****` .

# level 21-22

- Command to connect remote host : `ssh bandit21@bandit.labs.overthewire.org -p 2220`
 password is `****`
 In directory */etc/crond.d/*
, file important to us is *cronjob_bandit22*
. It is a crontab file and contain commands. The content can be viewed using `cat cronjob_bandit22`

The command is executing the file *cronjob_bandit22.sh* which is in the directory */usr/bin/*. Lets see the content of file *cronjob_bandit22.sh* using command `cat /usr/bin/cronjob_bandit22.sh`.

.Now we know that file */tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv*
 contains the password for the next level. We can view the password using command `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`
 and the password is `****`

# level 22-23

- Command to connect remote host : `ssh bandit22@bandit.labs.overthewire.org -p 2220`
 password is `****`

After executing *cronjob_bandit23.sh* using `./cronjob_bandit23.sh` it generates a file in *tmp* directory and the name of the file is md5 hash containing bandit22.

If we change bandit23 to bandit23 then new hash is generated which is the name of new file in tmp directory which may contain password for level 23.

To generate new hash run `echo I am user bandit23 | md5sum | cut -d ' ' -f 1` on terminal. The new hash is *8ca319486bfbbc3663ea0fbe81326349* and this is the name of file in *tmp* directory.

To see password run `cat /tmp/8ca319486bfbbc3663ea0fbe81326349` and the password is `****` .

# level 23-24

- Command to connect remote host : `ssh bandit23@bandit.labs.overthewire.org -p 2220` password is `****` .

Execute these commands to know the content of crontab file and then content of the script file.

`cd /etc/cron.d/
ls
cat cronjob_bandit24
cat /usr/bin/cronjob_bandit24.sh`

The command `cd /vars/pool/$myname`
 will change to *bandit24*
 directory and then all scripts in directory *bandit24*
 will be executed and then deleted. This is done in every 60 seconds as `timeout`
 is provided.

So if we put our script in */var/spool/bandit24* then it will be executed and then deleted. So we will write our script such that it will output password for next level.

We will create a directory *pcdir123* in */tmp* directory and change the permissions to readable, writeable and executable for *pcdir123*. (This is very important). The command are:

`mkdir /tmp/pcdir123
chmod 777 pcdir123`

Now create a script file *pass24script.sh* in */tmp/pcdir123* which will contain our script. The script is

`#!/bin/sh
cat /etc/bandit_pass/bandit24 > /tmp/pcdir123/pass24file`

*pass24script.sh*
 is not executable, so make it executable for all users using command `chmod 777 pass24script`.

 .

Copy this script in */var/spool/bandit/24* using command `cp pass24script.sh /var/spool/bandit24`

When new minute starts, file pass24file is produced with password for the next level if the directory pcdir123 has write permission enabled. The password is `****` .

# level 24-25

- Command to connect remote host : `ssh bandit24@bandit.labs.overthewire.org -p 2220` password is `UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ` .

We can connect on port 30002 in a same way as we have done in level 20. We also have to pass password for current level and the 4 digit pin.

The script is

`#!/bin/bash
for i in {0000..9999}
do 
	echo "UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i"
done`

The name of the script is *bruteforcescript.sh* and file *combinations.txt* will store all combinations of 4 digit number with password for bandit20. First we have to make bruteforcescript.sh executable using command

`chmod 700 bruteforcescript.sh
./bruteforcescript.sh > combinations.txt`

And the final command is

`nc localhost 30002 < combinations.txt`

The password for the next level is `****` .

Here are the basics:

- [x]  Click anywhere and just start typing
- [x]  Hit **/** to see all the types of content you can add - headers, videos, sub pages, etc.
- [x]  Highlight any text, and use the menu that pops up to **style** *your* ~~writing~~ `however` [you](https://www.notion.so/product) like
- [x]  See the **⋮⋮** to the left of this checkbox on hover? Click and drag to move this line
- [x]  Click the **+ New Page** button at the bottom of your sidebar to add a new page
- [x]  Click **Templates** in your sidebar to get started with pre-built pages
- This is a toggle block. Click the little triangle to see more useful tips!
    - [**notion.com/templates**](https://www.notion.so/templates): More templates built by the Notion community
    - [**notion.com/help**](https://www.notion.so/help): ****Guides and FAQs for everything in Notion
    - [**notion.com/guides**](http://notion.com/guides): Watch videos and read tutorials to become a Notion expert

👉 **Have a question?** Click the `?` at the bottom right for more guides, or to send us a message.