<h2>❓ How to connect</h2>

`ssh <username>@bandit.labs.overthewire.org -p 2220`

- username - bandit*x* , where *x* is the current level
- password - a 32-character string, which is a random combination of letters and numbers
		   generally obtained as result of solving the previous level. 

<h2>🔰 Level - 0</h2>
 
- username - bandit0
- password - bandit0

Connect to server using ssh.

There was a readme file in the home directory. Inside the file was the password for level 1.

password for level 1 - NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

- Commands used
	- `cat readme`

<h2>🔰 Level - 1</h2>

- username - bandit1
- password - NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

There was file named '-'
Cant simply cat it. It considers '-' as a prefix for some option and pauses for it.
Tried `cat ./-` and got the password

password for level 2 - rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

- Commands used
	- `cat ./-`

<h2>🔰 Level - 2</h2>

- username - bandit2
- password - rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

There was a file named 'spaces in this filename'
As the previous one, cant simply cat it.
Tried cat 'filename' and got the password

password for level 3 - aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

- Commands used
	- `cat 'spaces in the filename'`

<h2>🔰 Level - 3</h2>

- username - bandit3
- password - aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

There was a dir, with no files.
list command with '--all' option revealed a hidden file.
Used cat to get passwd

password for level 4 - 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

- Commands used
	- `ls -la`
	- `cat`

<h2>🔰 Level - 4</h2>

- username - bandit4
- password - 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

There was 9 files inside a directory in which only one is in ASCII format
I just tried cat with all.

Could have used `file ./*` to list out all files and their types

Each of these challenges have multiple solutions. 

Some are easy
Some are efficient
Some just get the job done

password for level 5 - lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

- Commands used
	- `cat`

<h2>🔰 Level - 5</h2>

- username - bandit5
- password - lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

A number of directories with a number of files.
Hidden, executables, non readables etc.

Conditions given : required file is in ASCII format, 1033 bytes of size, and not executable

I used `find` command using 1033c as parameter for size. 

password for level 6 - P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
 

- Command used
	- `ls -la -r ./*` - listed out all files recursively
	- `ls -la -r ./* | grep 1033` - grep 1033 from output 
	- `find . -name .file2 -size 1033c` - previous o/p gave filename as .file2. So searched with it

<h2>🔰 Level - 6</h2>

- username - bandit6
- password - P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

No files where there in home.
Then I read info again. It was mentioned *somewhere on the server*

Conditions given : owned by user bandit7, group bandit6, 33 size

I used `find` command, with type as file and group name as bandit6

So many permission denied directories, and something named bandit7.password :)

password for level 7 - z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

- Commands used
	- `find / -type f -group bandit6` - list out all files in root dir belonging to group bandit6

<h2>🔰 Level - 7</h2>

- username - bandit7
- password - z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

There was a file named data.txt
lot of data of format (word : pwdlookingstuff)

Given that the right password was near the word 'millionth'

So used grep command

password for level 8 - TESKZC0XvTetK0S9xNwm25STk5iWrBvP

- Commands used
	- `cat data.txt | grep millionth`

<h2>🔰 Level - 8</h2>

- username - bandit8
- password - TESKZC0XvTetK0S9xNwm25STk5iWrBvP

There was a data.txt file
lots of password-like looking strings

Given right one occurs only once.

Used the `uniq` command, with -u option to only print the unique line.
Forgot to use `sort` first. `uniq` requires input to be sorted first.

Password for level 9 - EN632PlfYiZbn3PhVK3XOGSlNInNE00t

- Commands used
	- `sort data.txt | uniq -u`

<h2>🔰 Level - 9</h2>

- username - bandit9
- password - EN632PlfYiZbn3PhVK3XOGSlNInNE00t

There was a data.txt
Lot of non-human-readable stuff.

Given password was human readable, and preceded by some ======
I used `strings` command

Password for level10 - G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

- Commands used
	- `strings data.txt`

<h2>🔰 Level - 10</h2>

- username - bandit10
- password - G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

There was data.txt.
Base64 encoded data.

Used `base64` with -d option to decode

Password for level 11 - 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

- Commands used
	- `echo VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg== | base64 -d`

<h2>🔰 Level - 11</h2>

- username - bandit11
- password - 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

There was data.txt
ROT 13 
Used cyberchef

Password for level 12 - JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

<h2>🔰 Level - 12</h2>

- username - bandit12
- password - JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

Hardest yet. 
data.txt was given
Was a hexdump. And the input file was also compressed(multiple times and algorithms)

Checked ytb and all.
Reverted hexdump using `xxd` with option -r. Put it on a file.
used `file` to know which archive it is. It was gzip.
unzipped it. It went on for some time.
there was gzip, tar, bzip2

