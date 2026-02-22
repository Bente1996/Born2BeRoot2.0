*This project has been created as part of the 42 curriculum by bede-kon.*

# Description:

Born2BeRoot is about creating your own virtual machine in 'VirtualBox' using
specific instructions and setting up your own operating system while
implementing strict rules such as:

- creating at least two encrypted partitions using 'LVM'
- setting up an 'SSH' service on the mandatory port 4242
- configuring your operating system with the 'UFW'
- implementing a strong password policy
- installing and configuring 'sudo'

Finally, you have to create a simple script in 'bash' that, with the use of
cron, displays some information about the virtual machine on all terminals.


# Instructions:

To start the virtual machine you just have to open 'Oracle VirtualBox', select
the right machine and press start.
Connecting to the machine via the regular terminal can be done by typing 
'ssh bede-kon@localhost -p 4242' on the command line.


# Resources:

# Project description:

I have chosen 'Debian' as operating system over 'Rocky' because 'Debian' is more
flexible, customizable and supports a wider range of software. The pros of
'Rocky' on the other hand are that it offers long-term stability and support,
making it great for companies. The subject also highly recommended people who 
are new to system administration to instal 'Debian' so it was an easy choice for
me.

During the setup, several design choices had to be made:

- I chose to use the entire disk and set up encrypted LVM, this was needed to
  create at least two encrypted partitions
- for the security of 'sudo' I made a file where I added some password requirements, a file that logs all the
  times the 'sudo' command was used and set the use of 'TTY' to be required
  I modified another file 
- 
