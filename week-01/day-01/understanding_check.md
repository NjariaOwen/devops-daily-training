1. its a variable folder in the log directory meaning that it hold logs for an app "nginx" 
and the file is errors that happened inside the nginx application

2. two files with the same inode number is a hardlink 

3. there is a folder called /proc that holds data about the runnimg processes the i can use
ps aux | grep "app name"

4. the kernel is the operating system and the shell provides the user an interface to interact
with the kernel

5. a symlink points to an original file if you  remove the original file then the link breaks
it works not like the hardlink where even if the original file is deleted it doesn't  affect
it so when you carry the original and leave or you carry the symlink and leave the original
then the link breaks making it looking for something it can find.

		AM DONE!!!!!! 
