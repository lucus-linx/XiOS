# [UNIX / Linux set your PATH Variable Using set or export Command](https://www.cyberciti.biz/faq/unix-linux-adding-path/)

Author: Vivek Gite Last updated: August 7, 2025 [23 comments](https://www.cyberciti.biz/faq/unix-linux-adding-path/#comments)

How do I add a new path to $PATH variable under Linux and UNIX like operating system? What is my path, and how do I set or modify it using csh/tcsh or bash/ksh/sh shell?

The PATH is an environment variable. It is a colon delimited list of directories that your shell searches through when you enter a command. All executables are kept in different directories on the Linux and Unix like operating systems. Let us see how to set your PATH variable using the [set command](https://bash.cyberciti.biz/guide/Set_command) and [export command](https://www.cyberciti.biz/faq/linux-unix-shell-export-command/) under Linux or Unix-like systems.

| Tutorial details  |                                                              |
| :---------------: | ------------------------------------------------------------ |
| Difficulty level  | [Easy](https://www.cyberciti.biz/faq/tag/easy/)              |
|  Root privileges  | No                                                           |
|   Requirements    | Linux or Unix terminal                                       |
|     Category      | [Linux shell scripting](https://bash.cyberciti.biz/guide/Main_Page) |
| OS compatibility  | [AIX](https://www.cyberciti.biz/faq/unix-linux-adding-path/) • AlmaLinux • [Alpine](https://www.cyberciti.biz/faq/category/alpine-linux/) • [Arch](https://www.cyberciti.biz/faq/category/arch-linux/) • BSD • [Debian](https://www.cyberciti.biz/faq/category/debian-ubuntu/) • [Fedora](https://www.cyberciti.biz/faq/category/fedora-linux/) • [FreeBSD](https://www.cyberciti.biz/faq/category/freebsd/) • [HP-UX](https://www.cyberciti.biz/faq/category/hp-ux-unix/) • [Linux](https://www.cyberciti.biz/faq/category/linux/) • [macOS](https://www.cyberciti.biz/faq/category/mac-os-x/) • Mint • NetBSD • [OpenBSD](https://www.cyberciti.biz/faq/category/openbsd/) • [openSUSE](https://www.cyberciti.biz/faq/tag/opensuse/) • Pop!_OS • [RHEL](https://www.cyberciti.biz/faq/category/redhat-and-friends/) • Rocky • [Stream](https://www.cyberciti.biz/faq/tag/centos-stream/) • [SUSE](https://www.cyberciti.biz/faq/category/suse/) • [Ubuntu](https://www.cyberciti.biz/faq/category/ubuntu-linux/) • [Unix](https://www.cyberciti.biz/faq/category/unix/) • WSL |
| Est. reading time | 2 minutes                                                    |

## Finding out your current path

To find out what your current path setting, type the following command at shell prompt. Open the Terminal and type [echo command](https://bash.cyberciti.biz/guide/Echo_Command) or [printf command](https://bash.cyberciti.biz/guide/Printf_command):

```
echo "$PATH"
```

OR

```
printf "%s\n" "$PATH"
```

Sample outputs:

```
/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:/opt/X11/bin:/usr/local/sbin/modemZapp:/Users/vivek/gcutil-1.8.4
```

## How do I modify or set my PATH variable under Linux or Unix?

To modify your path edit $PATH variable as per your shell. The syntax for setting path under UNIX / Linux dependent upon your login shell.

### Bash, Sh, Ksh shell syntax to modify $PATH

If you are using bash, sh, or ksh, at the shell prompt, type:

```
## please note 'PATH' is CASE sensitivity and must be in UPPERCASE ##
export PATH=$PATH:/path/to/dir1
export PATH=$PATH:/path/to/dir1:/path/to/dir2
```

OR

```
## please note 'PATH' is CASE sensitivity and must be in UPPERCASE ##
PATH=$PATH:/path/to/dir1; export PATH
```

Please feel free to replace /path/to/dir1 with the directory you want the shell to search. You can use the [grep command](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/) or [egrep command](https://www.cyberciti.biz/faq/grep-regular-expressions/) to search for PATH as follows:

```
grep -i path ~/.profile
egrep -i 'path|java_path' ~/.profile
```

### Tcsh or csh shell syntax to modify $PATH

If you are using tcsh or csh, shell enter:

```
 ## please note 'path' is case sensitivity and must be in lowercase ##
set path = ($path /path/to/dir1)
set path = ($path /path/to/dir1 /path/to/dir2)
```

OR

```
## please note 'PATH' is CASE sensitivity and must be in UPPERCASE ##
setenv PATH $PATH:/path/to/dir1
setenv PATH $PATH:/path/to/dir1:/path/to/dir2
```

Please feel free to replace /path/to/dir1 with the directory you want the shell to search.

## Examples

In this example add /usr/local/bin to your path under BASH/ksh/sh shell, enter:

```
export PATH=$PATH:/usr/local/bin
```

OR

```
PATH=$PATH:/usr/local/bin; export PATH
```

To make these changes permanent, add the commands described above to the end of your [~/.profile](https://bash.cyberciti.biz/guide/.profile) file for sh and ksh shell, or [~/.bash_profile](https://bash.cyberciti.biz/guide/.bash_profile) file for bash shell:

```
## BASH SHELL ##
echo 'export PATH=$PATH:/usr/local/bin'  >> ~/.bash_profile
```

KSH/sh shell user try:

```
## KSH / SH SHELL ##
echo 'PATH=$PATH:/usr/local/bin;export PATH'  >> ~/.profile
```

In this final example add /usr/local/bin/ and /scripts/admin/ to your path under csh / tcsh shell, enter:

```
set path = ($path /usr/local/bin /scripts/admin)
```

OR

```
setenv PATH $PATH:/usr/local/bin:/scripts/admin
```

To make these changes permanent, add the commands described above to the end of your [~/.cshrc](https://bash.cyberciti.biz/guide/.cshrc) file:

```
echo 'set path = ($path /usr/local/bin /scripts/admin)'  >> ~/.cshrc
```

OR

```
echo 'setenv PATH $PATH:/usr/local/bin:/scripts/admin'  >> ~/.cshrc
```

To verify new path settings, enter:
`echo "$PATH"`



## Summing up

I hope this helps someone set up PATH variables under Unix or Linux. For more info see the following manual pages using the [man command](https://bash.cyberciti.biz/guide/Man_command) or [help command](https://bash.cyberciti.biz/guide/Help_command):

```sh
$ man bash
$ man tcsh
$ man kshman csh
```





