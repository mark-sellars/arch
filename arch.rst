Arch build super micro

Partitions

nvme0n1
- EFI: 512MB
- swap: 48G
- /: 100G
- home: MAX

packages

groups 

base 
base-devel

vim 

htop

refind

networkmanager

openssh

xf86-video-intel

firewalld

vim /etv/hosts
change IP to host IP on line 127.0.1.1 locahost.localdomain arch

Add User
========
useradd -m -g wheel mark
vim /etc/sudoers

Setup startx
============
vim /etc/X11/xinit/xinitrc

Comment these lines out:
#twm &
#exec xterm ....

Add this:
exec i3

Start Xwindows
==============
startx

Auto Startx
===========
add to .bash_profile
if [ -z "${DISPLAY}" ] && [ "${XDG_VTNR}" -eq 1 ]; then
  exec startx
fi
