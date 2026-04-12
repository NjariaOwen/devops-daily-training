what i think about the filesystem is:

-- all files exist under a root directory which is / even if they are stored on
different physical or virtual devices
-so under "ls /" i found files like bin, dev, etc, home and many more

-- the /etc folder host specific system configurations
under ls /etc | head -20 i can see adduser.conf, apache2, bluetooth and even
bash.bashrc that even makes it self explanatory its a config for bash

-- the /var folder contains variable data files like logs for processes we have
metrics we have backups there and that folder var its contents are not sharable
between different systems

-- the /usr folder it contains the readonly user data like under /usr we have bin
it has users command libraries it has /src that has source files 

-- the /bin folder it has the user command binaries i think its the commands that
we use daily eg. man, less, nmtui, netcat, networkctl ... after deep research and 
reading i found about /sbin it hold the same command binaries but now this has the
administrative commands eg. ip, iptables, arptables, iwconging and many more


-- i saw the /boot that stores the kernel and grub boot files essential for the
machine to be able to boot

-- and i found another intresting one /proc so this hold infomation about all the 
systems processes
