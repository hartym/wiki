Virtualization
==============

* :wiki:`App/Virtualization/Docker`
* :wiki:`App/Virtualization/VirtualBox`

Quick troubleshooting notes
:::::::::::::::::::::::::::

On some networks, I had really slow DNS requests, making a real hell to use package managers like npm or gem (especially when building docker images). 

VBoxManage modifyvm <vm-name> --natdnsproxy1 on
VBoxManage modifyvm <vm-name> --natdnshostresolver1 on

cf https://github.com/docker/docker/pull/1813/files
