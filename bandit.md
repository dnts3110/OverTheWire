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

8:cvX2JJa4CFALtqS87jk27qwqGhBM9plV
Use "cat data.txt | grep "millionth" to search for the lines that have the given pattern or string in them.

9:UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
Use "cat data.txt | sort | uniq -u" to search for the unique line of text.

10:truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
Use "strings data.txt| grep "=="" it will give us the human-readable strings in a file, and search for several "=" characters

11:IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
Use "base64 -d data.txt" to decode the base64 encoded data.

12:5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
Use "cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'" to decrypt the rot13 encryption

13:8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
mkdir /tmp/banditgame/
cp data.txt /tmp/banditgame/
cd /tmp/banditgame/
xxd -r data.txt data.gz 
gzip -d data.gz && bzip2 -d -q data
mv data.out data.gz && 
gzip -d data.gz 
tar xf data
tar xf data5.bin
bzip2 -d -q data6.bin
tar xf data6.bin.out
mv data8.bin data8.gz
gzip -d data8.gz
cat data8
These are the process do decompress that hexdump file that has been repeatedly compressed

14: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
Use "ssh bandit14@localhost -i sshkey.private" to access the SSH using an ssh private key.
Then "cat /etc/bandit_pass/bandit14" to have the password to use it next time without
the hassle of going to level 13 to access level 14.

15: BfMYroe26WYalil77FoDi9qh59eK5xNr
Use "nc localhost 30000" to submit the password of level 14 to prot 30000 on localhost.
Note: nc stands for netcat.

16: cluFn7wTiGryunymYOu4RcffSxQluehd
Use "openssl s_client -connect localhost:30001" to access to the port 30001 on localhost using SSL encryption, and then we can submit the password from level 15.

17: xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn
Use "nmap -A localhost -p 31000-32000" to do an aggressive scan to see which port is not
echoing back/send back whatever you send to it.
The results shows the port 31790 is the only one that doesnt echo.
Use "openssl s_client -connect localhost:31790" to connect to that port and submit the password from level 16. The port will then send back what the RSA private key. We need it as a file to use it to connect using SSL encryption.
We first need to make a directory in the temp directory "mkdir /tmp/son1", then "nano /tmp/son1/key.private" to create the file with the RSA private key for SSL encryption.
Then we use "ssh bandit17@localhost -i /tmp/son1/key.private" to connect to level 17 using SSL encryption. However, the terminal then tell me that "Permissions 0644 for '/tmp/son1/key.private' are too open.". Thus we need to use "chmod 600 /tmp/son1/key.private
", which means only the owner has full read and write access to the file, while no other users can access the file.
After we connect successfully to level 17, use "cat /etc/bandit_pass/bandit17" to achieve the password of level 17 so we can access level 17 without going again from level 16

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