Password for level 13 - 
 

- Commands used 
	- `xxd -r data.txt > data` - to revert the hex dump
	- `file data` - to check which type of compressed archive it is
	- `gunzip data.gz` - to unzip gzip (need .gz as file extension)
	- `tar -xvf data.tar` - to unzip tar posix archive(.tar)
	- `bunzip2 data.bz2` - to unzip bzip2 (need .bz2)

<h2>🔰 Level - 13</h2>

- username - bandit13
- password - wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

There is a file called sshkey.private

Given, no password on this level. Password for lvl 14 is in */etc/bandit_pass/bandit14* and can be read only by bandit14
We have to login using the private ssh key given.
Looked it up how to login using key
create a file with the key
then use it in ssh command

Password for level 14 - fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq (got it after logging in)

- Commands used
	- `ssh -i key.txt bandit14@bandit.labs.overthewire.org -p 2220` 

<h2>🔰 Level - 14</h2>

- username - bandit14
- password - fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

We have to submit password of level 14 to localhost at port 30000
Did that using `nc` command. Looked up how to use it

Password for level 15 - jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

- Commands used
	- `nc localhost 30000` - and just pasted the current password in there

<h2>🔰 Level - 15</h2>

- username - bandit15
- password - jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

Need to submit current password to localhost port 30001, but using ssl encryption.
Didnt research too much. Checked youtube. It just needed to use `ncat` command (like nc but) with --ssl option

Password for level 16 - JQttfApK4SeyHwDlI9SXGR50qclOAil1

- Commands used
	- `ncat localhost 30001 --ssl` 

<h2>🔰 Level - 16</h2>

- username - bandit16
- password - JQttfApK4SeyHwDlI9SXGR50qclOAil1

A port range given (31000 - 32000)
Scan for open ports. Find which speaks ssl.
One will give the credentials.
I used nmap to scan. 5 ports where open. 
Then i bruteforced(tried each port)

Got the private key

Password for level 17 - VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

- Commands used
	- `nmap localhost -p 31000-32000`  -  Scanned ports in given range
	- `ncat localhost 31790 --ssl`   -  Passed current lvl pwd to this port
	- `ssh -i key.txt bandit14@bandit.labs.overthewire.org -p 2220`  - Created a file, changed permissions(to 600)

<h2>🔰 Level - 17</h2>

- username - bandit17
- password - VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

There is two files, passwords.new and passwords.old in home directory
The password is in new file. That's the only line different from old

I used diff command

Password for level 18 - hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

- Commands used
	- `diff passwords.new passwords.old -y --suppress-common-lines` - -y gives side by side result

<h2>🔰 Level - 18</h2>

- username - bandit18
- password - hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

Cannot login. Just as we login, it says byebye and connection is closed.
Given that changes were made to bashrc to close connection as soon as we login. The password for next level was stored in a readme file in home directory


Got to learn that we can actually execute commands directly via ssh (immeadiately as we login).
We just have to append the command at the end of the ssh command.

So i append cat command as end of ssh to read the readme file.

This execution will happen even before .bashrc is executed. So readme file will be read before we get logged out.

Password for level 19 - awhqfNnAbc1naukrpqDYcF95h7HoMTrC 

- Commands used
	- `ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme` - 'cat readme' will be executed as we login

<h2>🔰 Level - 19</h2>

- username - bandit19
- password - awhqfNnAbc1naukrpqDYcF95h7HoMTrC

There was an executable binary in home. It sets setuid bit
Basically it means it give power of the group/user it belongs to

Password was in the default folder, but can be read only by user bandit20. Since this binary gives me the power of bandit20, I used it to read the pass file.

Password for level 20 - VxCazJaVykI6W36BkBU0mJTCM8rR95XT

- Commands used
	- `./bandit20-do cat /etc/bandit_pass/bandit20`

<h2>🔰 Level - 20</h2>

- username - bandit20
- password - VxCazJaVykI6W36BkBU0mJTCM8rR95XT

A good one. There was a binary.
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21). (from site)

I listened in port 3000 using netcat on one instance. Then i connected to port 3000 using the binary from another instance. Then I passed current password through the first instance and 2nd instance sent the password for next level

Password for level 21 - NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

- Commands used -
	- `nc -lv 3000`        -    Listens on port 3000 of localhost (-l for listen)
	- `./suconnect 3000`    -    Connects to port 3000 from another instance

<h2>🔰 Level - 21</h2>

- username - bandit21
- password - NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

