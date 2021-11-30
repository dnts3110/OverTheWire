login to ssh: ssh banditX@bandit.labs.overthewire.org, then the terminal will request the password for that level X
if you’re already connect to the ssh server and want to move on to the next level then you only need to use:
ssh banditX@localhost
1: 

2:  CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
Dealing with “-“ as the file name 
Using “cat ./-“
3: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
Dealing with spaces in filename
Use the double quote around that filename, “cat “spaces in the filename””.
4: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
Dealing with hidden file in a directory
Use “ls -a”
5: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
Find the human-readable file among others 
Since all these file begins with “-“, we need to specify “./“ before that filename when use any command
“cat ./-file00”
The way to find the only human readable file in the inhere directory is to use the “file” command, which
shows the file type. For example, “file ./-file00”.
We can use that command for each and every single file but the it would not be efficient if there were hundreds of them. So we can use “file ./-*”, which means that anything start with “-“, show me the file type
After that, we know that -file007 is the file with ASCII text, or human-readable file
So use “cat ./-file007” to see what is inside that file
6: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
We need to find a file that has the following properties:
human-readable
1033 bytes in size
not executable
For the size “find -size 1033c”, the output is “./maybehere07/.file2” . 
This means there is the only file that has 1033 bytes in size. so we use “cat ./maybehere07/.file2” 
to open that file without going to cd into that directory.

7:HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
We need to find a file that has the following properties:
owned by user bandit7
owned by group bandit6
33 bytes in size
Since it said the password is stored somewhere on the server so we want to search all, not only the bandit6 folder
We use pwd command to see our current working directory, which is “/home/bandit6”.
We will use “find / -user bandit7 -group bandit6 -size 33c“, to search everything on the server/machine here.
The output is “/var/lib/dpkg/info/bandit7.password”
So use “cat /var/lib/dpkg/info/bandit7.password” to print the content out from that file, which is also the password

8:

9:

10:

11:

12:

13:

14:

15:

16:

17:

18:

19:

20: 

21:

22:

23:

24:

25:

26:

27:

28:

29:

30:

31:

32:

33:
