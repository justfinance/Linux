# Linux



Command Breakdown

sudo: Runs a command with superuser (root) privileges.
-: This is a flag normally used with su (like su -), which tells the system to load the target user's full profile, environment variables, and start them in their home directory. Putting it before su is technically incorrect syntax for sudo.
su: Stands for "switch user" (or substitute user). It is the actual command being executed by sudo.
ubuntu: The target username you want to switch into.
It essentially tells the system: "Use administrator privileges to switch into the ubuntu user's account."
Why This Happens (The "Why"):
When you connect via Session Manager, AWS logs you in as a temporary system user called ssm-user.
That user's "home" is in the system folders (like /var/snap/...).
When you run sudo su - ubuntu, you are telling Linux: "Switch me to the real ubuntu user and load their environment."
The - (dash) is critical. It tells Linux to also switch the directory to that user's home folder (/home/ubuntu).

(Note: Ctrl + C is the universal "panic button" in Linux. If a command is stuck, freezing, or doing something weird, Ctrl + C will almost always stop it and give you your prompt back.)
$ cd ~
$ pwd
/home/ssm-user
$ ssm-user                                   
sh: 3: ssm-user: not found
$ pwd
/home/ssm-user
$ whoami
ssm-user
$ I'm in
> cd~
> cd ~
> pwd
> ^C
$ Whoami
sh: 10: Whoami: not found
$ whoami
ssm-user
$ sudo su -ubuntu
Try 'su --help' for more information.
$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo su -  ubuntu
ubuntu@ip-172-31-15-229:~$ pwd
/home/ubuntu
ubuntu@ip-172-31-15-229:~$ pwd
/home/ubuntu
ubuntu@ip-172-31-15-229:~$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:~$ whoami
ubuntu
ubuntu@ip-172-31-15-229:~$ pwd
/home/ubuntu
ubuntu@ip-172-31-15-229:~$ whoami
ubuntu
ubuntu@ip-172-31-15-229:~$ pwd
/home/ubuntu
ubuntu@ip-172-31-15-229:~$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:~$ exit
exit
ubuntu@ip-172-31-15-229:~$ exit
exit
ubuntu@ip-172-31-15-229:~$ exit
logout
ubuntu@ip-172-31-15-229:/home/ssm-user$ cd ~
ubuntu@ip-172-31-15-229:~$ cd ~
ubuntu@ip-172-31-15-229:~$ exit
exit
$ ^C
$ pwd
/home/ssm-user
$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ exit
exit
ubuntu@ip-172-31-15-229:/home/ssm-user$ ^C
ubuntu@ip-172-31-15-229:/home/ssm-user$ exit
exit
ubuntu@ip-172-31-15-229:/home/ssm-user$ exit
exit
ubuntu@ip-172-31-15-229:/home/ssm-user$ exit
exit
ubuntu@ip-172-31-15-229:/home/ssm-user$ cd ~
ubuntu@ip-172-31-15-229:~$ exit
exit
$ pwd
/home/ssm-user
$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su  ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ whomami
Command 'whomami' not found, did you mean:
  command 'whoami' from deb coreutils-from-gnu (0.0.0~ubuntu25)
  command 'whoami' from deb coreutils-from-uutils (0.0.0~ubuntu25)
  command 'whoami' from deb coreutils-from-busybox (0.0.0~ubuntu25)
  command 'whoami' from deb coreutils-from-toybox (0.0.0~ubuntu25)
Try: sudo apt install <deb name>
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
ubuntu@ip-172-31-15-229:/home/ssm-user$ suddo - su ubuntu
Command 'suddo' not found, did you mean:
  command 'sudo' from deb sudo (1.9.17p2-1ubuntu3)
  command 'sudo' from deb sudo-rs (0.2.13-0ubuntu1)
Try: sudo apt install <deb name>
ubuntu@ip-172-31-15-229:/home/ssm-user$ sudo - su ubuntu 
ubuntu@ip-172-31-15-229:/home/ssm-user$ whoami
ubuntu
ubuntu@ip-172-31-15-229:/home/ssm-user$ pwd
/home/ssm-user
> To get to the /home/ubuntu directory from where you are, you just need to change your directory.
Because you used a command that kept your current working directory (leaving you in /home/ssm-user), you simply need to tell the system to go home.
ubuntu@ip-172-31-15-229:/home/ssm-user$ cd ~
ubuntu@ip-172-31-15-229:~$ cd home/ubuntu
bash: cd: home/ubuntu: No such file or directory
ubuntu@ip-172-31-15-229:~$ cd /home/ubuntu
ubuntu@ip-172-31-15-229:~$ whoami
ubuntu
ubuntu@ip-172-31-15-229:~$ pwd
/home/ubuntu
ubuntu@ip-172-31-15-229:~$ 
