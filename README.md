vagrant-puphpet-grn
===================

Vagrant instance for local PHP development for the GetRepairs project generated through PUPHPET. This is, by default, intended for a Windows host machine but the the PUPHPET _config.yaml_ file can be modified to adopt to any host. Here's what is configured for this instance.

* Vagrant Box: puphpet/ubuntu1404-x64
* Vagrant Profider: Virtualbox
* Guest Memory: 1024MB
* Guest IP Address(private network): 192.168.56.101

Synced Folders
==============

Before provisioning, the following folders must be created in the host machine.

* c:\vagrant\web\trusty-php
* c:\vagrant\home\trusty-php

These respectively map to _/var/www_ and _/home/vagrant/shared_ directories in the guest machine. Again, these can be modified by updating the config.yaml.

SSH Keys
=======

SSH keys can be added by placing both the public and private keys in _puphpet/files/dot/ssh_. For convenience sake, rename these keys to _id_rsa.pub_ and _id_rsa_ respectively. If the guest machine has already been provisioned, stop the machine by running _**vagrant halt**_ followed by _**vagrant provision**_.

Access Guest Machine Sites
==========================

To access the guest machine sites, update the Windows hosts file, _c:\windows\system32\drivers\etc\hosts_, and add a mapping for the Apache's vhost servername value and the guest machine IP address.

> 192.168.56.101  getrepairs.dev

Miscellaneous
=============

This instance have both [Adminer](http://www.adminer.org) and [MailCatcher](http://mailcatcher.me) installed and enabled. You can access these from the host using the following:

* http://192.168.56.101/adminer
* http://192.168.56.101:1080
