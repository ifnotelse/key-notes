# linux-notes

Getting Help:

ubuntu@ip-10-184-0-35:~$ help alias
alias: alias [-p] [name[=value] ... ]
    Define or display aliases.
    
Without arguments, `alias' prints the list of aliases in the reusable form `alias NAME=VALUE' on standard output.
    
Otherwise, an alias is defined for each NAME whose VALUE is given. A trailing space in VALUE causes the next word to be checked for alias substitution when the alias is expanded.
    
    Options:
      -p	Print all defined aliases in a reusable format
    
    Exit Status:
    alias returns true unless a NAME is supplied for which no alias has been
    defined.
    
    
    One drawback of the help command is that is only works on built-in shell commands. These commands are part of the BASH shell, not a separate executable. The majority of commands that you will execute are not built-in shell commands, so the help command won’t be that helpful.
    
    However, almost all commands have documentation available via a command called the man command (man is short for manual). To view a man page for a command, execute man cmd, replacing cmd with the command name. 
    
    For example, to view the man page for the cal command, execute man cal.
    
    To facilitate the process of reading the man page, you can use several keys to move through the document:

 <spacebar>—Move down one screen.

 <ENTER>—Move down one line.

 b—Move back one screen.

 /term—Search for term.

 h—Display help screen.

 q—Quit displaying man page.
 
 
 
In addition to man pages, you might find info documentation helpful. Not all commands and files have info documentation, but for those that do, using it can be easier than using man pages. To use an info document, execute the info command followed by the command to display; 

for example, 
        info ls.
