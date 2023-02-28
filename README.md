# ubuntu_server_install

So Recently I've been learning system administration and most common is to install ubuntu server 20.04
So I make a tutorial for myself because I encountered an error it wont connect to internet

so after downloading ubuntu 20.04 , i encountered an error and even after reinstalling the same image in virtual box this issue persists
Temporary failure in name resolution
here is the fix

""
I've faced the exactly same problem but I've fixed it with another approache.

Using Ubuntu 18.04, first disable systemd-resolved service.

sudo systemctl disable systemd-resolved.service

Stop the service

sudo systemctl stop systemd-resolved.service

Then, remove the link to /run/systemd/resolve/stub-resolv.conf in /etc/resolv.conf

sudo rm /etc/resolv.conf

Add a manually created resolv.conf in /etc/

sudo vim /etc/resolv.conf

Add your prefered DNS server there

nameserver 208.67.222.222

I've tested this with success.
"""

Thank you to André M. Faria for giving the solution

