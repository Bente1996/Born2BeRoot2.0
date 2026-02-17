# Born2BeRoot2.0

*This project has been created as part of the 42 curriculum by bede-kon.*

Description:
General description

Instructions:
Any relevant info about installation, compilations and/or execution

Resources:
Classic references related to topic
https://apparmor.net/
https://www.redhat.com/en/topics/linux/what-is-selinux
https://www.redhat.com/en/blog/apparmor-selinux-isolation
https://en.wikipedia.org/wiki/Uncomplicated_Firewall
https://firewalld.org/
https://linuxhandbook.com/crontab/

No AI was used in the making of this project.

Project Description:
Choice Debian vs Rocky:
Comparisons:
- Debian vs Rocky Linux:
- AppArmor vs SELinux:
  "AppArmor protects OS and applications from external or internal threats."
  "SELinux is a security architecture for Linux systems that allows administrators to have more control over who can access the system."
  Difference?
  AppArmor is less complicated and controls fewer operations.
  AppArmor doesn't have Multi-Level Security (MLS) and Multi-Category Security (MCS).
  SELinux seperates containers by default, AppArmor doesn't.
  AppArmor can't be used in highly secure environments.
- UFW vs Firewalld:
  UFW (Uncopmlicated Firewall) is an easy to user-friendly front-end for managing iptables (default firewall configuration tool for many Linux distributions).
  UFW is easier to use. Firewalld is better documented so might be easier if you need something specific or don't use it often.
- VirtualBox vs UTM:
