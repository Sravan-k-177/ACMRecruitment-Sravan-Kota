Linux: OverTheWire

Level 0:
Username: ssh bandit0@bandit.labs.overthewire.org -p 2220
Pw: bandit0
Note: 2220 is the port number. Always use the ‘exit’ command to logout from one bandit

Level 0 – Level 1:
Username:  ssh bandit1@bandit.labs.overthewire.org -p 2220
Pw: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Level 2 – Level 3:
Username: ssh bandit2@bandit.labs.overthewire.org -p 2220
Pw: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
Note: cat spaces\ in\ this\ filename

Level 3- Level 4:
Username: ssh bandit3@bandit.labs.overthewire.org -p 2220
Pw: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
Note: to view hidden files: ls -a/A

Level 4- Level 5:
Username: ssh bandit4@bandit.labs.overthewire.org -p 2220
Pw: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
Note: when using special characters, use the forward slash ‘/’ and when giving space use the backward slash ‘\’. If we want to check if the given content in a file is human readable or not, use ‘file ./<file name>’. the ‘./’ can be used if there’s any special character is there.

Level 5- Level 6:
Username: ssh bandit5@bandit.labs.overthewire.org -p 2220
Pw: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
Note: check for all the file permissions using ‘ls -lR’. Check the file size and then narrow down your search.

Level 6- Level 7:
Username: ssh bandit6@bandit.labs.overthewire.org -p 2220
Pw: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
Note: “/var/lib/dpkg/info/bandit7.password” is the path to the password. Use the cat command with the path to see the password.



Level 7- Level 8:
Username: ssh bandit7@bandit.labs.overthewire.org -p 2220
Pw: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
Note: see the data.txt file which has large size, and use the cat command to view the file with the grep command the word which they have given.

Level 8- Level 9:
Username: ssh bandit8@bandit.labs.overthewire.org -p 2220
Pw: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
Note: use the sort and the uniq -u commands (found this sol in google)

Level 9- Level 10:
Username: ssh bandit9@bandit.labs.overthewire.org -p 2220
Pw: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
Note: strings- this command specifies human readable strings. Later use the grep command with ‘=’.


Level 10- Level 11:
Username: ssh bandit10@bandit.labs.overthewire.org -p 2220
Pw:  dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
Note: “cat data.txt | base64 -d” the base64 converts binary text representations into string texts. ‘-d’ displays in standard output.

Level 11- Level 12:
Username: ssh bandit11@bandit.labs.overthewire.org -p 2220
Pw: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
Note: 

here this command “ tr ‘A-Za-z’ ‘N-ZA-Mn-za-m’” the 13th letter after a is n so there is shift in letters from one to another.

Level 12- Level 13:
Username: ssh bandit12@bandit.labs.overthewire.org -p 2220
Pw: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
Note: mkdir used to create a new directory. cp <source> <destination> used to copy files. mv <source> <destination> moves or renames the files. Hexdumps are basically data that cannot be represented in string format so the data shown in hex values. xxd <input file> <output file> used to create hexdumps. Compression is basically reducing the size of the file without doing any damage to the information present in the file. gzip- command used to compress the file, gzip -d used to decompress the file. gzip file usually ends with .gz. 

    1. Create a new directory using the ‘mktemp -d command’ and cd to that directory.
    2. Change the data.txt file to the newly created directory and rename it to data to remove the .txt file extension.
    3. Use the xxd command to convert the data into its binary equivalent.
    4. Use the file command to see what type of data stored in file. File compressed using gzip, so use the gunzip command to decompress it.











Level 13- Level 14:
Username:
Pw: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Notes: -i keys allows only the user with the private key to access the ssh. Local host is the machine that the user is currently working on. 

bandit13@bandit:~$ ls
sshkey.private

bandit13@bandit:~$ ssh -i sshkey.private -p 2220 bandit14@localhost
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14

Level 14- Level 15:
Username: ssh -I sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
Pw: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Notes: the password that we have to enter right after typing in the username is the one that we got in level 13-14. Since this is a private key we have to get the password for this key and that should be typed after accessing the local host. 
Local host is a hostname which has the IP address ‘127.0.0.1’. Used to access network services.
nc or netcat- command that is used to read and write data over a network. Syntax: nc <host> <port>.


Level 15- Level 16:
Username: ssh bandit15@bandit.labs.overthewire.org -p 2220
Pw: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
Notes: OpenSSL is a library for secure communication over networks. openssl s_client is the command that is used to connect to the server using SSL/TLS.
SSL: Secure Sockets Layer
TSL: Transport Layer Security
To solve this level we are first connecting to the localhost server using openSSL and sending pw to this level. The server returns the password for next level.



Level 16- Level 17:
Username: ssh -i private16.key bandit17@localhost -p 2220
Pw:MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
Notes: first the the port 31000-32000 is scanned via nmap. 


Now each port is being opened and checked using the command ncat –ssl localhost <port>


Here the pw for the level 16 has to be typed and we get a private rsa key which has to be stored in a file called private16.key
The file permission has to be changed to 700


Now bandit17 has to be accessed





Level 17- Level 18:
Username: ssh bandit18@bandit.labs.overthewire.org -p 2220
Pw: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
Notes:we have to see all the files that are present in the home directory. there is one line which is different in both the files and the different line in the password.new file is the pw for level 18. The diff command can be used, this command gives us the difference between both the files. 



open a new terminal and type in the username for level 18. Your supposed to get the message:







