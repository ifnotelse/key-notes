# linux-notes

Getting Help:

ubuntu@ip-10-184-0-35:~$ help alias
alias: alias [-p] [name[=value] ... ]
    Define or display aliases.
    
    Without arguments, `alias' prints the list of aliases in the reusable
    form `alias NAME=VALUE' on standard output.
    
    Otherwise, an alias is defined for each NAME whose VALUE is given.
    A trailing space in VALUE causes the next word to be checked for
    alias substitution when the alias is expanded.
    
    Options:
      -p	Print all defined aliases in a reusable format
    
    Exit Status:
    alias returns true unless a NAME is supplied for which no alias has been
    defined.
    
    
    One drawback of the help command is that is only works on built-in shell commands. These commands are part of the BASH shell, not a separate executable. The majority of commands that you will execute are not built-in shell commands, so the help command won’t be that helpful.
    
    However, almost all commands have documentation available via a command called the man command (man is short for manual). To view a man page for a command, execute man cmd, replacing cmd with the command name. 
    
    For example, to view the man page for the cal command, execute man cal.
    
    
    2. Introduction to Linux
What exactly is Linux? The answer can be a complex one. Technically, Linux is a piece of software called the kernel. The kernel handles tasks such as booting the system and interacting with hardware devices. By itself, the kernel doesn’t really provide users with any functionality. The rest of the operating system (OS), consisting of the filesystem and a large number of commands, is what provides users with useful features.

Although Linux is technically just the kernel, many people refer to the entire OS as Linux. In reality, the collection of software that makes up the OS is known as a Linux distribution (also called a distro). Many distros are available to choose from, which often results in some confusion for novice Linux users.

What Is a Distribution?

A distribution is a collection of Linux software that is maintained by an organization. Each distribution has features that make it unique. Some distributions are designed for general use whereas others are designed for a very specific use case, like a firewall or a web server.

Picking the distro that works best for you might take some time. The website distrowatch.com can aid you in this endeavor. Additional information is also provided later in this chapter.

ACCESSING A LINUX SYSTEM
Before you can access a Linux system, you need to have one installed. Because each distro has a different installation program, the steps to installing a distro are not included in this book. However, the following should provide you with enough information to successfully install a distro:

 First consider which distro you want to use. This topic is explored in more detail later in this chapter.

 Consider installing the distro on a Virtual Machine (VM). By using a VM, you can install multiple distros and still use your host operating system. Several VM software choices are available, including VirtualBox, VMware, and Parallels Desktop (for Mac users). Some of these products have free versions, whereas others might charge a license fee.

 During the installation, consider accepting the defaults. Typically, the defaults provide you with the software that you need as a developer. You can always reinstall the distro in the future or add additional software using the tools described in Chapter 6, “System Administration.”

Choosing the Right Distribution
Often an organization spends a great deal of time to ensure that it chooses the Linux distribution that best fits the company’s needs. Each distro is different, and there isn’t a “one distro fits all scenarios” solution. There are many features to take into consideration, including:

 Cost—Some distros are entirely free, whereas some charge for support and access to updates.

 Features—Some distros provide limited access to software based on the objective of the distro. For example, a security-hardened distro only provides software that has met rigorous security benchmarks.

 Function—Some distros are specifically tailored to meet a specific function. For example, a distro might be designed to host database applications.

 Support—The organization that creates the distro might provide support, or the support might be completely community sponsored. For most distros used in a corporate environment, the organization that creates and maintains the distro provides support.

Although these might not be all the features you or your organization consider when choosing a distro, the preceding list provides you with an idea of what features are normally considered. Because literally hundreds of distros exist, I recommend exploring http://distrowatch.com, a website devoted to monitoring these distros, their features, and their popularity.

Linux distributions are generally split into three primary families:2

 Debian—Known to be a favorite of the hard-core Linux geeks, Debian was one of the first Linux distributions. Popular variations of Debian include Ubuntu and Mint.

 Red Hat:—Designed to be a commercial distro, Red Hat Linux was introduced shortly after Debian. It is now called Red Hat Enterprise Linux (RHEL). Because it is a commercial distro, payment of a license fee (for support and updates) is required to use RHEL. However, several free Red Hat–based distros exist, including Fedora and CENTOS.

 Slackware/SUSE—Slackware was the original “founding father” of this family of distros, but SUSE is the most popular now. SUSE is like RHEL in that it is designed to be a commercial distro. OpenSUSE is a free variation.