Cron jobs and stuff. Went to /etc/cron.d, checked the files. Found the one needed (bandit22 named file). Opened it to see that it copies level 22 pwd and store it on /tmp directory

Went there, got the flag

Password for level 22 - WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

<h2>🔰 Level - 22</h2>

- username - bandit22
- password - WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

Cronjob files. Shellscript which decides the directory inside /tmp where pwd is stored. 
Read the shellscript, got the hash for pwd file, read it from /tmp

Password for level 23 - QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

<h2>🔰 Level - 23</h2>

- username - bandit23
- password - QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

A cronjob was running by bandit24. script is visible. It executes files with owner "bandit23" and deletes all files in a directory. That directory is readable by bandit24 only. But bandit23 has write permissions in that dir. 
I got to /tmp and wrote(kinda it was already there by somebody else) a  script to cat out the password of bandit24 from bandit_pass/badnit24 file .
Got the flag.

Password for level 24 - VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

<h2>🔰 Level - 24</h2>

- username - bandit24
- password - VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

A daemon listening at port 30002 of localhost in bandit24 machine. It needs password of bandit24 and a 4 digit pin
Bruteforce.
Script to print out bandit24pass and all combination of 4 digits
output to a file. 
cat that file into connection `nc localhost 30002`

- script
	```bash
	#!/bin/bash
	for i in {9999..0000};
	do
	        echo 'VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar' $i;
	done
	```
- commands used -
	- `./my_script.sh > input.txt`
	- `cat input.txt | nc localhost 30002`

Password for level 25 - p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

<h2>🔰 Level - 25</h2>

- username - bandit25
- password - p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Tuff one

- Given: ssh privatekey for bandit26 is given in home directory.
 	     shell for bandit26 is not /bin/bash.
When logged in using ssh and private key, it immediately logs out.
Tried passing commands along with ssh command to no avail.
Checked /etc/passwd file from bandit25's shell. Found out the shell for bandit26 user is /usr/bin/showtext
Navigated to /home/bandit26 to find that there are two files bandit27-do (prolly for next chal) and text.txt.
No permissions (currently bandit25).
opened showtext file to find that it sets TERM=linux and reads text.txt with `more` command. Then it exits(0).
Thats why it logs out.

Referred some walkthroughs. 
Apparently, the file is so small that the `more` commands output buffer won't exceed screen size and, thus finishes file and returns exit(0). This logs out the connection.
Reduced screen size so small that buffered text would not fit in the screen. 
It seems you could type `v` inside the result of `more` command to open vi, and,
read an external file, using `:r` command inside vi.

- Commands used:-
	- `ssh -i key_26.txt bandit26@bandit.labs.overthewire.org -p 2220`
	- `:r /etc/bandit_pass/bandit26` (Inside vi)

Password for level 26 - c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

<h2>🔰 Level - 26</h2>

- username - bandit26
- password - c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

There was a bandit27-do, a setuid file in home directory for bandit26. 
Logged in to bandit26 like in previous level. 
Entered `v` to open v within `more` .
Then used vi commands to set shell back to /bin/bash. Now normal bash commands would work
Executed the setuid binary to `cat` the passkey file from the `/etc/bandit_pass` directory.

- Commands used:-
	- `:set shell=/bin/bash`
	- `:!ls`
	- `:!./bandit27-do`
	- `:!./bandit27-do cat /etc/bandit_pass/bandit27`

Password for level 27 - YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS	


<h2>🔰 Level - 27</h2>

- username - bandit27
- password - YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

A link to a git repo was given.
`ssh://bandit27-git@localhost/home/bandit27-git/repo`
We should clone the repo as bandit27-git (same password as bandit27) using port 2220 and get our flag.

I tried the normal `git clone command` but didn't. Said some issues with permissions.
I didnt how to specify port in this command. Also my home direcotory didnt have write permissions.
So I had to make a temp dir in /tmp.

So when I specified the port to be used is 2220, cloning was successfully done. Inside the repo was a readme file with the flag.

- Commands used:- 
	- `git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo` 

Password for level 28 - AVanL161y9rsbcJIsFHuw35rjaOM19nR

<h2>🔰 Level - 28</h2>

- username - bandit28
- password - AVanL161y9rsbcJIsFHuw35rjaOM19nR

Similar to the previous file. Instead of password, the contents of readme were :-

# Bandit Notes
Some notes for level29 of bandit.
credentials
- username: bandit29
- password: xxxxxxxxxx

It was evident that there was a password and they must have changed it. (Prolly).
So I tried git log to see other commits and indeed there it was, the previous commit replaced the password string with 
`xxxxxxxxxx`
- Commands used :-
	- `git log`

Password for level 29 - tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S