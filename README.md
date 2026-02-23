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
'cron', displays some information about the virtual machine on all terminals.


# Instructions:

To start the virtual machine you just have to open 'Oracle VirtualBox', select
the right machine and press start.
Connecting to the machine via the regular terminal can be done by typing 
'ssh bede-kon@localhost -p 4242' on the command line.


# Resources:

[https://en.wikipedia.org/wiki/Firewall_(computing)#Packet_filter] -> Firewall
[https://noreply.gitbook.io/born2beroot] -> B2BR tutorial
[https://en.wikipedia.org/wiki/UTM_(software)] -> UTM
[https://en.wikipedia.org/wiki/VirtualBox] -> VirtualBox
[https://en.wikipedia.org/wiki/Hypervisor#Classification] -> about hypervisors
[https://apparmor.net/] -> AppArmor
[https://www.redhat.com/en/topics/linux/what-is-selinux] -> SELinux
[https://en.wikipedia.org/wiki/Uncomplicated_Firewall] -> UFW
[https://firewalld.org/] -> Firewalld
[https://linuxhandbook.com/crontab/] -> Crontab

No AI was involved in the making of this project.


# Project description:

I have chosen 'Debian' as operating system over 'Rocky' because 'Debian' is more
flexible, customizable and supports a wider range of software. The pros of
'Rocky' on the other hand are that it offers long-term stability and support,
making it great for companies. The subject also highly recommended people who 
are new to system administration to install 'Debian' so it was an easy choice 
for me.

During the setup, several design choices had to be made:

- I chose to use the entire disk and set up encrypted LVM, this was needed to
  create at least two encrypted partitions
- For the security of 'sudo' I made a file where I added some password
  requirements, a file that logs all the times the 'sudo' command was used and
  set the use of 'TTY' to be required. I modified another file to make sure the
  password has to be changed every 30 days (with a warning seven days 
  beforehand) along with the need for the password to stay the same for at least
  two days. Finally, I installed a password quality library which let me add
  some more password requirements by modifying a file.
- User managment is done by creating users ('sudo adduser <user>') and adding 
  them to groups ('sudo addgroup <user>').
- Services I've installed are 'sudo' (enables users to run programs with the
  security privileges of the root user), 'openssh-server' (making remote access
  with the 'SSH' protocol possible), 'ufw' ('Uncomplicated Firewall' is a
  firewall that uses the command line to set up 'iptables' (default firewall
  configuration tool for many Linux distributions)).

Comparing:

- 'AppArmor' vs 'SELinux':
  Both are security systems that allow administrators to have more control over
  who can access the system, giving protection to the OS and applications.
  'AppArmor' is less compcated, controls fewer operations, doesn't have 
  'Multi-Level Security' (MLS), 'Multi-Category Security' (MCS)
  and doesn't seperate containers by default. 
  'SELinux' _does_, making it more suitable for highly secure environments.
  Setting up 'AppArmor' was documented in a tutorial so I used that one as I
  figured that I didn't need something highly secure for this project.
- 'UFW' vs 'Firewalld': 
  Both are firewalls (netwerk security system that monitors and controls
  incoming and outgoing network traffic).
  'UFW' (Uncomplicated Firewall) is easier to use but 'Firewalld' is better
  documented, making it easier if you need something specific or don't use it 
  often. Setting up 'UFW' was documented in a tutorial so I used that one.
- 'VirtualBox' vs 'UTM':
  Both are open-source virtual machine applications.
  'VirtualBox' is feature-rich with broader Linux distro support but may have
  slower performance. 'UTM' is a macOS-specific VM which makes it a good (easy
  to use and high performing) choice for Macs. 
