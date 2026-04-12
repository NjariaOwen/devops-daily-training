which bash shows where it is placed for me it returned 

~ ➤ which bash                                                                       git:main*
/usr/bin/bash
~ ➤ file /usr/bin/bash                                                               git:main*

/usr/bin/bash: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=2f77b36371c214e11670c7d9d92727e9a49f626b, for GNU/Linux 3.2.0, stripped
~ ➤ which python3                                                                    git:main*
/usr/bin/python3
~ ➤ file /usr/bin/python3                                                            git:main*

/usr/bin/python3: symbolic link to python3.12
~ ➤ which systemctl                                                                  git:main*
/usr/bin/systemctl
~ ➤ file /usr/bin/systemctl                                                          git:main*
/usr/bin/systemctl: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=dff0af65f816d5c93f8dd9c985c7bef8e34806f9, for GNU/Linux 3.2.0, stripped
~ ➤

so i think which command is used to locate the executable file associated with the command 

------------------------------------------------------------------------------------------------
 ➤ ls /usr/bin | wc -l                                                              git:main*
1586
~ ➤ ls /bin | wc -l                                                                  git:main*
1586
~ ➤ stat /usr/bin                                                                    git:main*
  File: /usr/bin
  Size: 61440     	Blocks: 128        IO Block: 4096   directory
Device: 252,0	Inode: 11403266    Links: 2
Access: (0755/drwxr-xr-x)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2026-04-11 20:15:48.526659340 +0300
Modify: 2026-04-05 10:04:51.957731675 +0300
Change: 2026-04-05 10:04:51.957731675 +0300
 Birth: 2026-01-23 12:49:15.647133403 +0300
~ ➤ stat /bin                                                                        git:main*
  File: /bin -> usr/bin
  Size: 7         	Blocks: 0          IO Block: 4096   symbolic link
Device: 252,0	Inode: 12          Links: 1
Access: (0777/lrwxrwxrwx)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2026-04-12 15:02:07.237557243 +0300
Modify: 2024-04-22 16:08:03.000000000 +0300
Change: 2026-01-23 12:49:15.350887340 +0300
 Birth: 2026-01-23 12:49:15.350158346 +0300
~ ➤

in my system the /bin shows lrwxrwxrwx which "l" means its a symbolic link of usr/bin

the difference between /bin and /usr/bin historically the /bin was on the root disk and
/usr/bin was on a separate disk but in the modern days they make them one the essential difference is /bin is for essenial necessary binaries the system need to function and
/usr/bin is for majority of apps and binaries not needed during boot up
