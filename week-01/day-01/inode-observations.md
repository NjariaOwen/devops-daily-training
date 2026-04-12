-- stat command displays detailed statistics of a file or directory
-- file is used to know the type of a file by examining the contents not the extension
-- ln is used to create links between files which can either be hardlink or soft (symbolic)
links 
when you run with -s it makes a symbolic link with ln with no tag you make hard links

-- when i run stat /etc/hosts it should me the size, inode, links it has 1 then it has
permisions of that file and more data there

-- when i run ls -li /etc/hosts it displays the file /etc/hosts as a long list format and then
the i adds inode number in the list
~ ➤ ls -li /etc/hosts                                                                git:main*
4981128 -rw-r--r-- 1 root root 224 Jan 23 13:06 /etc/hosts
~ ➤

-- stat /tmp/original.txt is the original file we made on my side when i run ii, it says it
has an inode number 4587545 and the /tmp/hardlink.txt which is a hardlink of the original file
has an inode number 4587545 and i can notice something hardlinks have the same inode number
with the original file but a symlink has a different inode number 4587550 than the original
file but there is something else the size for hardlink size remained for softlink the size increased
-i beacame a bit curious and deleted the original.txt what happened was unexpected

~ ➤ rm -rf /tmp/original.txt                                                         git:main*
~ ➤ stat /tmp/original.txt                                                           git:main*
stat: cannot statx '/tmp/original.txt': No such file or directory
~ ➤ stat /tmp/hardlink.txt                                                           git:main*
  File: /tmp/hardlink.txt
  Size: 6         	Blocks: 8          IO Block: 4096   regular file
Device: 252,0	Inode: 4587545     Links: 1
Access: (0664/-rw-rw-r--)  Uid: ( 1000/    owen)   Gid: ( 1000/    owen)
Access: 2026-04-12 17:19:49.287745829 +0300
Modify: 2026-04-12 17:19:49.287745829 +0300
Change: 2026-04-12 17:30:20.820551532 +0300
 Birth: 2026-04-12 17:19:49.287745829 +0300
~ ➤ stat /tmp/symlink.txt                                                            git:main*
  File: /tmp/symlink.txt -> /tmp/original.txt
  Size: 17        	Blocks: 0          IO Block: 4096   symbolic link
Device: 252,0	Inode: 4587550     Links: 1
Access: (0777/lrwxrwxrwx)  Uid: ( 1000/    owen)   Gid: ( 1000/    owen)
Access: 2026-04-12 17:20:32.551989983 +0300
Modify: 2026-04-12 17:19:49.297746354 +0300
Change: 2026-04-12 17:19:49.297746354 +0300
 Birth: 2026-04-12 17:19:49.297746354 +0300
~ ➤                                                                                  git:main*

i thought the symlink will go so now i hit the dangling symlink error and when i
cat /tmp/symlink.txt it said
 ➤ cat /tmp/symlink.txt                                                             git:main*
cat: /tmp/symlink.txt: No such file or directory
~ ➤    
meaning the file it is referencing to is gone so its a bridge to nowhere so i said let me 
try something i recreated the file to see what happens

surprisingly:

~ ➤ echo "I am back" > /tmp/original.txt                                             git:main*
~ ➤ cat /tmp/symlink.txt                                                             git:main*
I am back


it started working again i think when it looked for the path again it found it but i found 
a way of instead i remakinga new file i should just make a hardlonk of the hardlink.txt 
and name it original.txt as in - ln hardlink.txt original.txt so the original.txt comes
back with the same content it initially had 