Regarding the information provided in this book, in most cases which distro you use does not matter. However, for some topics the distro does matter. When these situations arise, I provide detailed information regarding the differences between the distros. Otherwise, the examples make use of different distros to highlight that core functionality is largely the same across Linux distributions.3

Logging In
Typically, there are three ways to log in to a Linux system:

 Via the GUI—On laptops, desktops, and some servers, a GUI-based login appears by default.

 Via the command line—Administrators commonly do not install the GUI software on servers because that software is a huge hardware hog (CPU, RAM, and so on). On these servers, you typically see a command-line login.

 Via the network—A network-based login could either be via command line (very common) or GUI (not as common). The machine that you log into must have special software installed and enabled to allow this sort of access.

Logging In via the GUI
The software that allows you to log in to a Linux system is called a display manager. Several different display manager software programs are available, resulting in a different look and feel for the login screen. In some ways, this is dependent on the distro, because the organization that supports the distro tends to favor one display manager or another. However, an administrator can choose to install a different display manager or configure the appearance of the existing display manager. See Figure 2.1 for an illustration of display managers.


Figure 2.1 The default display manager on CentOS (left) and MintOS (right)

The good news is that regardless of which display manager you use, the basic operation shouldn’t change. You either select your user name from a list or type your user name in the dialog box provided. Then you are prompted for your password. As you become more experienced, try exploring other options provided by your display manager, such as shutting down your system.

Logging In via the Command Line
In most cases, you only log in via the command line when the server you are working on has no GUI. However, if your system has a GUI, logging in via a command line is still possible (even if you are working on a virtual machine). Holding down the Ctrl+Alt buttons on your keyboard and pressing the F2 key4 should provide a command-line login. See Figure 2.2 for an example of a command-line login screen.


Figure 2.2 A command-line login screen for CentOS

To log out of a command-line environment, type exit and then press the Enter key. To return to the GUI screen, press either Ctrl+Alt+F1 or Ctrl+Alt+F2.

Logging In via the Network
You can use a few techniques to log in to a remote system via the network. The techniques that are available depend on two factors: what sort of system you are logging in from and whether you want to log in to a command-line interface (CLI) or GUI:

 Logging in to a Linux system from a Microsoft Windows system: You will likely need some additional software because Microsoft Windows doesn’t normally provide the software needed to log in to a Linux system. If you want to log in through a CLI, install a Secure Shell (SSH) client program. If you want to log in to a GUI, install a virtual network computing (VNC) client program.5

 Logging in to a Linux system from a Macintosh system: At its heart, the Macintosh OS is Unix-based, so some client tools should already be available. For example, you should be able to open a terminal window and use the ssh command to log in to a Linux system via the CLI. You could also install VNC client software to log in to a Linux system via the GUI.

 Logging in to a Linux system from a Linux system: You should be able to use the ssh command to log in. A VNC client might also be installed, but if it isn’t then contact the administrator.6

In the following example, the “bob” user on the local machine logged in to the machine named “remote” using the “student” account (Note: Instead of a machine name, an IP address can be used):

bob@ubuntu:~$ ssh student@remote

The authenticity of host 'remote' can't be established.

ECDSA key fingerprint is 8a:d9:88:b0:e8:05:d6:2b:85:df:53:10:54:66:5f:0f.

Are you sure you want to continue connecting (yes/no)? yes

Warning: Permanently added 'remote' (ECDSA) to the list of known hosts.

student@remote's password:

Welcome to Ubuntu 14.04.2 LTS (GNU/Linux 3.16.0-30-generic x86_64)

student@remote:~$

Note the message about the key fingerprint. This is used in the future to verify that you are logging in to the correct system and not some fake machine that has assumed the identity of the remote system. This question only appears the first time you log in to this system.

To return to the local system, execute the exit command.

USING THE GUI
The heading “Using the GUI” is a bit misleading because there isn’t just one GUI. With Linux, you have your choice of several different desktops, each of which provides the same essential functions in different ways in addition to having unique features. A small sample of available desktops includes the following:

 GNOME

 KDE

 Unity+

 Cinnamon

 Xfce

 MATE

With so many desktops available, you might ask yourself “Which one should I use?” To some extent, that question might be answered for you when you choose your Linux distribution. Most distros have a “favored default” desktop which will be installed and used automatically. Although other desktops might be available for the distro, you typically need to install them separately.

In some cases, the developers of the distro might provide you the option of choosing your desktop before you install the distro. For example, consider Figure 2.3, which displays the download links for the Mint distribution.


Figure 2.3 Mint download links

Figure 2.3 shows the different install options provided, primarily divided by the type of desktop. Additionally, a user with administrative access can install multiple desktops on a single system. If there are multiple desktops, you could choose which desktop you want to use before you log in, as demonstrated in Figure 2.4.


Figure 2.4 Desktop choices at login

After you successfully log in, a desktop appears. The overall look and feel of the desktop varies. However, figuring out where things are on a particular desktop shouldn’t take too long. For example, look at Figure 2.5, which displays the default desktops for MintOS.


Figure 2.5 Cinnamon versus MATE desktops

As you can see, the Cinnamon and MATE desktops look very similar. Both provide a menu (bottom left) that enables you to access additional programs and features. Both have quick launch icons and both provide system information (bottom right) such as date/time. The choice comes down to exploring the desktop that you are using rather than memorizing where features reside for a specific desktop.

BASIC COMMAND-LINE EXECUTION
Although the GUI interface makes using Linux easy, most users and administrators use the command-line environment for system tasks. If you log in to a system via the GUI, you can access the command-line environment by opening a terminal window. The terminal window is a GUI-based program that launches a shell, a program that enables you to enter commands. See Figure 2.6 for an example of a terminal window.


Figure 2.6 Typical terminal window

The most common shell program in Linux is the BASH7 shell. This book shows BASH shell–based examples.

Command-Line Structure
A command has three components:

 Command name—This is just the name of the command.

 Option(s)—An option (also referred to as a flag) is a predefined value that changes the behavior of the command. The format of options can vary. In some cases, the option begins with a single hyphen followed by a single character; for example: ls -a. In other cases, the option begins with two hyphens followed by a word; for example: ls --all. In some rare cases, the option is just a single character with no hyphen. The format depends on the command because some commands support the single-hyphen method whereas others support the double-hyphen method (and some support both methods).

 Arguments—Arguments are used to provide additional information to the command. This information could be things like a filename, user name, or host name.

See Figure 2.7 for a visual example of the command-line components.


Figure 2.7 Components of a command line

Getting Help
You might be wondering how to tell what options and arguments a command will accept. Several ways exist to display documentation that can help you use a command. One method you could use is the help command:

bo@mintos:~ > help alias

alias: alias [-p] [name[=value] ... ]

    Define or display aliases.


    Without arguments, 'alias' prints the list of aliases in the reusable

    form 'alias NAME=VALUE' on standard output.


    Otherwise, an alias is defined for each NAME whose VALUE is given.

    A trailing space in VALUE causes the next word to be checked for

    alias substitution when the alias is expanded.


    Options:

      -p    Print all defined aliases in a reusable format


    Exit Status:

    alias returns true unless a NAME is supplied for which no alias has

    been defined.

As you can see from the output of the help alias command, the command accepts the -p option. Because the option is enclosed within square brackets, the option is not required for the command to run. Additionally, you can include a name or name=value argument with the command. Again, the square brackets indicate that these arguments are not required and that name does not require an =value argument.

One drawback of the help command is that is only works on built-in shell commands. These commands are part of the BASH shell, not a separate executable.8 The majority of commands that you will execute are not built-in shell commands, so the help command won’t be that helpful.

However, almost all commands have documentation available via a command called the man command (man is short for manual). To view a man page for a command, execute man cmd, replacing cmd with the command name. For example, to view the man page for the cal command, execute man cal.

Note

You will eventually discover that not only commands have man pages. Configuration files and other things have man pages, too.

The man page for a given command9 can be quite large. To facilitate the process of reading the man page, you can use several keys to move through the document:

 <spacebar>—Move down one screen.

 <ENTER>—Move down one line.

 b—Move back one screen.

 /term—Search for term.

 h—Display help screen.

 q—Quit displaying man page.
