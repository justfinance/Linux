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




11/23/2026, on Ubuntu:

ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ la /ls
ls: cannot access '/ls': No such file or directory
ossau@LAPTOP-2HK683AM:~$ la -ls
total 28
4 -rw------- 1 ossau ossau  174 Nov 17 09:37 .bash_history
4 -rw-r--r-- 1 ossau ossau  220 Nov 16 16:15 .bash_logout
4 -rw-r--r-- 1 ossau ossau 3771 Nov 16 16:15 .bashrc
4 drwxr-x--- 4 ossau ossau 4096 Nov 16 16:17 .cache
4 drwxr-x--- 3 ossau ossau 4096 Nov 16 16:17 .config
4 -rw------- 1 ossau ossau   20 Nov 16 16:24 .lesshst
0 -rw-rw-r-- 1 ossau ossau    0 Nov 17 09:32 .motd_shown
4 -rw-r--r-- 1 ossau ossau  807 Nov 16 16:15 .profile
ossau@LAPTOP-2HK683AM:~$ ls -la
total 36
drwxr-x--- 4 ossau ossau 4096 Nov 17 08:15 .
drwxr-xr-x 3 root  root  4096 Nov 16 16:15 ..
-rw------- 1 ossau ossau  174 Nov 17 09:37 .bash_history
-rw-r--r-- 1 ossau ossau  220 Nov 16 16:15 .bash_logout
-rw-r--r-- 1 ossau ossau 3771 Nov 16 16:15 .bashrc
drwxr-x--- 4 ossau ossau 4096 Nov 16 16:17 .cache
drwxr-x--- 3 ossau ossau 4096 Nov 16 16:17 .config
-rw------- 1 ossau ossau   20 Nov 16 16:24 .lesshst
-rw-rw-r-- 1 ossau ossau    0 Nov 17 09:32 .motd_shown
-rw-r--r-- 1 ossau ossau  807 Nov 16 16:15 .profile
ossau@LAPTOP-2HK683AM:~$ ls -la
total 36
drwxr-x--- 4 ossau ossau 4096 Nov 17 08:15 .
drwxr-xr-x 3 root  root  4096 Nov 16 16:15 ..
-rw------- 1 ossau ossau  174 Nov 17 09:37 .bash_history
-rw-r--r-- 1 ossau ossau  220 Nov 16 16:15 .bash_logout
-rw-r--r-- 1 ossau ossau 3771 Nov 16 16:15 .bashrc
drwxr-x--- 4 ossau ossau 4096 Nov 16 16:17 .cache
drwxr-x--- 3 ossau ossau 4096 Nov 16 16:17 .config
-rw------- 1 ossau ossau   20 Nov 16 16:24 .lesshst
-rw-rw-r-- 1 ossau ossau    0 Nov 17 09:32 .motd_shown
-rw-r--r-- 1 ossau ossau  807 Nov 16 16:15 .profile
ossau@LAPTOP-2HK683AM:~$ cat  /ewtc/os-release
cat: /ewtc/os-release: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04.1 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
ossau@LAPTOP-2HK683AM:~$ sudo apt update
[sudo: authenticate] Password:
Hit:1 http://archive.ubuntu.com/ubuntu resolute InRelease
Get:2 http://archive.ubuntu.com/ubuntu resolute-updates InRelease [137 kB]
Get:3 http://archive.ubuntu.com/ubuntu resolute-backports InRelease [137 kB]
Get:4 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 Packages [872 kB]
Get:5 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 Components [110 kB]
Get:6 http://archive.ubuntu.com/ubuntu resolute-updates/universe amd64 Packages [391 kB]
Get:7 http://archive.ubuntu.com/ubuntu resolute-updates/universe Translation-en [123 kB]
Get:8 http://archive.ubuntu.com/ubuntu resolute-updates/universe amd64 Components [201 kB]
Get:9 http://archive.ubuntu.com/ubuntu resolute-backports/universe amd64 Components [1056 B]
Get:10 http://security.ubuntu.com/ubuntu resolute-security InRelease [137 kB]
Get:11 http://security.ubuntu.com/ubuntu resolute-security/main amd64 Packages [718 kB]
Get:12 http://security.ubuntu.com/ubuntu resolute-security/main amd64 Components [46.7 kB]
Get:13 http://security.ubuntu.com/ubuntu resolute-security/universe amd64 Packages [220 kB]
Get:14 http://security.ubuntu.com/ubuntu resolute-security/universe amd64 Components [62.8 kB]
Fetched 3156 kB in 4s (805 kB/s)
144 packages can be upgraded. Run 'apt list --upgradable' to see them.
ossau@LAPTOP-2HK683AM:~$ ls -la
total 36
drwxr-x--- 4 ossau ossau 4096 Nov 17 08:15 .
drwxr-xr-x 3 root  root  4096 Nov 16 16:15 ..
-rw------- 1 ossau ossau  174 Nov 17 09:37 .bash_history
-rw-r--r-- 1 ossau ossau  220 Nov 16 16:15 .bash_logout
-rw-r--r-- 1 ossau ossau 3771 Nov 16 16:15 .bashrc
drwxr-x--- 4 ossau ossau 4096 Nov 16 16:17 .cache
drwxr-x--- 3 ossau ossau 4096 Nov 16 16:17 .config
-rw------- 1 ossau ossau   20 Nov 16 16:24 .lesshst
-rw-rw-r-- 1 ossau ossau    0 Nov 17 09:32 .motd_shown
-rw-r--r-- 1 ossau ossau  807 Nov 16 16:15 .profile
ossau@LAPTOP-2HK683AM:~$ sudo apt upgrade -y
Upgrading:
  apt                      gpgsm                     libheif1               libx11-6                 python3.14-minimal
  base-files               gpgv                      liblzma5               libx11-data              rsyslog
  bsdextrautils            gtk-update-icon-cache     libmount1              libx11-xcb1              rust-coreutils
  bsdutils                 libaom3                   libnetplan1            libxml2-16               snapd
  bubblewrap               libapt-pkg7.0             libnss-systemd         libxtst6                 sudo
  ca-certificates          libattr1                  libpam-modules         locales                  sudo-rs
  cloud-init               libaudit-common           libpam-modules-bin     login                    systemd
  cloud-init-base          libaudit1                 libpam-runtime         motd-news-config         systemd-cryptsetup
  curl                     libblkid1                 libpam-systemd         mount                    systemd-resolved
  diffutils                libbrotli1                libpam0g               netplan-generator        systemd-sysv
  dirmngr                  libbz2-1.0                libpcre2-8-0           netplan.io               tmux
  distro-info-data         libc-bin                  libperl5.40            openssh-client           tzdata
  eject                    libc-gconv-modules-extra  libpng16-16t64         openssl                  ubuntu-insights
  fdisk                    libc6                     libpolkit-agent-1-0    openssl-provider-legacy  ubuntu-minimal
  gir1.2-girepository-3.0  libcurl3t64-gnutls        libpolkit-gobject-1-0  perl                     ubuntu-pro-client
  gir1.2-glib-2.0          libcurl4t64               libpython3.14          perl-base                ubuntu-pro-client-l10n
  git                      libevent-core-2.1-7t64    libpython3.14-minimal  perl-modules-5.40        ubuntu-release-upgrader-core
  git-man                  libexpat1                 libpython3.14-stdlib   polkitd                  ubuntu-wsl
  glycin-loaders           libfdisk1                 librsvg2-2             python3-cryptography     udev
  glycin-thumbnailers      libfreetype6              librsvg2-common        python3-distupgrade      util-linux
  gnu-coreutils            libgcrypt20               libsmartcols1          python3-jwt              vim
  gnupg                    libgirepository-2.0-0     libsqlite3-0           python3-netplan          vim-common
  gnupg-l10n               libglib2.0-0t64           libssh2-1t64           python3-pyasn1           vim-runtime
  gnupg-utils              libglib2.0-bin            libssl3t64             python3-requests         vim-tiny
  gpg                      libglib2.0-data           libsystemd-shared      python3-twisted          wsl-pro-service
  gpg-agent                libglycin-2-0             libsystemd0            python3-urllib3          xxd
  gpg-wks-client           libheif-plugin-aomdec     libudev1               python3.14               xz-utils
  gpgconf                  libheif-plugin-aomenc     libuuid1               python3.14-gdbm          zlib1g

Not upgrading yet due to phasing:
  distro-info  python3-distro-info  python3-software-properties  software-properties-common

Summary:
  Upgrading: 140, Installing: 0, Removing: 0, Not Upgrading: 4
102 standard LTS security updates
  Download size: 130 MB
  Freed space: 57.4 MB

Get:1 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 motd-news-config all 14ubuntu6.3 [5286 B]
Get:2 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libc-gconv-modules-extra amd64 2.43-2ubuntu2.7 [1363 kB]
Get:3 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libc6 amd64 2.43-2ubuntu2.7 [2104 kB]
Get:4 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 base-files amd64 14ubuntu6.3 [74.7 kB]
Get:5 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 diffutils amd64 1:3.12-1ubuntu0.1 [176 kB]
Get:6 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libperl5.40 amd64 5.40.1-7ubuntu0.4 [4888 kB]
Get:7 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 perl amd64 5.40.1-7ubuntu0.4 [262 kB]
Get:8 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 perl-base amd64 5.40.1-7ubuntu0.4 [1851 kB]
Get:9 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 perl-modules-5.40 all 5.40.1-7ubuntu0.4 [3213 kB]
Get:10 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libbz2-1.0 amd64 1.0.8-6ubuntu0.1 [36.2 kB]
Get:11 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 zlib1g amd64 1:1.3.dfsg+really1.3.1-1ubuntu3.2 [61.8 kB]
Get:12 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 eject amd64 2.41.3-3ubuntu2.2 [40.3 kB]
Get:13 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libfdisk1 amd64 2.41.3-3ubuntu2.2 [164 kB]
Get:14 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 bsdextrautils amd64 2.41.3-3ubuntu2.2 [86.7 kB]
Get:15 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libsmartcols1 amd64 2.41.3-3ubuntu2.2 [84.9 kB]
Get:16 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 fdisk amd64 2.41.3-3ubuntu2.2 [139 kB]
Get:17 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libblkid1 amd64 2.41.3-3ubuntu2.2 [126 kB]
Get:18 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libmount1 amd64 2.41.3-3ubuntu2.2 [159 kB]
Get:19 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 mount amd64 2.41.3-3ubuntu2.2 [136 kB]
Get:20 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libuuid1 amd64 2.41.3-3ubuntu2.2 [36.7 kB]
Get:21 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 util-linux amd64 2.41.3-3ubuntu2.2 [1070 kB]
Get:22 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libc-bin amd64 2.43-2ubuntu2.7 [701 kB]
Get:23 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 liblzma5 amd64 5.8.3-1ubuntu0.1 [146 kB]
Get:24 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 openssl-provider-legacy amd64 3.5.5-1ubuntu3.7 [39.7 kB]
Get:25 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libssl3t64 amd64 3.5.5-1ubuntu3.7 [2368 kB]
Get:26 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libsystemd0 amd64 259.9-0ubuntu0.1 [481 kB]
Get:27 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpam-systemd amd64 259.9-0ubuntu0.1 [273 kB]
Get:28 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 systemd-sysv amd64 259.9-0ubuntu0.1 [9420 B]
Get:29 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 systemd-resolved amd64 259.9-0ubuntu0.1 [300 kB]
Get:30 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libsystemd-shared amd64 259.9-0ubuntu0.1 [2473 kB]
Get:31 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 systemd amd64 259.9-0ubuntu0.1 [3137 kB]
Get:32 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 systemd-cryptsetup amd64 259.9-0ubuntu0.1 [125 kB]
Get:33 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 udev amd64 259.9-0ubuntu0.1 [1525 kB]
Get:34 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libudev1 amd64 259.9-0ubuntu0.1 [151 kB]
Get:35 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libaudit-common all 1:4.1.2-1ubuntu0.1 [4958 B]
Get:36 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libaudit1 amd64 1:4.1.2-1ubuntu0.1 [55.1 kB]
Get:37 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpam0g amd64 1.7.0-5ubuntu3.2 [65.0 kB]
Get:38 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpam-runtime all 1.7.0-5ubuntu3.2 [149 kB]
Get:39 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpam-modules-bin amd64 1.7.0-5ubuntu3.2 [45.6 kB]
Get:40 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpam-modules amd64 1.7.0-5ubuntu3.2 [193 kB]
Get:41 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libapt-pkg7.0 amd64 3.2.1ubuntu0.1 [1139 kB]
Get:42 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libgcrypt20 amd64 1.12.0-2ubuntu1.1 [675 kB]
Get:43 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gpgv amd64 2.4.8-4ubuntu3.1 [155 kB]
Get:44 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 apt amd64 3.2.1ubuntu0.1 [1507 kB]
Get:45 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gnu-coreutils amd64 9.7-3ubuntu2.1 [1339 kB]
Get:46 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 login amd64 1:4.16.0-2+really2.41.3-3ubuntu2.2 [85.9 kB]
Get:47 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libexpat1 amd64 2.7.4-1ubuntu0.2 [98.8 kB]
Get:48 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpython3.14 amd64 3.14.4-1ubuntu0.2 [2579 kB]
Get:49 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3.14 amd64 3.14.4-1ubuntu0.2 [830 kB]
Get:50 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpython3.14-stdlib amd64 3.14.4-1ubuntu0.2 [2415 kB]
Get:51 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3.14-minimal amd64 3.14.4-1ubuntu0.2 [2579 kB]
Get:52 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpython3.14-minimal amd64 3.14.4-1ubuntu0.2 [916 kB]
Get:53 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 tzdata all 2026e-0ubuntu0.26.04.1 [193 kB]
Get:54 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libsqlite3-0 amd64 3.46.1-9ubuntu0.3 [720 kB]
Get:55 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 sudo amd64 1.9.17p2-1ubuntu3.2 [955 kB]
Get:56 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libattr1 amd64 1:2.5.2-4ubuntu0.1 [12.0 kB]
Get:57 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpcre2-8-0 amd64 10.46-1ubuntu0.1 [257 kB]
Get:58 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 rust-coreutils amd64 0.10.0-1ubuntu2~26.04.1 [4515 kB]
Get:59 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 bsdutils amd64 1:2.41.3-3ubuntu2.2 [80.7 kB]
Get:60 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 openssl amd64 3.5.5-1ubuntu3.7 [1243 kB]
Get:61 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ca-certificates all 20260816ubuntu0.26.04.2 [138 kB]
Get:62 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 distro-info-data all 2026.10.12-0ubuntu0.26.04.1 [6382 B]
Get:63 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libglib2.0-data all 2.88.0-1ubuntu0.1 [38.5 kB]
Get:64 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libglib2.0-bin amd64 2.88.0-1ubuntu0.1 [99.4 kB]
Get:65 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gir1.2-girepository-3.0 amd64 2.88.0-1ubuntu0.1 [25.2 kB]
Get:66 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libgirepository-2.0-0 amd64 2.88.0-1ubuntu0.1 [76.1 kB]
Get:67 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gir1.2-glib-2.0 amd64 2.88.0-1ubuntu0.1 [183 kB]
Get:68 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libglib2.0-0t64 amd64 2.88.0-1ubuntu0.1 [1598 kB]
Get:69 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-netplan amd64 1.2-1ubuntu5.1 [24.8 kB]
Get:70 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 netplan-generator amd64 1.2-1ubuntu5.1 [65.1 kB]
Get:71 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 netplan.io amd64 1.2-1ubuntu5.1 [69.6 kB]
Get:72 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libnetplan1 amd64 1.2-1ubuntu5.1 [132 kB]
Get:73 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libnss-systemd amd64 259.9-0ubuntu0.1 [227 kB]
Get:74 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libxml2-16 amd64 2.15.2+dfsg-0.1ubuntu0.3 [607 kB]
Get:75 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 locales all 2.43-2ubuntu2.7 [4226 kB]
Get:76 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 rsyslog amd64 8.2512.0-1ubuntu4.2 [536 kB]
Get:77 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 sudo-rs amd64 0.2.13-0ubuntu1.2 [596 kB]
Get:78 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ubuntu-pro-client-l10n amd64 38ubuntu0~26.04 [19.8 kB]
Get:79 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ubuntu-pro-client amd64 38ubuntu0~26.04 [243 kB]
Get:80 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 vim amd64 2:9.1.2141-1ubuntu4.10 [2069 kB]
Get:81 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 vim-tiny amd64 2:9.1.2141-1ubuntu4.10 [869 kB]
Get:82 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 vim-runtime all 2:9.1.2141-1ubuntu4.10 [7516 kB]
Get:83 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 vim-common all 2:9.1.2141-1ubuntu4.10 [495 kB]
Get:84 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ubuntu-minimal amd64 1.570.4 [8766 B]
Get:85 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 xxd amd64 2:9.1.2141-1ubuntu4.10 [69.4 kB]
Get:86 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpng16-16t64 amd64 1.6.57-1ubuntu0.1 [195 kB]
Get:87 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libx11-6 amd64 2:1.8.13-1ubuntu0.1 [658 kB]
Get:88 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libx11-xcb1 amd64 2:1.8.13-1ubuntu0.1 [7980 B]
Get:89 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libx11-data all 2:1.8.13-1ubuntu0.1 [115 kB]
Get:90 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libbrotli1 amd64 1.2.0-3ubuntu0.1 [343 kB]
Get:91 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libssh2-1t64 amd64 1.11.1-1ubuntu0.26.04.4 [138 kB]
Get:92 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libcurl3t64-gnutls amd64 8.18.0-1ubuntu2.8 [421 kB]
Get:93 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 git-man all 1:2.53.0-1ubuntu1.1 [1197 kB]
Get:94 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 git amd64 1:2.53.0-1ubuntu1.1 [4223 kB]
Get:95 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 openssh-client amd64 1:10.2p1-2ubuntu3.8 [936 kB]
Get:96 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ubuntu-release-upgrader-core all 1:26.04.27 [25.0 kB]
Get:97 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-distupgrade all 1:26.04.27 [107 kB]
Get:98 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3.14-gdbm amd64 3.14.4-1ubuntu0.2 [29.5 kB]
Get:99 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 xz-utils amd64 5.8.3-1ubuntu0.1 [406 kB]
Get:100 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 bubblewrap amd64 0.11.1-1ubuntu0.3 [51.0 kB]
Get:101 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 cloud-init-base all 26.2-0ubuntu1~26.04.1 [591 kB]
Get:102 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 cloud-init all 26.2-0ubuntu1~26.04.1 [2116 B]
Get:103 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-urllib3 all 2.6.3-1ubuntu1.2 [97.6 kB]
Get:104 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-requests all 2.32.5+dfsg-1ubuntu1.1 [51.9 kB]
Get:105 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 curl amd64 8.18.0-1ubuntu2.8 [273 kB]
Get:106 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libcurl4t64 amd64 8.18.0-1ubuntu2.8 [430 kB]
Get:107 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gnupg-utils amd64 2.4.8-4ubuntu3.1 [127 kB]
Get:108 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gpg-wks-client amd64 2.4.8-4ubuntu3.1 [71.9 kB]
Get:109 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 dirmngr amd64 2.4.8-4ubuntu3.1 [327 kB]
Get:110 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gpg-agent amd64 2.4.8-4ubuntu3.1 [236 kB]
Get:111 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gpg amd64 2.4.8-4ubuntu3.1 [637 kB]
Get:112 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gpgconf amd64 2.4.8-4ubuntu3.1 [106 kB]
Get:113 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gnupg all 2.4.8-4ubuntu3.1 [311 kB]
Get:114 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gpgsm amd64 2.4.8-4ubuntu3.1 [239 kB]
Get:115 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libaom3 amd64 3.13.1-2ubuntu0.1 [1969 kB]
Get:116 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libheif-plugin-aomenc amd64 1.21.2-3ubuntu0.7 [20.9 kB]
Get:117 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libheif1 amd64 1.21.2-3ubuntu0.7 [551 kB]
Get:118 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libheif-plugin-aomdec amd64 1.21.2-3ubuntu0.7 [15.6 kB]
Get:119 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 librsvg2-common amd64 2.61.3+dfsg-3ubuntu0.1 [153 kB]
Get:120 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 librsvg2-2 amd64 2.61.3+dfsg-3ubuntu0.1 [1850 kB]
Get:121 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 glycin-loaders amd64 2.1.5+ds-0ubuntu0.2 [2984 kB]
Get:122 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libglycin-2-0 amd64 2.1.5+ds-0ubuntu0.2 [1487 kB]
Get:123 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 glycin-thumbnailers amd64 2.1.5+ds-0ubuntu0.2 [223 kB]
Get:124 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gnupg-l10n all 2.4.8-4ubuntu3.1 [68.8 kB]
Get:125 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 gtk-update-icon-cache amd64 4.22.4+ds-0ubuntu0.2 [42.7 kB]
Get:126 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libevent-core-2.1-7t64 amd64 2.1.12-stable-10ubuntu0.2 [92.6 kB]
Get:127 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libfreetype6 amd64 2.14.2+dfsg-1ubuntu0.2 [409 kB]
Get:128 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 polkitd amd64 127-2ubuntu1.1 [102 kB]
Get:129 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpolkit-agent-1-0 amd64 127-2ubuntu1.1 [18.1 kB]
Get:130 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libpolkit-gobject-1-0 amd64 127-2ubuntu1.1 [45.8 kB]
Get:131 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 libxtst6 amd64 2:1.2.5-1ubuntu0.1 [13.2 kB]
Get:132 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-cryptography amd64 46.0.5-1ubuntu2.2 [1160 kB]
Get:133 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-jwt all 2.10.1-4ubuntu1.3 [23.8 kB]
Get:134 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-pyasn1 all 0.6.3-1ubuntu0.2 [57.6 kB]
Get:135 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 python3-twisted all 25.5.0-5ubuntu0.2 [2075 kB]
Get:136 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 snapd amd64 2.78+ubuntu26.04 [25.3 MB]
Get:137 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 tmux amd64 3.6a-2ubuntu0.2 [517 kB]
Get:138 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ubuntu-insights amd64 0.9.3ubuntu0.1 [3122 kB]
Get:139 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 ubuntu-wsl amd64 1.570.4 [8694 B]
Get:140 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 wsl-pro-service amd64 0.1.19ubuntu2.1 [4629 kB]
Fetched 130 MB in 18s (7316 kB/s)
Extracting templates from packages: 100%
Preconfiguring packages ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../motd-news-config_14ubuntu6.3_all.deb ...
Unpacking motd-news-config (14ubuntu6.3) over (14ubuntu6.2) ...
Preparing to unpack .../libc-gconv-modules-extra_2.43-2ubuntu2.7_amd64.deb ...
Unpacking libc-gconv-modules-extra:amd64 (2.43-2ubuntu2.7) over (2.43-2ubuntu2.3) ...
Setting up libc-gconv-modules-extra:amd64 (2.43-2ubuntu2.7) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libc6_2.43-2ubuntu2.7_amd64.deb ...
Unpacking libc6:amd64 (2.43-2ubuntu2.7) over (2.43-2ubuntu2.3) ...
Setting up libc6:amd64 (2.43-2ubuntu2.7) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../base-files_14ubuntu6.3_amd64.deb ...
Unpacking base-files (14ubuntu6.3) over (14ubuntu6.2) ...
Setting up base-files (14ubuntu6.3) ...
motd-news.service is a disabled or a static unit not running, not starting it.
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../diffutils_1%3a3.12-1ubuntu0.1_amd64.deb ...
Unpacking diffutils (1:3.12-1ubuntu0.1) over (1:3.12-1) ...
Setting up diffutils (1:3.12-1ubuntu0.1) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libperl5.40_5.40.1-7ubuntu0.4_amd64.deb ...
Unpacking libperl5.40:amd64 (5.40.1-7ubuntu0.4) over (5.40.1-7ubuntu0.1) ...
Preparing to unpack .../perl_5.40.1-7ubuntu0.4_amd64.deb ...
Unpacking perl (5.40.1-7ubuntu0.4) over (5.40.1-7ubuntu0.1) ...
Preparing to unpack .../perl-base_5.40.1-7ubuntu0.4_amd64.deb ...
Unpacking perl-base (5.40.1-7ubuntu0.4) over (5.40.1-7ubuntu0.1) ...
Setting up perl-base (5.40.1-7ubuntu0.4) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../perl-modules-5.40_5.40.1-7ubuntu0.4_all.deb ...
Unpacking perl-modules-5.40 (5.40.1-7ubuntu0.4) over (5.40.1-7ubuntu0.1) ...
Preparing to unpack .../libbz2-1.0_1.0.8-6ubuntu0.1_amd64.deb ...
Unpacking libbz2-1.0:amd64 (1.0.8-6ubuntu0.1) over (1.0.8-6build2) ...
Setting up libbz2-1.0:amd64 (1.0.8-6ubuntu0.1) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../zlib1g_1%3a1.3.dfsg+really1.3.1-1ubuntu3.2_amd64.deb ...
Unpacking zlib1g:amd64 (1:1.3.dfsg+really1.3.1-1ubuntu3.2) over (1:1.3.dfsg+really1.3.1-1ubuntu3) ...
Setting up zlib1g:amd64 (1:1.3.dfsg+really1.3.1-1ubuntu3.2) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../eject_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking eject (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Preparing to unpack .../libfdisk1_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking libfdisk1:amd64 (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Preparing to unpack .../bsdextrautils_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking bsdextrautils (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Preparing to unpack .../libsmartcols1_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking libsmartcols1:amd64 (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Setting up libsmartcols1:amd64 (2.41.3-3ubuntu2.2) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../fdisk_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking fdisk (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Preparing to unpack .../libblkid1_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking libblkid1:amd64 (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Setting up libblkid1:amd64 (2.41.3-3ubuntu2.2) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libmount1_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking libmount1:amd64 (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Setting up libmount1:amd64 (2.41.3-3ubuntu2.2) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../mount_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking mount (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Preparing to unpack .../libuuid1_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking libuuid1:amd64 (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Setting up libuuid1:amd64 (2.41.3-3ubuntu2.2) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../util-linux_2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking util-linux (2.41.3-3ubuntu2.2) over (2.41.3-3ubuntu2) ...
Setting up util-linux (2.41.3-3ubuntu2.2) ...
fstrim.service is a disabled or a static unit not running, not starting it.
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libc-bin_2.43-2ubuntu2.7_amd64.deb ...
Unpacking libc-bin (2.43-2ubuntu2.7) over (2.43-2ubuntu2.3) ...
Setting up libc-bin (2.43-2ubuntu2.7) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../liblzma5_5.8.3-1ubuntu0.1_amd64.deb ...
Unpacking liblzma5:amd64 (5.8.3-1ubuntu0.1) over (5.8.3-1) ...
Setting up liblzma5:amd64 (5.8.3-1ubuntu0.1) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../openssl-provider-legacy_3.5.5-1ubuntu3.7_amd64.deb ...
Unpacking openssl-provider-legacy (3.5.5-1ubuntu3.7) over (3.5.5-1ubuntu3.4) ...
Setting up openssl-provider-legacy (3.5.5-1ubuntu3.7) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libssl3t64_3.5.5-1ubuntu3.7_amd64.deb ...
Unpacking libssl3t64:amd64 (3.5.5-1ubuntu3.7) over (3.5.5-1ubuntu3.4) ...
Setting up libssl3t64:amd64 (3.5.5-1ubuntu3.7) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libsystemd0_259.9-0ubuntu0.1_amd64.deb ...
Unpacking libsystemd0:amd64 (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Setting up libsystemd0:amd64 (259.9-0ubuntu0.1) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../libpam-systemd_259.9-0ubuntu0.1_amd64.deb ...
Unpacking libpam-systemd:amd64 (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../systemd-sysv_259.9-0ubuntu0.1_amd64.deb ...
Unpacking systemd-sysv (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../systemd-resolved_259.9-0ubuntu0.1_amd64.deb ...
Unpacking systemd-resolved (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../libsystemd-shared_259.9-0ubuntu0.1_amd64.deb ...
Unpacking libsystemd-shared:amd64 (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Setting up libsystemd-shared:amd64 (259.9-0ubuntu0.1) ...
(Reading database ... 35908 files and directories currently installed.)
Preparing to unpack .../systemd_259.9-0ubuntu0.1_amd64.deb ...
Unpacking systemd (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../systemd-cryptsetup_259.9-0ubuntu0.1_amd64.deb ...
Unpacking systemd-cryptsetup (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../udev_259.9-0ubuntu0.1_amd64.deb ...
Unpacking udev (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../libudev1_259.9-0ubuntu0.1_amd64.deb ...
Unpacking libudev1:amd64 (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Setting up libudev1:amd64 (259.9-0ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libaudit-common_1%3a4.1.2-1ubuntu0.1_all.deb ...
Unpacking libaudit-common (1:4.1.2-1ubuntu0.1) over (1:4.1.2-1build1) ...
Setting up libaudit-common (1:4.1.2-1ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libaudit1_1%3a4.1.2-1ubuntu0.1_amd64.deb ...
Unpacking libaudit1:amd64 (1:4.1.2-1ubuntu0.1) over (1:4.1.2-1build1) ...
Setting up libaudit1:amd64 (1:4.1.2-1ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libpam0g_1.7.0-5ubuntu3.2_amd64.deb ...
Unpacking libpam0g:amd64 (1.7.0-5ubuntu3.2) over (1.7.0-5ubuntu3.1) ...
Setting up libpam0g:amd64 (1.7.0-5ubuntu3.2) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libpam-runtime_1.7.0-5ubuntu3.2_all.deb ...
Unpacking libpam-runtime (1.7.0-5ubuntu3.2) over (1.7.0-5ubuntu3.1) ...
Setting up libpam-runtime (1.7.0-5ubuntu3.2) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libpam-modules-bin_1.7.0-5ubuntu3.2_amd64.deb ...
Unpacking libpam-modules-bin (1.7.0-5ubuntu3.2) over (1.7.0-5ubuntu3.1) ...
Setting up libpam-modules-bin (1.7.0-5ubuntu3.2) ...
pam_namespace.service is a disabled or a static unit not running, not starting it.
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libpam-modules_1.7.0-5ubuntu3.2_amd64.deb ...
Unpacking libpam-modules:amd64 (1.7.0-5ubuntu3.2) over (1.7.0-5ubuntu3.1) ...
Setting up libpam-modules:amd64 (1.7.0-5ubuntu3.2) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libapt-pkg7.0_3.2.1ubuntu0.1_amd64.deb ...
Unpacking libapt-pkg7.0:amd64 (3.2.1ubuntu0.1) over (3.2.0) ...
Setting up libapt-pkg7.0:amd64 (3.2.1ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libgcrypt20_1.12.0-2ubuntu1.1_amd64.deb ...
Unpacking libgcrypt20:amd64 (1.12.0-2ubuntu1.1) over (1.12.0-2ubuntu1) ...
Setting up libgcrypt20:amd64 (1.12.0-2ubuntu1.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../gpgv_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gpgv (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Setting up gpgv (2.4.8-4ubuntu3.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../apt_3.2.1ubuntu0.1_amd64.deb ...
Unpacking apt (3.2.1ubuntu0.1) over (3.2.0) ...
Setting up apt (3.2.1ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../gnu-coreutils_9.7-3ubuntu2.1_amd64.deb ...
Unpacking gnu-coreutils (9.7-3ubuntu2.1) over (9.7-3ubuntu2) ...
Setting up gnu-coreutils (9.7-3ubuntu2.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../00-login_1%3a4.16.0-2+really2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking login (1:4.16.0-2+really2.41.3-3ubuntu2.2) over (1:4.16.0-2+really2.41.3-3ubuntu2) ...
Preparing to unpack .../01-libexpat1_2.7.4-1ubuntu0.2_amd64.deb ...
Unpacking libexpat1:amd64 (2.7.4-1ubuntu0.2) over (2.7.4-1) ...
Preparing to unpack .../02-libpython3.14_3.14.4-1ubuntu0.2_amd64.deb ...
Unpacking libpython3.14:amd64 (3.14.4-1ubuntu0.2) over (3.14.4-1ubuntu0.1) ...
Preparing to unpack .../03-python3.14_3.14.4-1ubuntu0.2_amd64.deb ...
Unpacking python3.14 (3.14.4-1ubuntu0.2) over (3.14.4-1ubuntu0.1) ...
Preparing to unpack .../04-libpython3.14-stdlib_3.14.4-1ubuntu0.2_amd64.deb ...
Unpacking libpython3.14-stdlib:amd64 (3.14.4-1ubuntu0.2) over (3.14.4-1ubuntu0.1) ...
Preparing to unpack .../05-python3.14-minimal_3.14.4-1ubuntu0.2_amd64.deb ...
Unpacking python3.14-minimal (3.14.4-1ubuntu0.2) over (3.14.4-1ubuntu0.1) ...
Preparing to unpack .../06-libpython3.14-minimal_3.14.4-1ubuntu0.2_amd64.deb ...
Unpacking libpython3.14-minimal:amd64 (3.14.4-1ubuntu0.2) over (3.14.4-1ubuntu0.1) ...
Preparing to unpack .../07-tzdata_2026e-0ubuntu0.26.04.1_all.deb ...
Unpacking tzdata (2026e-0ubuntu0.26.04.1) over (2026c-0ubuntu0.26.04.1) ...
Preparing to unpack .../08-libsqlite3-0_3.46.1-9ubuntu0.3_amd64.deb ...
Unpacking libsqlite3-0:amd64 (3.46.1-9ubuntu0.3) over (3.46.1-9ubuntu0.2) ...
Preparing to unpack .../09-sudo_1.9.17p2-1ubuntu3.2_amd64.deb ...
Unpacking sudo (1.9.17p2-1ubuntu3.2) over (1.9.17p2-1ubuntu3) ...
Preparing to unpack .../10-libattr1_1%3a2.5.2-4ubuntu0.1_amd64.deb ...
Unpacking libattr1:amd64 (1:2.5.2-4ubuntu0.1) over (1:2.5.2-4) ...
Setting up libattr1:amd64 (1:2.5.2-4ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../libpcre2-8-0_10.46-1ubuntu0.1_amd64.deb ...
Unpacking libpcre2-8-0:amd64 (10.46-1ubuntu0.1) over (10.46-1build1) ...
Setting up libpcre2-8-0:amd64 (10.46-1ubuntu0.1) ...
(Reading database ... 35912 files and directories currently installed.)
Preparing to unpack .../rust-coreutils_0.10.0-1ubuntu2~26.04.1_amd64.deb ...
Unpacking rust-coreutils (0.10.0-1ubuntu2~26.04.1) over (0.8.0-0ubuntu3) ...
Setting up rust-coreutils (0.10.0-1ubuntu2~26.04.1) ...
(Reading database ... 35977 files and directories currently installed.)
Preparing to unpack .../00-bsdutils_1%3a2.41.3-3ubuntu2.2_amd64.deb ...
Unpacking bsdutils (1:2.41.3-3ubuntu2.2) over (1:2.41.3-3ubuntu2) ...
Preparing to unpack .../01-openssl_3.5.5-1ubuntu3.7_amd64.deb ...
Unpacking openssl (3.5.5-1ubuntu3.7) over (3.5.5-1ubuntu3.4) ...
Preparing to unpack .../02-ca-certificates_20260816ubuntu0.26.04.2_all.deb ...
Unpacking ca-certificates (20260816ubuntu0.26.04.2) over (20260601~26.04.1) ...
Preparing to unpack .../03-distro-info-data_2026.10.12-0ubuntu0.26.04.1_all.deb ...
Unpacking distro-info-data (2026.10.12-0ubuntu0.26.04.1) over (0.72-0ubuntu0.26.04.1) ...
Preparing to unpack .../04-libglib2.0-data_2.88.0-1ubuntu0.1_all.deb ...
Unpacking libglib2.0-data (2.88.0-1ubuntu0.1) over (2.88.0-1) ...
Preparing to unpack .../05-libglib2.0-bin_2.88.0-1ubuntu0.1_amd64.deb ...
Unpacking libglib2.0-bin (2.88.0-1ubuntu0.1) over (2.88.0-1) ...
Preparing to unpack .../06-gir1.2-girepository-3.0_2.88.0-1ubuntu0.1_amd64.deb ...
Unpacking gir1.2-girepository-3.0:amd64 (2.88.0-1ubuntu0.1) over (2.88.0-1) ...
Preparing to unpack .../07-libgirepository-2.0-0_2.88.0-1ubuntu0.1_amd64.deb ...
Unpacking libgirepository-2.0-0:amd64 (2.88.0-1ubuntu0.1) over (2.88.0-1) ...
Preparing to unpack .../08-gir1.2-glib-2.0_2.88.0-1ubuntu0.1_amd64.deb ...
Unpacking gir1.2-glib-2.0:amd64 (2.88.0-1ubuntu0.1) over (2.88.0-1) ...
Preparing to unpack .../09-libglib2.0-0t64_2.88.0-1ubuntu0.1_amd64.deb ...
Unpacking libglib2.0-0t64:amd64 (2.88.0-1ubuntu0.1) over (2.88.0-1) ...
Preparing to unpack .../10-python3-netplan_1.2-1ubuntu5.1_amd64.deb ...
Unpacking python3-netplan (1.2-1ubuntu5.1) over (1.2-1ubuntu5) ...
Preparing to unpack .../11-netplan-generator_1.2-1ubuntu5.1_amd64.deb ...
Adding 'diversion of /lib/systemd/system-generators/netplan to /lib/systemd/system-generators/netplan.usr-is-merged by netplan-generator'
Unpacking netplan-generator (1.2-1ubuntu5.1) over (1.2-1ubuntu5) ...
Preparing to unpack .../12-netplan.io_1.2-1ubuntu5.1_amd64.deb ...
Unpacking netplan.io (1.2-1ubuntu5.1) over (1.2-1ubuntu5) ...
Preparing to unpack .../13-libnetplan1_1.2-1ubuntu5.1_amd64.deb ...
Unpacking libnetplan1:amd64 (1.2-1ubuntu5.1) over (1.2-1ubuntu5) ...
Preparing to unpack .../14-libnss-systemd_259.9-0ubuntu0.1_amd64.deb ...
Unpacking libnss-systemd:amd64 (259.9-0ubuntu0.1) over (259.5-0ubuntu3.4) ...
Preparing to unpack .../15-libxml2-16_2.15.2+dfsg-0.1ubuntu0.3_amd64.deb ...
Unpacking libxml2-16:amd64 (2.15.2+dfsg-0.1ubuntu0.3) over (2.15.2+dfsg-0.1ubuntu0.1) ...
Preparing to unpack .../16-locales_2.43-2ubuntu2.7_all.deb ...
Unpacking locales (2.43-2ubuntu2.7) over (2.43-2ubuntu2.3) ...
Preparing to unpack .../17-rsyslog_8.2512.0-1ubuntu4.2_amd64.deb ...
Unpacking rsyslog (8.2512.0-1ubuntu4.2) over (8.2512.0-1ubuntu4.1) ...
Preparing to unpack .../18-sudo-rs_0.2.13-0ubuntu1.2_amd64.deb ...
Unpacking sudo-rs (0.2.13-0ubuntu1.2) over (0.2.13-0ubuntu1) ...
Preparing to unpack .../19-ubuntu-pro-client-l10n_38ubuntu0~26.04_amd64.deb ...
Unpacking ubuntu-pro-client-l10n (38ubuntu0~26.04) over (37.2ubuntu0.1) ...
Preparing to unpack .../20-ubuntu-pro-client_38ubuntu0~26.04_amd64.deb ...
Unpacking ubuntu-pro-client (38ubuntu0~26.04) over (37.2ubuntu0.1) ...
Preparing to unpack .../21-vim_2%3a9.1.2141-1ubuntu4.10_amd64.deb ...
Unpacking vim (2:9.1.2141-1ubuntu4.10) over (2:9.1.2141-1ubuntu4.8) ...
Preparing to unpack .../22-vim-tiny_2%3a9.1.2141-1ubuntu4.10_amd64.deb ...
Unpacking vim-tiny (2:9.1.2141-1ubuntu4.10) over (2:9.1.2141-1ubuntu4.8) ...
Preparing to unpack .../23-vim-runtime_2%3a9.1.2141-1ubuntu4.10_all.deb ...
Unpacking vim-runtime (2:9.1.2141-1ubuntu4.10) over (2:9.1.2141-1ubuntu4.8) ...
Preparing to unpack .../24-vim-common_2%3a9.1.2141-1ubuntu4.10_all.deb ...
Unpacking vim-common (2:9.1.2141-1ubuntu4.10) over (2:9.1.2141-1ubuntu4.8) ...
Preparing to unpack .../25-ubuntu-minimal_1.570.4_amd64.deb ...
Unpacking ubuntu-minimal (1.570.4) over (1.570.3) ...
Preparing to unpack .../26-xxd_2%3a9.1.2141-1ubuntu4.10_amd64.deb ...
Unpacking xxd (2:9.1.2141-1ubuntu4.10) over (2:9.1.2141-1ubuntu4.8) ...
Preparing to unpack .../27-libpng16-16t64_1.6.57-1ubuntu0.1_amd64.deb ...
Unpacking libpng16-16t64:amd64 (1.6.57-1ubuntu0.1) over (1.6.57-1) ...
Preparing to unpack .../28-libx11-6_2%3a1.8.13-1ubuntu0.1_amd64.deb ...
Unpacking libx11-6:amd64 (2:1.8.13-1ubuntu0.1) over (2:1.8.13-1) ...
Preparing to unpack .../29-libx11-xcb1_2%3a1.8.13-1ubuntu0.1_amd64.deb ...
Unpacking libx11-xcb1:amd64 (2:1.8.13-1ubuntu0.1) over (2:1.8.13-1) ...
Preparing to unpack .../30-libx11-data_2%3a1.8.13-1ubuntu0.1_all.deb ...
Unpacking libx11-data (2:1.8.13-1ubuntu0.1) over (2:1.8.13-1) ...
Preparing to unpack .../31-libbrotli1_1.2.0-3ubuntu0.1_amd64.deb ...
Unpacking libbrotli1:amd64 (1.2.0-3ubuntu0.1) over (1.2.0-3build1) ...
Preparing to unpack .../32-libssh2-1t64_1.11.1-1ubuntu0.26.04.4_amd64.deb ...
Unpacking libssh2-1t64:amd64 (1.11.1-1ubuntu0.26.04.4) over (1.11.1-1ubuntu0.26.04.3) ...
Preparing to unpack .../33-libcurl3t64-gnutls_8.18.0-1ubuntu2.8_amd64.deb ...
Unpacking libcurl3t64-gnutls:amd64 (8.18.0-1ubuntu2.8) over (8.18.0-1ubuntu2.4) ...
Preparing to unpack .../34-git-man_1%3a2.53.0-1ubuntu1.1_all.deb ...
Unpacking git-man (1:2.53.0-1ubuntu1.1) over (1:2.53.0-1ubuntu1) ...
Preparing to unpack .../35-git_1%3a2.53.0-1ubuntu1.1_amd64.deb ...
Unpacking git (1:2.53.0-1ubuntu1.1) over (1:2.53.0-1ubuntu1) ...
Preparing to unpack .../36-openssh-client_1%3a10.2p1-2ubuntu3.8_amd64.deb ...
Unpacking openssh-client (1:10.2p1-2ubuntu3.8) over (1:10.2p1-2ubuntu3.5) ...
Preparing to unpack .../37-ubuntu-release-upgrader-core_1%3a26.04.27_all.deb ...
Unpacking ubuntu-release-upgrader-core (1:26.04.27) over (1:26.04.23) ...
Preparing to unpack .../38-python3-distupgrade_1%3a26.04.27_all.deb ...
Unpacking python3-distupgrade (1:26.04.27) over (1:26.04.23) ...
Preparing to unpack .../39-python3.14-gdbm_3.14.4-1ubuntu0.2_amd64.deb ...
Unpacking python3.14-gdbm (3.14.4-1ubuntu0.2) over (3.14.4-1ubuntu0.1) ...
Preparing to unpack .../40-xz-utils_5.8.3-1ubuntu0.1_amd64.deb ...
Unpacking xz-utils (5.8.3-1ubuntu0.1) over (5.8.3-1) ...
Preparing to unpack .../41-bubblewrap_0.11.1-1ubuntu0.3_amd64.deb ...
Unpacking bubblewrap (0.11.1-1ubuntu0.3) over (0.11.1-1ubuntu0.1) ...
Preparing to unpack .../42-cloud-init-base_26.2-0ubuntu1~26.04.1_all.deb ...
Unpacking cloud-init-base (26.2-0ubuntu1~26.04.1) over (26.1-0ubuntu3~26.04.1) ...
Preparing to unpack .../43-cloud-init_26.2-0ubuntu1~26.04.1_all.deb ...
Unpacking cloud-init (26.2-0ubuntu1~26.04.1) over (26.1-0ubuntu3~26.04.1) ...
Preparing to unpack .../44-python3-urllib3_2.6.3-1ubuntu1.2_all.deb ...
Unpacking python3-urllib3 (2.6.3-1ubuntu1.2) over (2.6.3-1ubuntu1.1) ...
Preparing to unpack .../45-python3-requests_2.32.5+dfsg-1ubuntu1.1_all.deb ...
Unpacking python3-requests (2.32.5+dfsg-1ubuntu1.1) over (2.32.5+dfsg-1ubuntu1) ...
Preparing to unpack .../46-curl_8.18.0-1ubuntu2.8_amd64.deb ...
Unpacking curl (8.18.0-1ubuntu2.8) over (8.18.0-1ubuntu2.4) ...
Preparing to unpack .../47-libcurl4t64_8.18.0-1ubuntu2.8_amd64.deb ...
Unpacking libcurl4t64:amd64 (8.18.0-1ubuntu2.8) over (8.18.0-1ubuntu2.4) ...
Preparing to unpack .../48-gnupg-utils_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gnupg-utils (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../49-gpg-wks-client_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gpg-wks-client (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../50-dirmngr_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking dirmngr (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../51-gpg-agent_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gpg-agent (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../52-gpg_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gpg (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../53-gpgconf_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gpgconf (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../54-gnupg_2.4.8-4ubuntu3.1_all.deb ...
Unpacking gnupg (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../55-gpgsm_2.4.8-4ubuntu3.1_amd64.deb ...
Unpacking gpgsm (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../56-libaom3_3.13.1-2ubuntu0.1_amd64.deb ...
Unpacking libaom3:amd64 (3.13.1-2ubuntu0.1) over (3.13.1-2) ...
Preparing to unpack .../57-libheif-plugin-aomenc_1.21.2-3ubuntu0.7_amd64.deb ...
Unpacking libheif-plugin-aomenc:amd64 (1.21.2-3ubuntu0.7) over (1.21.2-3ubuntu0.4) ...
Preparing to unpack .../58-libheif1_1.21.2-3ubuntu0.7_amd64.deb ...
Unpacking libheif1:amd64 (1.21.2-3ubuntu0.7) over (1.21.2-3ubuntu0.4) ...
Preparing to unpack .../59-libheif-plugin-aomdec_1.21.2-3ubuntu0.7_amd64.deb ...
Unpacking libheif-plugin-aomdec:amd64 (1.21.2-3ubuntu0.7) over (1.21.2-3ubuntu0.4) ...
Preparing to unpack .../60-librsvg2-common_2.61.3+dfsg-3ubuntu0.1_amd64.deb ...
Unpacking librsvg2-common:amd64 (2.61.3+dfsg-3ubuntu0.1) over (2.61.3+dfsg-3) ...
Preparing to unpack .../61-librsvg2-2_2.61.3+dfsg-3ubuntu0.1_amd64.deb ...
Unpacking librsvg2-2:amd64 (2.61.3+dfsg-3ubuntu0.1) over (2.61.3+dfsg-3) ...
Preparing to unpack .../62-glycin-loaders_2.1.5+ds-0ubuntu0.2_amd64.deb ...
Unpacking glycin-loaders (2.1.5+ds-0ubuntu0.2) over (2.1.1+ds-0ubuntu1) ...
Preparing to unpack .../63-libglycin-2-0_2.1.5+ds-0ubuntu0.2_amd64.deb ...
Unpacking libglycin-2-0:amd64 (2.1.5+ds-0ubuntu0.2) over (2.1.1+ds-0ubuntu1) ...
Preparing to unpack .../64-glycin-thumbnailers_2.1.5+ds-0ubuntu0.2_amd64.deb ...
Unpacking glycin-thumbnailers (2.1.5+ds-0ubuntu0.2) over (2.1.1+ds-0ubuntu1) ...
Preparing to unpack .../65-gnupg-l10n_2.4.8-4ubuntu3.1_all.deb ...
Unpacking gnupg-l10n (2.4.8-4ubuntu3.1) over (2.4.8-4ubuntu3) ...
Preparing to unpack .../66-gtk-update-icon-cache_4.22.4+ds-0ubuntu0.2_amd64.deb ...
Unpacking gtk-update-icon-cache (4.22.4+ds-0ubuntu0.2) over (4.22.4+ds-0ubuntu0.1) ...
Preparing to unpack .../67-libevent-core-2.1-7t64_2.1.12-stable-10ubuntu0.2_amd64.deb ...
Unpacking libevent-core-2.1-7t64:amd64 (2.1.12-stable-10ubuntu0.2) over (2.1.12-stable-10build2) ...
Preparing to unpack .../68-libfreetype6_2.14.2+dfsg-1ubuntu0.2_amd64.deb ...
Unpacking libfreetype6:amd64 (2.14.2+dfsg-1ubuntu0.2) over (2.14.2+dfsg-1ubuntu0.1) ...
Preparing to unpack .../69-polkitd_127-2ubuntu1.1_amd64.deb ...
Unpacking polkitd (127-2ubuntu1.1) over (127-2ubuntu1) ...
Preparing to unpack .../70-libpolkit-agent-1-0_127-2ubuntu1.1_amd64.deb ...
Unpacking libpolkit-agent-1-0:amd64 (127-2ubuntu1.1) over (127-2ubuntu1) ...
Preparing to unpack .../71-libpolkit-gobject-1-0_127-2ubuntu1.1_amd64.deb ...
Unpacking libpolkit-gobject-1-0:amd64 (127-2ubuntu1.1) over (127-2ubuntu1) ...
Preparing to unpack .../72-libxtst6_2%3a1.2.5-1ubuntu0.1_amd64.deb ...
Unpacking libxtst6:amd64 (2:1.2.5-1ubuntu0.1) over (2:1.2.5-1build1) ...
Preparing to unpack .../73-python3-cryptography_46.0.5-1ubuntu2.2_amd64.deb ...
Unpacking python3-cryptography (46.0.5-1ubuntu2.2) over (46.0.5-1ubuntu2) ...
Preparing to unpack .../74-python3-jwt_2.10.1-4ubuntu1.3_all.deb ...
Unpacking python3-jwt (2.10.1-4ubuntu1.3) over (2.10.1-4ubuntu1) ...
Preparing to unpack .../75-python3-pyasn1_0.6.3-1ubuntu0.2_all.deb ...
Unpacking python3-pyasn1 (0.6.3-1ubuntu0.2) over (0.6.3-1) ...
Preparing to unpack .../76-python3-twisted_25.5.0-5ubuntu0.2_all.deb ...
Unpacking python3-twisted (25.5.0-5ubuntu0.2) over (25.5.0-5ubuntu0.1) ...
Preparing to unpack .../77-snapd_2.78+ubuntu26.04_amd64.deb ...
Unpacking snapd (2.78+ubuntu26.04) over (2.76.3+ubuntu26.04) ...
Preparing to unpack .../78-tmux_3.6a-2ubuntu0.2_amd64.deb ...
Unpacking tmux (3.6a-2ubuntu0.2) over (3.6a-2ubuntu0.1) ...
Preparing to unpack .../79-ubuntu-insights_0.9.3ubuntu0.1_amd64.deb ...
Unpacking ubuntu-insights (0.9.3ubuntu0.1) over (0.9.3ubuntu) ...
Preparing to unpack .../80-ubuntu-wsl_1.570.4_amd64.deb ...
Unpacking ubuntu-wsl (1.570.4) over (1.570.3) ...
Preparing to unpack .../81-wsl-pro-service_0.1.19ubuntu2.1_amd64.deb ...
Unpacking wsl-pro-service (0.1.19ubuntu2.1) over (0.1.19ubuntu2) ...
Setting up libexpat1:amd64 (2.7.4-1ubuntu0.2) ...
Setting up bubblewrap (0.11.1-1ubuntu0.3) ...
Setting up motd-news-config (14ubuntu6.3) ...
Setting up libaom3:amd64 (3.13.1-2ubuntu0.1) ...
Setting up bsdextrautils (2.41.3-3ubuntu2.2) ...
Setting up bsdutils (1:2.41.3-3ubuntu2.2) ...
Setting up python3-jwt (2.10.1-4ubuntu1.3) ...
Setting up distro-info-data (2026.10.12-0ubuntu0.26.04.1) ...
Setting up libxml2-16:amd64 (2.15.2+dfsg-0.1ubuntu0.3) ...
Setting up openssh-client (1:10.2p1-2ubuntu3.8) ...
Setting up libbrotli1:amd64 (1.2.0-3ubuntu0.1) ...
Setting up libpython3.14-minimal:amd64 (3.14.4-1ubuntu0.2) ...
Setting up libsqlite3-0:amd64 (3.46.1-9ubuntu0.3) ...
Setting up rsyslog (8.2512.0-1ubuntu4.2) ...
warn: The user `syslog' is already a member of `adm'.
Setting up libnss-systemd:amd64 (259.9-0ubuntu0.1) ...
Setting up ubuntu-insights (0.9.3ubuntu0.1) ...
Setting up python3-distupgrade (1:26.04.27) ...
Setting up locales (2.43-2ubuntu2.7) ...
Generating locales (this might take a while)...
Generation complete.
Setting up xxd (2:9.1.2141-1ubuntu4.10) ...
Setting up tzdata (2026e-0ubuntu0.26.04.1) ...

Current default time zone: 'America/Bogota'
Local time is now:      Tue Nov 17 10:43:23 -05 2026.
Universal Time is now:  Tue Nov 17 15:43:23 UTC 2026.
Run 'dpkg-reconfigure tzdata' if you wish to change it.

Setting up eject (2.41.3-3ubuntu2.2) ...
Setting up libglib2.0-0t64:amd64 (2.88.0-1ubuntu0.1) ...
Setting up libglib2.0-data (2.88.0-1ubuntu0.1) ...
Setting up vim-common (2:9.1.2141-1ubuntu4.10) ...
Setting up python3.14-gdbm (3.14.4-1ubuntu0.2) ...
Setting up systemd-cryptsetup (259.9-0ubuntu0.1) ...
Setting up libx11-data (2:1.8.13-1ubuntu0.1) ...
Setting up gnupg-l10n (2.4.8-4ubuntu3.1) ...
Setting up python3-cryptography (46.0.5-1ubuntu2.2) ...
Setting up xz-utils (5.8.3-1ubuntu0.1) ...
Setting up libpng16-16t64:amd64 (1.6.57-1ubuntu0.1) ...
Setting up sudo (1.9.17p2-1ubuntu3.2) ...
update-alternatives: warning: forcing reinstallation of alternative /usr/lib/cargo/bin/sudo because link group sudo is broken
Setting up gir1.2-glib-2.0:amd64 (2.88.0-1ubuntu0.1) ...
Setting up python3-urllib3 (2.6.3-1ubuntu1.2) ...
Setting up libfdisk1:amd64 (2.41.3-3ubuntu2.2) ...
Setting up mount (2.41.3-3ubuntu2.2) ...
Setting up perl-modules-5.40 (5.40.1-7ubuntu0.4) ...
Setting up gpgconf (2.4.8-4ubuntu3.1) ...
Setting up python3-pyasn1 (0.6.3-1ubuntu0.2) ...
Setting up git-man (1:2.53.0-1ubuntu1.1) ...
Setting up libx11-6:amd64 (2:1.8.13-1ubuntu0.1) ...
Setting up libevent-core-2.1-7t64:amd64 (2.1.12-stable-10ubuntu0.2) ...
Setting up libssh2-1t64:amd64 (1.11.1-1ubuntu0.26.04.4) ...
Setting up vim-runtime (2:9.1.2141-1ubuntu4.10) ...
Setting up openssl (3.5.5-1ubuntu3.7) ...
Setting up tmux (3.6a-2ubuntu0.2) ...
Setting up ubuntu-pro-client (38ubuntu0~26.04) ...
Installing new version of config file /etc/apparmor.d/ubuntu_pro_esm_cache ...
Setting up python3.14-minimal (3.14.4-1ubuntu0.2) ...
Setting up gpg (2.4.8-4ubuntu3.1) ...
Setting up libpolkit-gobject-1-0:amd64 (127-2ubuntu1.1) ...
Setting up sudo-rs (0.2.13-0ubuntu1.2) ...
Setting up gnupg-utils (2.4.8-4ubuntu3.1) ...
Setting up login (1:4.16.0-2+really2.41.3-3ubuntu2.2) ...
Setting up ubuntu-pro-client-l10n (38ubuntu0~26.04) ...
Setting up wsl-pro-service (0.1.19ubuntu2.1) ...
Setting up gtk-update-icon-cache (4.22.4+ds-0ubuntu0.2) ...
Setting up libx11-xcb1:amd64 (2:1.8.13-1ubuntu0.1) ...
Setting up gpg-agent (2.4.8-4ubuntu3.1) ...
Setting up libcurl4t64:amd64 (8.18.0-1ubuntu2.8) ...
Setting up libgirepository-2.0-0:amd64 (2.88.0-1ubuntu0.1) ...
Setting up libpython3.14-stdlib:amd64 (3.14.4-1ubuntu0.2) ...
Setting up libxtst6:amd64 (2:1.2.5-1ubuntu0.1) ...
Setting up gpgsm (2.4.8-4ubuntu3.1) ...
Setting up libcurl3t64-gnutls:amd64 (8.18.0-1ubuntu2.8) ...
Setting up libglib2.0-bin (2.88.0-1ubuntu0.1) ...
Setting up systemd (259.9-0ubuntu0.1) ...
Setting up vim-tiny (2:9.1.2141-1ubuntu4.10) ...
Setting up libnetplan1:amd64 (1.2-1ubuntu5.1) ...
Setting up gir1.2-girepository-3.0:amd64 (2.88.0-1ubuntu0.1) ...
Setting up fdisk (2.41.3-3ubuntu2.2) ...
Setting up librsvg2-2:amd64 (2.61.3+dfsg-3ubuntu0.1) ...
Setting up libperl5.40:amd64 (5.40.1-7ubuntu0.4) ...
Setting up dirmngr (2.4.8-4ubuntu3.1) ...
Setting up ca-certificates (20260816ubuntu0.26.04.2) ...
Updating certificates in /etc/ssl/certs...
rehash: warning: skipping ca-certificates.crt, it does not contain exactly one certificate or CRL
4 added, 5 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
Setting up perl (5.40.1-7ubuntu0.4) ...
Setting up libfreetype6:amd64 (2.14.2+dfsg-1ubuntu0.2) ...
Setting up python3-twisted (25.5.0-5ubuntu0.2) ...
/usr/lib/python3/dist-packages/twisted/internet/test/test_posixbase.py:55: SyntaxWarning: 'return' in a 'finally' block
  return
Setting up python3-requests (2.32.5+dfsg-1ubuntu1.1) ...
Setting up udev (259.9-0ubuntu0.1) ...
Setting up ubuntu-release-upgrader-core (1:26.04.27) ...
Setting up git (1:2.53.0-1ubuntu1.1) ...
Setting up librsvg2-common:amd64 (2.61.3+dfsg-3ubuntu0.1) ...
Setting up gnupg (2.4.8-4ubuntu3.1) ...
Setting up python3-netplan (1.2-1ubuntu5.1) ...
Setting up libpython3.14:amd64 (3.14.4-1ubuntu0.2) ...
Setting up libpolkit-agent-1-0:amd64 (127-2ubuntu1.1) ...
Setting up curl (8.18.0-1ubuntu2.8) ...
Setting up python3.14 (3.14.4-1ubuntu0.2) ...
Setting up netplan-generator (1.2-1ubuntu5.1) ...
Removing 'diversion of /lib/systemd/system-generators/netplan to /lib/systemd/system-generators/netplan.usr-is-merged by netplan-generator'
Setting up systemd-resolved (259.9-0ubuntu0.1) ...
Installing new version of config file /etc/systemd/resolved.conf ...
Setting up snapd (2.78+ubuntu26.04) ...
Installing new version of config file /etc/apparmor.d/usr.lib.snapd.snap-confine.real ...
snapd.failure.service is a disabled or a static unit not running, not starting it.
snapd.gpio-chardev-setup.target is a disabled or a static unit not running, not starting it.
snapd.snap-repair.service is a disabled or a static unit not running, not starting it.
Setting up systemd-sysv (259.9-0ubuntu0.1) ...
Setting up vim (2:9.1.2141-1ubuntu4.10) ...
Setting up gpg-wks-client (2.4.8-4ubuntu3.1) ...
Setting up netplan.io (1.2-1ubuntu5.1) ...
Setting up libpam-systemd:amd64 (259.9-0ubuntu0.1) ...
Setting up polkitd (127-2ubuntu1.1) ...
Setting up ubuntu-minimal (1.570.4) ...
Setting up ubuntu-wsl (1.570.4) ...
Setting up cloud-init-base (26.2-0ubuntu1~26.04.1) ...
Installing new version of config file /etc/profile.d/Z99-cloud-locale-test.sh ...
Installing new version of config file /etc/profile.d/Z99-cloudinit-warnings.sh ...
Encountered debconf setting for cloud-init-base/datasources.
Setting up cloud-init (26.2-0ubuntu1~26.04.1) ...
Setting up libheif-plugin-aomdec:amd64 (1.21.2-3ubuntu0.7) ...
Setting up libheif1:amd64 (1.21.2-3ubuntu0.7) ...
Setting up glycin-loaders (2.1.5+ds-0ubuntu0.2) ...
Setting up libglycin-2-0:amd64 (2.1.5+ds-0ubuntu0.2) ...
Setting up libheif-plugin-aomenc:amd64 (1.21.2-3ubuntu0.7) ...
Setting up glycin-thumbnailers (2.1.5+ds-0ubuntu0.2) ...
Processing triggers for dbus (1.16.2-2ubuntu4) ...
Processing triggers for shared-mime-info (2.4-5build3) ...
Processing triggers for procps (2:4.0.4-9ubuntu1) ...
Processing triggers for libgdk-pixbuf-2.0-0:amd64 (2.44.5+dfsg-4ubuntu1) ...
Processing triggers for sgml-base (1.31+nmu1build1) ...
Processing triggers for debianutils (5.23.2build1) ...
Processing triggers for install-info (7.2-5ubuntu2) ...
Processing triggers for hicolor-icon-theme (0.18-2build1) ...
Processing triggers for libc-bin (2.43-2ubuntu2.7) ...
Processing triggers for man-db (2.13.1-1build1) ...
Processing triggers for libselinux1:amd64 (3.9-4build1) ...
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ mkdir pracatice
ossau@LAPTOP-2HK683AM:~$ mkdir practice
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ pwd
/home/ossau/practice
ossau@LAPTOP-2HK683AM:~/practice$ touch notes.txt
ossau@LAPTOP-2HK683AM:~/practice$ ls -la
total 8
drwxr-xr-x 2 ossau ossau 4096 Nov 17 11:12 .
drwxr-x--- 6 ossau ossau 4096 Nov 17 11:11 ..
-rw-r--r-- 1 ossau ossau    0 Nov 17 11:12 notes.txt
ossau@LAPTOP-2HK683AM:~/practice$ echo "I'm learning Linux" > notes.txt
ossau@LAPTOP-2HK683AM:~/practice$ cat notes.txt
I'm learning Linux
ossau@LAPTOP-2HK683AM:~/practice$ cd
ossau@LAPTOP-2HK683AM:~/practice$ echo "I'm learning Linux" > notes.txt notes.txt q
ossau@LAPTOP-2HK683AM:~/practice$ ^C
ossau@LAPTOP-2HK683AM:~/practice$ ^C
ossau@LAPTOP-2HK683AM:~/practice$ cd ~
ossau@LAPTOP-2HK683AM:~$ sudo apt instqall git
[sudo: authenticate] Password:
Error: Invalid operation instqall
ossau@LAPTOP-2HK683AM:~$ Ozza6505
Ozza6505: command not found
ossau@LAPTOP-2HK683AM:~$ sudo apt install git
git is already the newest version (1:2.53.0-1ubuntu1.1).
git set to manually installed.
Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 4
ossau@LAPTOP-2HK683AM:~$ git --version
git version 2.53.0
ossau@LAPTOP-2HK683AM:~$ sudo apt install
[sudo: authenticate] Password:
Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 4
ossau@LAPTOP-2HK683AM:~$ nano $HOME/ .bashrc
ossau@LAPTOP-2HK683AM:~$ /etc/profile
-bash: /etc/profile: Permission denied
ossau@LAPTOP-2HK683AM:~$ ~/ .bash_profile
-bash: /home/ossau/: Is a directory
ossau@LAPTOP-2HK683AM:~$ HOME/
-bash: HOME/: No such file or directory
ossau@LAPTOP-2HK683AM:~$ RANDOM
RANDOM: command not found
ossau@LAPTOP-2HK683AM:~$ cd
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ /home
-bash: /home: Is a directory
ossau@LAPTOP-2HK683AM:~$ bash
ossau@LAPTOP-2HK683AM:~$ cd/
bash: cd/: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd /
ossau@LAPTOP-2HK683AM:/$ cd ~
ossau@LAPTOP-2HK683AM:~$ /bin/bash/
bash: /bin/bash/: Not a directory
ossau@LAPTOP-2HK683AM:~$ BASH
BASH: command not found
ossau@LAPTOP-2HK683AM:~$ SHELL
SHELL: command not found
ossau@LAPTOP-2HK683AM:~$ $shell
ossau@LAPTOP-2HK683AM:~$ $mail
ossau@LAPTOP-2HK683AM:~$ echo $value

ossau@LAPTOP-2HK683AM:~$ declare
BASH=/usr/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:globasciiranges:globskipdots:histappend:interactive_comments:patsub_replacement:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=([0]="0")
BASH_ARGV=()
BASH_CMDS=()
BASH_COMPLETION_VERSINFO=([0]="2" [1]="16" [2]="0")
BASH_LINENO=()
BASH_LOADABLES_PATH=/usr/local/lib/bash:/usr/lib/bash:/opt/local/lib/bash:/usr/pkg/lib/bash:/opt/pkg/lib/bash:.
BASH_SOURCE=()
BASH_VERSINFO=([0]="5" [1]="3" [2]="9" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
BASH_VERSION='5.3.9(1)-release'
COLUMNS=133
COMP_FILEDIR_FALLBACK=BASH_COMPLETION_FILEDIR_FALLBACK
COMP_KNOWN_HOSTS_WITH_AVAHI=BASH_COMPLETION_KNOWN_HOSTS_WITH_AVAHI
COMP_KNOWN_HOSTS_WITH_HOSTFILE=BASH_COMPLETION_KNOWN_HOSTS_WITH_HOSTFILE
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
DIRSTACK=()
DISPLAY=:0
EUID=1000
GROUPS=()
HISTCONTROL=ignoreboth
HISTFILE=/home/ossau/.bash_history
HISTFILESIZE=2000
HISTSIZE=1000
HOME=/home/ossau
HOSTNAME=LAPTOP-2HK683AM
HOSTTYPE=x86_64
IFS=$' \t\n'
LANG=C.UTF-8
LESSCLOSE='/usr/bin/lesspipe %s %s'
LESSOPEN='| /usr/bin/lesspipe %s'
LINES=33
LOGNAME=ossau
LS_COLORS='rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:'
MACHTYPE=x86_64-pc-linux-gnu
MAILCHECK=60
NAME=LAPTOP-2HK683AM
OLDPWD=/
OPTERR=1
OPTIND=1
OSTYPE=linux-gnu
PATH='/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Program Files/WindowsApps/MicrosoftCorporationII.WindowsSubsystemForLinux_3.0.5.0_x64__8wekyb3d8bbwe:/mnt/c/Program Files/Common Files/Oracle/Java/javapath:/mnt/c/WINDOWS/system32:/mnt/c/WINDOWS:/mnt/c/WINDOWS/System32/Wbem:/mnt/c/WINDOWS/System32/WindowsPowerShell/v1.0/:/mnt/c/WINDOWS/System32/OpenSSH/:/mnt/c/Program Files/Git/cmd:/mnt/c/Program Files/WSL/:/mnt/c/Users/Ossau/AppData/Local/Microsoft/WindowsApps:/snap/bin'
PIPESTATUS=([0]="0")
PPID=605
PS1='\[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
PS2='> '
PS4='+ '
PULSE_SERVER=unix:/mnt/wslg/PulseServer
PWD=/home/ossau
SHELL=/bin/bash
SHELLOPTS=braceexpand:emacs:hashall:histexpand:history:interactive-comments:monitor
SHLVL=2
TERM=xterm-256color
UID=1000
USER=ossau
WAYLAND_DISPLAY=wayland-0
WSL2_GUI_APPS_ENABLED=1
WSLENV=
WSL_DISTRO_NAME=Ubuntu
WSL_INTEROP=/run/WSL/604_interop
XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
XDG_RUNTIME_DIR=/run/user/1000
_=echo
__git_CRLF=$'\r\n'
__git_ESC=$'\E'
__git_LF=$'\n'
__git_SOH=$'\001'
__git_STX=$'\002'
__git_printf_supports_v=yes
_backup_glob='@(#*#|*@(~|.@(bak|orig|rej|swp|@(dpkg|ucf)-*|rpm@(orig|new|save))))'
_comp__base_directory=/usr/share/bash-completion
_comp_backup_glob='@(#*#|*@(~|.@(bak|orig|rej|swp|@(dpkg|ucf)-*|rpm@(orig|new|save))))'
_comp_dequote__regex_safe_word='^([^\'\''"$`;&|<>()!]|\\.|'\''[^'\'']*'\''|\$?"([^\"$`!]|\$([_a-zA-Z][_a-zA-Z0-9]*|[-*@#?$!0-9_])|\$\{[!#]?([_a-zA-Z][_a-zA-Z0-9]*(\[([0-9]+|[*@])\])?|[-*@#?$!0-9_])\}|\\.)*"|\$'\''([^\'\'']|\\.)*'\''|\$([_a-zA-Z][_a-zA-Z0-9]*|[-*@#?$!0-9_])|\$\{[!#]?([_a-zA-Z][_a-zA-Z0-9]*(\[([0-9]+|[*@])\])?|[-*@#?$!0-9_])\})*$'
_comp_xspecs=([tex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [freeamp]="!*.@(mp3|og[ag]|pls|m3u)" [gqmpeg]="!*.@(mp3|og[ag]|pls|m3u)" [texi2html]="!*.texi*" [hbpp]="!*.@([Pp][Rr][Gg]|[Cc][Ll][Pp])" [lowriter]="!*.@(sxw|stw|sxg|sgl|doc?([mx])|dot?([mx])|rtf|txt|htm|html|?(f)odt|ott|odm|pdf)" [rpm2cpio]="!*.[rs]pm" [localc]="!*.@(sxc|stc|xls?([bmx])|xlw|xlt?([mx])|[ct]sv|?(f)ods|ots)" [hbrun]="!*.[Hh][Rr][Bb]" [vi]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [latex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [view]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [madplay]="!*.mp3" [compress]="*.Z" [pdfjadetex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [pbunzip2]="!*.?(t)bz?(2)" [lrunzip]="!*.lrz" [gunzip]="!*.@(Z|[gGd]z|t[ag]z)" [oowriter]="!*.@(sxw|stw|sxg|sgl|doc?([mx])|dot?([mx])|rtf|txt|htm|html|?(f)odt|ott|odm|pdf)" [epiphany]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [acroread]="!*.[pf]df" [znew]="*.Z" [kwrite]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [xemacs]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [gview]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [lzfgrep]="!*.@(tlz|lzma)" [lzless]="!*.@(tlz|lzma)" [cdiff]="!*.@(dif?(f)|?(d)patch)?(.@([gx]z|bz2|lzma))" [zipinfo]="!*.@(zip|[aegjkswx]ar|exe|pk3|wsz|zargo|xpi|s[tx][cdiw]|sx[gm]|o[dt][tspgfc]|od[bm]|oxt|?(o)xps|epub|cbz|apk|aab|ipa|do[ct][xm]|p[op]t[mx]|xl[st][xm]|pyz|vsix|whl|[Ff][Cc][Ss]td)" [pdflatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [portecle]="!@(*.@(ks|jks|jceks|p12|pfx|bks|ubr|gkr|cer|crt|cert|p7b|pkipath|pem|p10|csr|crl)|cacerts)" [modplugplay]="!*.@(669|abc|am[fs]|d[bs]m|dmf|far|it|mdl|m[eo]d|mid?(i)|mt[2m]|oct|okt?(a)|p[st]m|s[3t]m|ult|umx|wav|xm)" [lokalize]="!*.po" [lbzcat]="!*.?(t)bz?(2)" [qiv]="!*.@(gif|jp?(e)g|tif?(f)|png|p[bgp]m|bmp|x[bp]m|rle|rgb|pcx|fits|pm|svg)" [totem]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|opus|OPUS|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM|iso|ISO)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [ps2pdfwr]="!*.@(?(e)ps|pdf)" [dvitype]="!*.dvi" [unpigz]="!*.@(Z|[gGdz]z|t[ag]z)" [mozilla]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [pdfunite]="!*.pdf" [gpdf]="!*.[pf]df" [texi2dvi]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [bunzip2]="!*.?(t)bz?(2)" [zathura]="!*.@(cb[rz7t]|djv?(u)|?(e)ps|pdf)" [kaffeine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|opus|OPUS|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM|iso|ISO)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [mpg123]="!*.mp3" [lzegrep]="!*.@(tlz|lzma)" [xv]="!*.@(gif|jp?(e)g?(2)|j2[ck]|jp[2f]|tif?(f)|png|p[bgpn]m|webp|bmp|x[bp]m|rle|rgb|pcx|fits|pm|?(e)ps)" [xdvi]="!*.@(dvi|DVI)?(.@(gz|Z|bz2))" [xfig]="!*.fig" [xpdf]="!*.@(pdf|fdf)?(.@(gz|Z|xz|lzma|bz2))" [oobase]="!*.odb" [xelatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [gharbour]="!*.@([Pp][Rr][Gg]|[Cc][Ll][Pp])" [bzcat]="!*.?(t)bz?(2)" [dragon]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|opus|OPUS|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM|iso|ISO)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [xanim]="!*.@(mpg|mpeg|avi|mov|qt)" [lualatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [rgview]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [rvim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [xetex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [lomath]="!*.@(sxm|smf|mml|odf)" [zcat]="!*.@(Z|[gGd]z|t[ag]z)" [lynx]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [uncompress]="!*.Z" [xzcat]="!*.@(?(t)xz|tlz|lzma)" [vim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [loimpress]="!*.@(sxi|sti|pps?(x)|ppt?([mx])|pot?([mx])|?(f)odp|otp)" [dvipdf]="!*.dvi" [mpg321]="!*.mp3" [jadetex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [lobase]="!*.odb" [epdfview]="!*.pdf" [ps2pdf14]="!*.@(?(e)ps|pdf)" [ps2pdf13]="!*.@(?(e)ps|pdf)" [ps2pdf12]="!*.@(?(e)ps|pdf)" [poedit]="!*.po" [luatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [kbabel]="!*.po" [bzme]="!*.@(zip|z|gz|tgz)" [dviselect]="!*.dvi" [realplay]="!*.@(rm?(j)|ra?(m)|smi?(l))" [kdvi]="!*.@(dvi|DVI)?(.@(gz|Z|bz2))" [elinks]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [kghostview]="!*.@(@(?(e)ps|?(E)PS|pdf|PDF)?(.gz|.GZ|.bz2|.BZ2|.Z))" [gtranslator]="!*.po" [unzip]="!*.@(zip|[aegjkswx]ar|exe|pk3|wsz|zargo|xpi|s[tx][cdiw]|sx[gm]|o[dt][tspgfc]|od[bm]|oxt|?(o)xps|epub|cbz|apk|aab|ipa|do[ct][xm]|p[op]t[mx]|xl[st][xm]|pyz|vsix|whl|[Ff][Cc][Ss]td)" [ggv]="!*.@(@(?(e)ps|?(E)PS|pdf|PDF)?(.gz|.GZ|.bz2|.BZ2|.Z))" [oomath]="!*.@(sxm|smf|mml|odf)" [dvipdfmx]="!*.dvi" [makeinfo]="!*.texi*" [okular]="!*.@(okular|@(?(e|x)ps|?(E|X)PS|[pf]df|[PF]DF|dvi|DVI|cb[rz]|CB[RZ]|djv?(u)|DJV?(U)|dvi|DVI|gif|jp?(e)g|miff|tif?(f)|pn[gm]|p[bgp]m|bmp|xpm|ico|xwd|tga|pcx|GIF|JP?(E)G|MIFF|TIF?(F)|PN[GM]|P[BGP]M|BMP|XPM|ICO|XWD|TGA|PCX|epub|EPUB|odt|ODT|fb?(2)|FB?(2)|mobi|MOBI|g3|G3|chm|CHM|md|markdown)?(.?(gz|GZ|bz2|BZ2|xz|XZ)))" [cacaxine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [sxemacs]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [aviplay]="!*.@(avi|asf|wmv)" [rgvim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [dvipdfm]="!*.dvi" [ly2dvi]="!*.ly" [oodraw]="!*.@(sxd|std|sda|sdd|?(f)odg|otg)" [kpdf]="!*.@(?(e)ps|pdf)" [bibtex]="!*.aux" [netscape]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [emacs]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [rview]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [galeon]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [dillo]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [fbxine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [oocalc]="!*.@(sxc|stc|xls?([bmx])|xlw|xlt?([mx])|[ct]sv|?(f)ods|ots)" [harbour]="!*.@([Pp][Rr][Gg]|[Cc][Ll][Pp])" [lodraw]="!*.@(sxd|std|sda|sdd|?(f)odg|otg)" [dvips]="!*.dvi" [ps2pdf]="!*.@(?(e)ps|pdf)" [kate]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [kid3-qt]="!*.@(mp[234c]|og[ag]|@(fl|a)ac|m4[abp]|spx|tta|w?(a)v|wma|aif?(f)|asf|ape)" [pdftex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [gvim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [timidity]="!*.@(mid?(i)|rmi|rcp|[gr]36|g18|mod|xm|it|x3m|s[3t]m|kar)" [ogg123]="!*.@(og[ag]|m3u|flac|spx)" [lzgrep]="!*.@(tlz|lzma)" [ee]="!*.@(gif|jp?(e)g|miff|tif?(f)|pn[gm]|p[bgp]m|bmp|xpm|ico|xwd|tga|pcx)" [unlzma]="!*.@(tlz|lzma)" [lbunzip2]="!*.?(t)bz?(2)" [ooimpress]="!*.@(sxi|sti|pps?(x)|ppt?([mx])|pot?([mx])|?(f)odp|otp)" [xine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [amaya]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [gv]="!*.@(@(?(e)ps|?(E)PS|pdf|PDF)?(.gz|.GZ|.bz2|.BZ2|.Z))" [kid3]="!*.@(mp[234c]|og[ag]|@(fl|a)ac|m4[abp]|spx|tta|w?(a)v|wma|aif?(f)|asf|ape)" [lilypond]="!*.ly" [modplug123]="!*.@(669|abc|am[fs]|d[bs]m|dmf|far|it|mdl|m[eo]d|mid?(i)|mt[2m]|oct|okt?(a)|p[st]m|s[3t]m|ult|umx|wav|xm)" [pbzcat]="!*.?(t)bz?(2)" [unxz]="!*.@(?(t)xz|tlz|lzma)" [playmidi]="!*.@(mid?(i)|cmf)" [lzcat]="!*.@(tlz|lzma)" [slitex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [aaxine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [advi]="!*.dvi" [lzmore]="!*.@(tlz|lzma)" )
__expand_tilde_by_ref ()
{
    [[ -n ${1+set} ]] || return 0;
    [[ $1 == REPLY ]] || local REPLY;
    _comp_expand_tilde "${!1-}";
    [[ $1 == REPLY ]] || printf -v "$1" "$REPLY"
}
__git_eread ()
{
    test -r "$1" && IFS=$__git_CRLF read -r "$2" < "$1"
}
__git_ps1 ()
{
    local exit="$?";
    local pcmode=no;
    local detached=no;
    local ps1pc_start='\u@\h:\w ';
    local ps1pc_end='\$ ';
    local printf_format=' (%s)';
    case "$#" in
        2 | 3)
            pcmode=yes;
            ps1pc_start="$1";
            ps1pc_end="$2";
            printf_format="${3:-$printf_format}";
            PS1="$ps1pc_start$ps1pc_end"
        ;;
        0 | 1)
            printf_format="${1:-$printf_format}"
        ;;
        *)
            return "$exit"
        ;;
    esac;
    local ps1_expanded=yes;
    [ -z "${ZSH_VERSION-}" ] || eval '[[ -o PROMPT_SUBST ]]' || ps1_expanded=no;
    [ -z "${BASH_VERSION-}" ] || shopt -q promptvars || ps1_expanded=no;
    local repo_info rev_parse_exit_code;
    repo_info="$(git rev-parse --git-dir --is-inside-git-dir --is-bare-repository --is-inside-work-tree --show-ref-format --short HEAD 2> /dev/null)";
    rev_parse_exit_code="$?";
    if [ -z "$repo_info" ]; then
        return "$exit";
    fi;
    local LF="$__git_LF";
    local short_sha="";
    if [ "$rev_parse_exit_code" = "0" ]; then
        short_sha="${repo_info##*$LF}";
        repo_info="${repo_info%$LF*}";
    fi;
    local ref_format="${repo_info##*$LF}";
    repo_info="${repo_info%$LF*}";
    local inside_worktree="${repo_info##*$LF}";
    repo_info="${repo_info%$LF*}";
    local bare_repo="${repo_info##*$LF}";
    repo_info="${repo_info%$LF*}";
    local inside_gitdir="${repo_info##*$LF}";
    local g="${repo_info%$LF*}";
    if [ "true" = "$inside_worktree" ] && [ -n "${GIT_PS1_HIDE_IF_PWD_IGNORED-}" ] && [ "$(git config --bool bash.hideIfPwdIgnored)" != "false" ] && git check-ignore -q .; then
        return "$exit";
    fi;
    local sparse="";
    if [ -z "${GIT_PS1_COMPRESSSPARSESTATE-}" ] && [ -z "${GIT_PS1_OMITSPARSESTATE-}" ] && [ "$(git config --bool core.sparseCheckout)" = "true" ]; then
        sparse="|SPARSE";
    fi;
    local r="";
    local b="";
    local step="";
    local total="";
    if [ -d "$g/rebase-merge" ]; then
        __git_eread "$g/rebase-merge/head-name" b;
        __git_eread "$g/rebase-merge/msgnum" step;
        __git_eread "$g/rebase-merge/end" total;
        r="|REBASE";
    else
        if [ -d "$g/rebase-apply" ]; then
            __git_eread "$g/rebase-apply/next" step;
            __git_eread "$g/rebase-apply/last" total;
            if [ -f "$g/rebase-apply/rebasing" ]; then
                __git_eread "$g/rebase-apply/head-name" b;
                r="|REBASE";
            else
                if [ -f "$g/rebase-apply/applying" ]; then
                    r="|AM";
                else
                    r="|AM/REBASE";
                fi;
            fi;
        else
            if [ -f "$g/MERGE_HEAD" ]; then
                r="|MERGING";
            else
                if __git_sequencer_status; then
                    :;
                else
                    if [ -f "$g/BISECT_LOG" ]; then
                        r="|BISECTING";
                    fi;
                fi;
            fi;
        fi;
        if [ -n "$b" ]; then
            :;
        else
            if [ -h "$g/HEAD" ]; then
                b="$(git symbolic-ref HEAD 2> /dev/null)";
            else
                local head="";
                case "$ref_format" in
                    files)
                        if ! __git_eread "$g/HEAD" head; then
                            return "$exit";
                        fi;
                        case $head in
                            "ref: "*)
                                head="${head#ref: }"
                            ;;
                            *)
                                head=""
                            ;;
                        esac
                    ;;
                    *)
                        head="$(git symbolic-ref HEAD 2> /dev/null)"
                    ;;
                esac;
                if test -z "$head"; then
                    detached=yes;
                    b="$(case "${GIT_PS1_DESCRIBE_STYLE-}" in contains)
        git describe --contains HEAD
    ;;
    branch)
        git describe --contains --all HEAD
    ;;
    tag)
        git describe --tags HEAD
    ;;
    describe)
        git describe HEAD
    ;;
    * | default)
        git describe --tags --exact-match HEAD
    ;;
esac 2> /dev/null)" || b="$short_sha...";
                    b="($b)";
                else
                    b="$head";
                fi;
            fi;
        fi;
    fi;
    if [ -n "$step" ] && [ -n "$total" ]; then
        r="$r $step/$total";
    fi;
    local conflict="";
    if [ "${GIT_PS1_SHOWCONFLICTSTATE-}" = "yes" ] && [ "$(git ls-files --unmerged 2> /dev/null)" ]; then
        conflict="|CONFLICT";
    fi;
    local w="";
    local i="";
    local s="";
    local u="";
    local h="";
    local c="";
    local p="";
    local upstream="";
    if [ "true" = "$inside_gitdir" ]; then
        if [ "true" = "$bare_repo" ]; then
            c="BARE:";
        else
            b="GIT_DIR!";
        fi;
    else
        if [ "true" = "$inside_worktree" ]; then
            if [ -n "${GIT_PS1_SHOWDIRTYSTATE-}" ] && [ "$(git config --bool bash.showDirtyState)" != "false" ]; then
                git diff --no-ext-diff --quiet || w="*";
                git diff --no-ext-diff --cached --quiet || i="+";
                if [ -z "$short_sha" ] && [ -z "$i" ]; then
                    i="#";
                fi;
            fi;
            if [ -n "${GIT_PS1_SHOWSTASHSTATE-}" ] && git rev-parse --verify --quiet refs/stash > /dev/null; then
                s="$";
            fi;
            if [ -n "${GIT_PS1_SHOWUNTRACKEDFILES-}" ] && [ "$(git config --bool bash.showUntrackedFiles)" != "false" ] && git ls-files --others --exclude-standard --directory --no-empty-directory --error-unmatch -- ':/*' > /dev/null 2> /dev/null; then
                u="%${ZSH_VERSION+%}";
            fi;
            if [ -n "${GIT_PS1_COMPRESSSPARSESTATE-}" ] && [ "$(git config --bool core.sparseCheckout)" = "true" ]; then
                h="?";
            fi;
            if [ -n "${GIT_PS1_SHOWUPSTREAM-}" ]; then
                __git_ps1_show_upstream;
            fi;
        fi;
    fi;
    local z="${GIT_PS1_STATESEPARATOR- }";
    b=${b##refs/heads/};
    if [ "$pcmode" = yes ] && [ "$ps1_expanded" = yes ]; then
        __git_ps1_branch_name=$b;
        b="\${__git_ps1_branch_name}";
    fi;
    if [ -n "${GIT_PS1_SHOWCOLORHINTS-}" ]; then
        __git_ps1_colorize_gitstring;
    fi;
    local f="$h$w$i$s$u$p";
    local gitstring="$c$b${f:+$z$f}${sparse}$r${upstream}${conflict}";
    if [ "$pcmode" = yes ]; then
        if [ "${__git_printf_supports_v-}" != yes ]; then
            gitstring=$(printf -- "$printf_format" "$gitstring");
        else
            printf -v gitstring -- "$printf_format" "$gitstring";
        fi;
        PS1="$ps1pc_start$gitstring$ps1pc_end";
    else
        printf -- "$printf_format" "$gitstring";
    fi;
    return "$exit"
}
__git_ps1_colorize_gitstring ()
{
    if [ -n "${ZSH_VERSION-}" ]; then
        local c_red='%F{red}';
        local c_green='%F{green}';
        local c_lblue='%F{blue}';
        local c_clear='%f';
    else
        local c_pre="${GIT_PS1_COLOR_PRE-$__git_SOH}${__git_ESC}[";
        local c_post="m${GIT_PS1_COLOR_POST-$__git_STX}";
        local c_red="${c_pre}31${c_post}";
        local c_green="${c_pre}32${c_post}";
        local c_lblue="${c_pre}1;34${c_post}";
        local c_clear="${c_pre}0${c_post}";
    fi;
    local bad_color="$c_red";
    local ok_color="$c_green";
    local flags_color="$c_lblue";
    local branch_color="";
    if [ "$detached" = no ]; then
        branch_color="$ok_color";
    else
        branch_color="$bad_color";
    fi;
    if [ -n "$c" ]; then
        c="$branch_color$c$c_clear";
    fi;
    b="$branch_color$b$c_clear";
    if [ -n "$w" ]; then
        w="$bad_color$w$c_clear";
    fi;
    if [ -n "$i" ]; then
        i="$ok_color$i$c_clear";
    fi;
    if [ -n "$s" ]; then
        s="$flags_color$s$c_clear";
    fi;
    if [ -n "$u" ]; then
        u="$bad_color$u$c_clear";
    fi
}
__git_ps1_show_upstream ()
{
    local key value;
    local svn_remotes="" svn_url_pattern="" count n;
    local upstream_type=git legacy="" verbose="" name="";
    local LF="$__git_LF";
    local output="$(git config -z --get-regexp '^(svn-remote\..*\.url|bash\.showupstream)$' 2> /dev/null | tr '\0\n' '\n ')";
    while read -r key value; do
        case "$key" in
            bash.showupstream)
                GIT_PS1_SHOWUPSTREAM="$value";
                if [ -z "${GIT_PS1_SHOWUPSTREAM}" ]; then
                    p="";
                    return;
                fi
            ;;
            svn-remote.*.url)
                svn_remotes=${svn_remotes}${value}${LF};
                svn_url_pattern="$svn_url_pattern\\|$value";
                upstream_type=svn+git
            ;;
        esac;
    done <<-OUTPUT
$output
OUTPUT

    local option
    for option in ${GIT_PS1_SHOWUPSTREAM-};
    do
        case "$option" in
            git | svn)
                upstream_type="$option"
            ;;
            verbose)
                verbose=1
            ;;
            legacy)
                legacy=1
            ;;
            name)
                name=1
            ;;
        esac;
    done;
    case "$upstream_type" in
        git)
            upstream_type="@{upstream}"
        ;;
        svn*)
            local svn_upstream="$(git log --first-parent -1 --grep="^git-svn-id: \(${svn_url_pattern#??}\)" 2> /dev/null)";
            if [ -n "$svn_upstream" ]; then
                svn_upstream=${svn_upstream##*$LF};
                svn_upstream=${svn_upstream#*: };
                svn_upstream=${svn_upstream%@*};
                case ${LF}${svn_remotes} in
                    *"${LF}${svn_upstream}${LF}"*)
                        upstream_type=${GIT_SVN_ID:-git-svn}
                    ;;
                    *)
                        upstream_type=${svn_upstream#/}
                    ;;
                esac;
            else
                if [ "svn+git" = "$upstream_type" ]; then
                    upstream_type="@{upstream}";
                fi;
            fi
        ;;
    esac;
    if [ -z "$legacy" ]; then
        count="$(git rev-list --count --left-right "$upstream_type"...HEAD 2> /dev/null)";
    else
        local commits;
        if commits="$(git rev-list --left-right "$upstream_type"...HEAD 2> /dev/null)"; then
            local commit behind=0 ahead=0;
            for commit in $commits;
            do
                case "$commit" in
                    "<"*)
                        behind=$((behind+1))
                    ;;
                    *)
                        ahead=$((ahead+1))
                    ;;
                esac;
            done;
            count="$behind      $ahead";
        else
            count="";
        fi;
    fi;
    if [ -z "$verbose" ]; then
        case "$count" in
            "")
                p=""
            ;;
            "0  0")
                p="="
            ;;
            "0  "*)
                p=">"
            ;;
            *"  0")
                p="<"
            ;;
            *)
                p="<>"
            ;;
        esac;
    else
        case "$count" in
            "")
                upstream=""
            ;;
            "0  0")
                upstream="|u="
            ;;
            "0  "*)
                upstream="|u+${count#0  }"
            ;;
            *"  0")
                upstream="|u-${count%   0}"
            ;;
            *)
                upstream="|u+${count#*  }-${count%      *}"
            ;;
        esac;
        if [ -n "$count" ] && [ -n "$name" ]; then
            __git_ps1_upstream_name=$(git rev-parse --abbrev-ref "$upstream_type" 2> /dev/null);
            if [ "$pcmode" = yes ] && [ "$ps1_expanded" = yes ]; then
                upstream="$upstream \${__git_ps1_upstream_name}";
            else
                upstream="$upstream ${__git_ps1_upstream_name}";
                unset __git_ps1_upstream_name;
            fi;
        fi;
    fi
}
__git_sequencer_status ()
{
    local todo;
    if test -f "$g/CHERRY_PICK_HEAD"; then
        r="|CHERRY-PICKING";
        return 0;
    else
        if test -f "$g/REVERT_HEAD"; then
            r="|REVERTING";
            return 0;
        else
            if __git_eread "$g/sequencer/todo" todo; then
                case "$todo" in
                    p[\ \       ] | pick[\ \    ]*)
                        r="|CHERRY-PICKING";
                        return 0
                    ;;
                    revert[\ \  ]*)
                        r="|REVERTING";
                        return 0
                    ;;
                esac;
            fi;
        fi;
    fi;
    return 1
}
__load_completion ()
{
    _comp_load "$@"
}
__ltrim_colon_completions ()
{
    _comp_ltrim_colon_completions "$@"
}
__parse_options ()
{
    local -a _options=();
    _comp_compgen_help__parse "$1";
    printf '%s\n' "${_options[@]}"
}
_allowed_groups ()
{
    _comp_compgen -c "${1:-$cur}" allowed_groups
}
_allowed_users ()
{
    _comp_compgen -c "${1:-$cur}" allowed_users
}
_available_interfaces ()
{
    _comp_compgen_available_interfaces "$@"
}
_bashcomp_try_faketty ()
{
    _comp_try_faketty "$@"
}
_cd ()
{
    declare -F _comp_cmd_cd &> /dev/null || __load_completion cd;
    _comp_cmd_cd "$@"
}
_cd_devices ()
{
    _comp_compgen -a cd_devices
}
_command ()
{
    _comp_command "$@"
}
_command_offset ()
{
    local words;
    unset -v words;
    _comp_command_offset "$@"
}
_comp__find_original_word ()
{
    REPLY=$1;
    [[ -v cword && -v words ]] || return 0;
    local reassembled_offset=$1 i=0 j;
    for ((j = 0; j < reassembled_offset; j++))
    do
        local word=${words[j]};
        while [[ -n $word && i -lt ${#COMP_WORDS[@]} && $word == *"${COMP_WORDS[i]}"* ]]; do
            word=${word#*"${COMP_WORDS[i++]}"};
        done;
    done;
    REPLY=$i
}
_comp__get_cword_at_cursor ()
{
    local cword words=();
    _comp__reassemble_words "$1" words cword;
    local i cur="" index=$COMP_POINT lead=${COMP_LINE:0:COMP_POINT};
    if [[ $index -gt 0 && ( -n $lead && -n ${lead//[[:space:]]/} ) ]]; then
        cur=$COMP_LINE;
        for ((i = 0; i <= cword; ++i))
        do
            while [[ ${#cur} -ge ${#words[i]} && ${cur:0:${#words[i]}} != "${words[i]-}" ]]; do
                cur=${cur:1};
                ((index > 0)) && ((index--));
            done;
            if ((i < cword)); then
                local old_size=${#cur};
                cur=${cur#"${words[i]}"};
                local new_size=${#cur};
                ((index -= old_size - new_size));
            fi;
        done;
        [[ -n $cur && ! -n ${cur//[[:space:]]/} ]] && cur=;
        ((index < 0)) && index=0;
    fi;
    local IFS='
';
    local "$2" "$3" "$4" && _comp_upvars -a"${#words[@]}" "$2" ${words[@]+"${words[@]}"} -v "$3" "$cword" -v "$4" "${cur:0:index}"
}
_comp__included_ssh_config_files ()
{
    (($# < 1)) && echo "bash_completion: $FUNCNAME: missing mandatory argument CONFIG" 1>&2;
    local configfile i files f REPLY;
    configfile=$1;
    local relative_include_base;
    if [[ $configfile == /etc/ssh* ]]; then
        relative_include_base="/etc/ssh";
    else
        relative_include_base="$HOME/.ssh";
    fi;
    local depth=1;
    local -a included;
    local -a include_files;
    included=("$configfile");
    local max_depth=16;
    while ((${#included[@]} > 0 && depth++ < max_depth)); do
        _comp_split include_files "$(command sed -ne 's/^[[:blank:]]*[Ii][Nn][Cc][Ll][Uu][Dd][Ee][[:blank:]]\(.*\)$/\1/p' "${included[@]}")" || return;
        included=();
        for i in "${include_files[@]}";
        do
            if [[ $i != [~/]* ]]; then
                i="${relative_include_base}/${i}";
            fi;
            _comp_expand_tilde "$i";
            if _comp_expand_glob files '$REPLY'; then
                for f in "${files[@]}";
                do
                    if [[ -r $f && ! -d $f ]]; then
                        config+=("$f");
                        included+=("$f");
                    fi;
                done;
            fi;
        done;
    done
}
_comp__reassemble_words ()
{
    local exclude="" i j line ref;
    if [[ -n $1 ]]; then
        exclude="[${1//[^$COMP_WORDBREAKS]/}]";
    fi;
    printf -v "$3" %s "$COMP_CWORD";
    if [[ -n $exclude ]]; then
        line=$COMP_LINE;
        for ((i = 0, j = 0; i < ${#COMP_WORDS[@]}; i++, j++))
        do
            while [[ $i -gt 0 && ${COMP_WORDS[i]} == +($exclude) ]]; do
                [[ $line != [[:blank:]]* ]] && ((j >= 2)) && ((j--));
                ref="$2[$j]";
                printf -v "$ref" %s "${!ref-}${COMP_WORDS[i]}";
                ((i == COMP_CWORD)) && printf -v "$3" %s "$j";
                line=${line#*"${COMP_WORDS[i]}"};
                if ((i < ${#COMP_WORDS[@]} - 1)); then
                    ((i++));
                else
                    break 2;
                fi;
                [[ $line == [[:blank:]]* ]] && ((j++));
            done;
            ref="$2[$j]";
            printf -v "$ref" %s "${!ref-}${COMP_WORDS[i]}";
            line=${line#*"${COMP_WORDS[i]}"};
            ((i == COMP_CWORD)) && printf -v "$3" %s "$j";
        done;
        ((i == COMP_CWORD)) && printf -v "$3" %s "$j";
    else
        for i in "${!COMP_WORDS[@]}";
        do
            printf -v "$2[i]" %s "${COMP_WORDS[i]}";
        done;
    fi
}
_comp__split_longopt ()
{
    if [[ $cur == --?*=* ]]; then
        prev=${cur%%?(\\)=*};
        cur=${cur#*=};
        return 0;
    fi;
    return 1
}
_comp_abspath ()
{
    REPLY=$1;
    [[ $REPLY == /* ]] || REPLY=$PWD/$REPLY;
    REPLY=${REPLY//+(\/)/\/};
    while true; do
        case $REPLY in
            */./*)
                REPLY=${REPLY//\/.\//\/}
            ;;
            */.)
                REPLY=${REPLY%/.}
            ;;
            /..?(/*))
                REPLY=${REPLY#/..}
            ;;
            */+([^/])/../*)
                REPLY=${REPLY/\/+([^\/])\/..\//\/}
            ;;
            */+([^/])/..)
                REPLY=${REPLY%/+([^/])/..}
            ;;
            *)
                break
            ;;
        esac;
    done;
    [[ -n $REPLY ]] || REPLY=/
}
_comp_as_root ()
{
    [[ $EUID -eq 0 || -n ${_comp_root_command-} ]]
}
_comp_awk ()
{
    command awk "$@"
}
_comp_command ()
{
    local words;
    unset -v words;
    local offset i;
    offset=1;
    for ((i = 1; i <= COMP_CWORD; i++))
    do
        if [[ ${COMP_WORDS[i]} != -* ]]; then
            offset=$i;
            break;
        fi;
    done;
    _comp_command_offset $offset
}
_comp_command_offset ()
{
    local REPLY;
    _comp__find_original_word "$1";
    local word_offset=$REPLY;
    local COMP_LINE=$COMP_LINE COMP_POINT=$COMP_POINT COMP_CWORD=$COMP_CWORD;
    local -a comp_words=("${COMP_WORDS[@]}");
    local -a COMP_WORDS=("${comp_words[@]}");
    local i tail;
    for ((i = 0; i < word_offset; i++))
    do
        tail=${COMP_LINE#*"${COMP_WORDS[i]}"};
        ((COMP_POINT -= ${#COMP_LINE} - ${#tail}));
        COMP_LINE=$tail;
    done;
    COMP_WORDS=("${COMP_WORDS[@]:word_offset}");
    ((COMP_CWORD -= word_offset));
    COMPREPLY=();
    local cur;
    _comp_get_words cur;
    if ((COMP_CWORD == 0)); then
        _comp_compgen_commands;
    else
        _comp_dequote "${COMP_WORDS[0]}" || REPLY=${COMP_WORDS[0]};
        local cmd=$REPLY compcmd=$REPLY;
        local cspec=$(complete -p -- "$cmd" 2> /dev/null);
        if [[ ! -n $cspec && $cmd == */* ]]; then
            cspec=$(complete -p -- "${cmd##*/}" 2> /dev/null);
            [[ -n $cspec ]] && compcmd=${cmd##*/};
        fi;
        if [[ ! -n $cspec ]]; then
            compcmd=${cmd##*/};
            _comp_load -D -- "$compcmd";
            cspec=$(complete -p -- "$compcmd" 2> /dev/null);
        fi;
        local retry_count=0;
        while true; do
            local args original_cur=${comp_args[1]-$cur};
            if ((${#COMP_WORDS[@]} >= 2)); then
                args=("$cmd" "$original_cur" "${COMP_WORDS[-2]}");
            else
                args=("$cmd" "$original_cur");
            fi;
            if [[ ! -n $cspec ]]; then
                if ((${#COMPREPLY[@]} == 0)); then
                    _comp_complete_minimal "${args[@]}";
                fi;
            else
                if [[ $cspec == *\ -[CF]\ * ]]; then
                    if [[ $cspec == *' -F '* ]]; then
                        local func=${cspec#* -F };
                        func=${func%% *};
                        $func "${args[@]}";
                        if (($? == 124 && retry_count++ == 0)); then
                            COMPREPLY=();
                            cspec=$(complete -p -- "$compcmd" 2> /dev/null);
                            [[ -n $cspec ]] || break;
                            continue;
                        fi;
                    else
                        local completer=${cspec#* -C \'};
                        if ! _comp_dequote "'$completer"; then
                            _minimal "${args[@]}";
                            break;
                        fi;
                        completer=${REPLY[0]};
                        local -a suggestions;
                        local IFS='
';
                        local reset_monitor=$(shopt -po monitor) reset_lastpipe=$(shopt -p lastpipe) reset_noglob=$(shopt -po noglob);
                        set +o monitor;
                        shopt -s lastpipe;
                        set -o noglob;
                        COMP_KEY="$COMP_KEY" COMP_LINE="$COMP_LINE" COMP_POINT="$COMP_POINT" COMP_TYPE="$COMP_TYPE" $completer "${args[@]}" | mapfile -t suggestions;
                        $reset_monitor;
                        $reset_lastpipe;
                        $reset_noglob;
                        _comp_unlocal IFS;
                        local suggestion;
                        local i=0;
                        COMPREPLY=();
                        for suggestion in "${suggestions[@]}";
                        do
                            COMPREPLY[i]+=${COMPREPLY[i]+'
'}$suggestion;
                            if [[ $suggestion != *\\ ]]; then
                                ((i++));
                            fi;
                        done;
                    fi;
                    local opt;
                    while [[ $cspec == *" -o "* ]]; do
                        cspec=${cspec#*-o };
                        opt=${cspec%% *};
                        compopt -o "$opt";
                        cspec=${cspec#"$opt"};
                    done;
                else
                    cspec=${cspec#complete};
                    cspec=${cspec%%@("$compcmd"|"'${compcmd//\'/\'\\\'\'}'")};
                    eval "_comp_compgen -- $cspec";
                fi;
            fi;
            break;
        done;
    fi
}
_comp_compgen ()
{
    local _append=;
    local _var=;
    local _cur=${_comp_compgen__cur-${cur-}};
    local _dir="";
    local _ifs='
' _has_ifs="";
    local _icmd="" _xcmd="";
    local -a _upvars=();
    local _old_nocasematch="";
    if shopt -q nocasematch; then
        _old_nocasematch=set;
        shopt -u nocasematch;
    fi;
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':av:U:Rc:C:lF:i:x:' _opt "$@"; do
        case $_opt in
            a)
                _append=set
            ;;
            v)
                if [[ $OPTARG == @(*[^_a-zA-Z0-9]*|[0-9]*|''|_*|IFS|OPTIND|OPTARG|OPTERR|cur) ]]; then
                    printf 'bash_completion: %s: -v: invalid array name `%s'\''\n' "$FUNCNAME" "$OPTARG" 1>&2;
                    return 2;
                fi;
                _var=$OPTARG
            ;;
            U)
                if [[ $OPTARG == @(*[^_a-zA-Z0-9]*|[0-9]*|'') ]]; then
                    printf 'bash_completion: %s: -U: invalid variable name `%s'\''\n' "$FUNCNAME" "$OPTARG" 1>&2;
                    return 2;
                else
                    if [[ $OPTARG == @(_*|IFS|OPTIND|OPTARG|OPTERR|cur) ]]; then
                        printf 'bash_completion: %s: -U: unnecessary to mark `%s'\'' as upvar\n' "$FUNCNAME" "$OPTARG" 1>&2;
                        return 2;
                    fi;
                fi;
                _upvars+=("$OPTARG")
            ;;
            c)
                _cur=$OPTARG
            ;;
            R)
                _cur=""
            ;;
            C)
                if [[ ! -n $OPTARG ]]; then
                    printf 'bash_completion: %s: -C: invalid directory name `%s'\''\n' "$FUNCNAME" "$OPTARG" 1>&2;
                    return 2;
                fi;
                _dir=$OPTARG
            ;;
            l)
                _has_ifs=set _ifs='
'
            ;;
            F)
                _has_ifs=set _ifs=$OPTARG
            ;;
            [ix])
                if [[ ! -n $OPTARG ]]; then
                    printf 'bash_completion: %s: -%s: invalid command name `%s'\''\n' "$FUNCNAME" "$_opt" "$OPTARG" 1>&2;
                    return 2;
                else
                    if [[ -n $_icmd ]]; then
                        printf 'bash_completion: %s: -%s: `-i %s'\'' is already specified\n' "$FUNCNAME" "$_opt" "$_icmd" 1>&2;
                        return 2;
                    else
                        if [[ -n $_xcmd ]]; then
                            printf 'bash_completion: %s: -%s: `-x %s'\'' is already specified\n' "$FUNCNAME" "$_opt" "$_xcmd" 1>&2;
                            return 2;
                        fi;
                    fi;
                fi
            ;;&
            i)
                _icmd=$OPTARG
            ;;
            x)
                _xcmd=$OPTARG
            ;;
            *)
                printf 'bash_completion: %s: usage error\n' "$FUNCNAME" 1>&2;
                return 2
            ;;
        esac;
    done;
    [[ -n $_old_nocasematch ]] && shopt -s nocasematch;
    shift "$((OPTIND - 1))";
    if (($# == 0)); then
        printf 'bash_completion: %s: unexpected number of arguments\n' "$FUNCNAME" 1>&2;
        printf 'usage: %s [-alR|-F SEP|-v ARR|-c CUR] -- ARGS...' "$FUNCNAME" 1>&2;
        return 2;
    fi;
    if [[ ! -n $_var ]]; then
        _var=${_comp_compgen__var-COMPREPLY};
        [[ -n $_append ]] || _append=${_comp_compgen__append-};
    fi;
    if [[ $1 != -* ]]; then
        if [[ -n $_has_ifs ]]; then
            printf 'bash_completion: %s: `-l'\'' and `-F sep'\'' are not supported for generators\n' "$FUNCNAME" 1>&2;
            return 2;
        fi;
        local -a _generator;
        if [[ -n $_icmd ]]; then
            _generator=("_comp_cmd_${_icmd//[^a-zA-Z0-9_]/_}__compgen_$1");
        else
            if [[ -n $_xcmd ]]; then
                _generator=(_comp_xfunc "$_xcmd" "compgen_$1");
            else
                _generator=("_comp_compgen_$1");
            fi;
        fi;
        if ! declare -F -- "${_generator[0]}" &> /dev/null; then
            printf 'bash_completion: %s: unrecognized generator `%s'\'' (function %s not found)\n' "$FUNCNAME" "$1" "${_generator[0]}" 1>&2;
            return 2;
        fi;
        shift;
        _comp_compgen__call_generator "$@";
    else
        if [[ -n $_icmd || -n $_xcmd ]]; then
            printf 'bash_completion: %s: generator name is unspecified for `%s'\''\n' "$FUNCNAME" "${_icmd:+-i $_icmd}${_xcmd:+x $_xcmd}" 1>&2;
            return 2;
        fi;
        local IFS='
';
        if [[ $* == *\$[0-9]* || $* == *\$\{[0-9]* ]]; then
            printf 'bash_completion: %s: positional parameter $1, $2, ... do not work inside this function\n' "$FUNCNAME" 1>&2;
            return 2;
        fi;
        _comp_compgen__call_builtin "$@";
    fi
}
_comp_compgen__call_builtin ()
{
    if [[ -n $_dir ]]; then
        local _original_pwd=$PWD;
        local PWD=${PWD-} OLDPWD=${OLDPWD-};
        command cd -- "$_dir" &> /dev/null || {
            _comp_compgen__error_fallback;
            return
        };
    fi;
    local -a _result=();
    IFS=$_ifs compgen -V _result -X '' "$@" ${_cur:+-- "$_cur"} || {
        _comp_compgen__error_fallback;
        return
    };
    [[ -n $_dir ]] && command cd -- "$_original_pwd";
    ((${#_upvars[@]})) && _comp_unlocal "${_upvars[@]}";
    ((${#_result[@]})) || return;
    if [[ -n $_append ]]; then
        eval -- "$_var+=(\"\${_result[@]}\")";
    else
        eval -- "$_var=(\"\${_result[@]}\")";
    fi;
    return
}
_comp_compgen__call_generator ()
{
    ((${#_upvars[@]})) && _comp_unlocal "${_upvars[@]}";
    if [[ -n $_dir ]]; then
        local _original_pwd=$PWD;
        local PWD=${PWD-} OLDPWD=${OLDPWD-};
        command cd -- "$_dir" &> /dev/null || {
            _comp_compgen__error_fallback;
            return
        };
    fi;
    local _comp_compgen__append=$_append;
    local _comp_compgen__var=$_var;
    local _comp_compgen__cur=$_cur cur=$_cur;
    "${_generator[@]}" "$@";
    local _status=$?;
    [[ -n $_dir ]] && command cd -- "$_original_pwd";
    return "$_status"
}
_comp_compgen__error_fallback ()
{
    local _status=$?;
    if [[ -n $_append ]]; then
        eval -- "$_var+=()";
    else
        eval -- "$_var=()";
    fi;
    return "$_status"
}
_comp_compgen_allowed_groups ()
{
    if _comp_as_root; then
        _comp_compgen -- -g;
    else
        _comp_compgen_split -- "$(id -Gn 2> /dev/null || groups 2> /dev/null)";
    fi
}
_comp_compgen_allowed_users ()
{
    if _comp_as_root; then
        _comp_compgen -- -u;
    else
        _comp_compgen_split -- "$(id -un 2> /dev/null || whoami 2> /dev/null)";
    fi
}
_comp_compgen_available_interfaces ()
{
    local PATH=$PATH:/sbin;
    local generated;
    _comp_compgen -v generated split -- "$({ if [[ ${1-} == -w ]]; then
    iwconfig;
else
    if [[ ${1-} == -a ]]; then
        ip -c=never link show up || ip link show up || ifconfig;
    else
        ip -c=never link show || ip link show || ifconfig -a;
    fi;
fi; } 2> /dev/null | _comp_awk '/^[^ \t]/ { if ($1 ~ /^[0-9]+:/) { print $2 } else { print $1 } }')" && _comp_compgen -U generated set "${generated[@]%:}"
}
_comp_compgen_cd_devices ()
{
    _comp_compgen -c "${cur:-/dev/}" -- -f -d -X "!*/?([amrs])cd!(c-*)"
}
_comp_compgen_commands ()
{
    [[ ! -n ${cur-} ]] && shopt -q no_empty_cmd_completion && return 1;
    _comp_compgen -- -c -o plusdirs && compopt -o filenames
}
_comp_compgen_configured_interfaces ()
{
    local -a files;
    if [[ -f /etc/debian_version ]]; then
        _comp_expand_glob files '/etc/network/interfaces /etc/network/interfaces.d/*' || return 0;
        _comp_compgen -U files split -- "$(command sed -ne 's|^iface \([^ ]\{1,\}\).*$|\1|p' "${files[@]}" 2> /dev/null)";
    else
        if [[ -f /etc/SuSE-release ]]; then
            _comp_expand_glob files '/etc/sysconfig/network/ifcfg-*' || return 0;
            _comp_compgen -U files split -- "$(printf '%s\n' "${files[@]}" | command sed -ne 's|.*ifcfg-\([^*].*\)$|\1|p')";
        else
            if [[ -f /etc/pld-release ]]; then
                _comp_compgen -U files split -- "$(command ls -B /etc/sysconfig/interfaces | command sed -ne 's|.*ifcfg-\([^*].*\)$|\1|p')";
            else
                _comp_expand_glob files '/etc/sysconfig/network-scripts/ifcfg-*' || return 0;
                _comp_compgen -U files split -- "$(printf '%s\n' "${files[@]}" | command sed -ne 's|.*ifcfg-\([^*].*\)$|\1|p')";
            fi;
        fi;
    fi
}
_comp_compgen_dvd_devices ()
{
    _comp_compgen -c "${cur:-/dev/}" -- -f -d -X "!*/?(r)dvd*"
}
_comp_compgen_filedir ()
{
    _comp_compgen_tilde && return;
    local -a toks;
    local _arg=${1-};
    if [[ $_arg == -d ]]; then
        _comp_compgen -v toks -- -d;
    else
        local REPLY;
        _comp_quote_compgen "${cur-}";
        local _quoted=$REPLY;
        _comp_unlocal REPLY;
        [[ $_quoted == "''" ]] && _quoted="";
        local _xspec=${_arg:+"!*.@($_arg|${_arg^^})"} _plusdirs=();
        local _opts=(-f -X "$_xspec");
        [[ -n $_xspec ]] && _plusdirs=(-o plusdirs);
        [[ -n ${BASH_COMPLETION_FILEDIR_FALLBACK-} || ! -n ${_plusdirs-} ]] || _opts+=("${_plusdirs[@]}");
        _comp_compgen -v toks -c "$_quoted" -- "${_opts[@]}";
        [[ -n ${BASH_COMPLETION_FILEDIR_FALLBACK-} && -n $_arg && ${#toks[@]} -lt 1 ]] && _comp_compgen -av toks -c "$_quoted" -- -f ${_plusdirs+"${_plusdirs[@]}"};
    fi;
    if ((${#toks[@]} != 0)); then
        if [[ $cur != ?(*/).. ]]; then
            _comp_compgen -Rv toks -- -X '?(*/)@(.|..)' -W '"${toks[@]}"';
        fi;
    fi;
    if ((${#toks[@]} != 0)); then
        compopt -o filenames 2> /dev/null;
    fi;
    local IFS='
';
    _comp_compgen -U toks set ${toks[@]+"${toks[@]}"}
}
_comp_compgen_filedir_xspec ()
{
    _comp_compgen_tilde && return;
    local REPLY;
    _comp_quote_compgen "$cur";
    local quoted=$REPLY;
    local xspec=${_comp_xspecs[${1##*/}]-${_xspecs[${1##*/}]-}};
    local -a toks;
    _comp_compgen -v toks -c "$quoted" -- -d;
    eval xspec="${xspec}";
    local matchop=!;
    if [[ $xspec == !* ]]; then
        xspec=${xspec#!};
        matchop=@;
    fi;
    xspec="$matchop($xspec|${xspec^^})";
    _comp_compgen -av toks -c "$quoted" -- -f -X "@(|!($xspec))";
    [[ -n ${BASH_COMPLETION_FILEDIR_FALLBACK-} && ${#toks[@]} -lt 1 ]] && _comp_compgen -av toks -c "$quoted" -- -f;
    ((${#toks[@]})) || return 1;
    if [[ $cur != ?(*/).. ]]; then
        _comp_compgen -Rv toks -- -X '?(*/)@(.|..)' -W '"${toks[@]}"' || return 1;
    fi;
    compopt -o filenames;
    _comp_compgen -RU toks -- -W '"${toks[@]}"'
}
_comp_compgen_fstypes ()
{
    local _fss;
    if [[ -e /proc/filesystems ]]; then
        _fss="$(cut -d' ' -f2 /proc/filesystems)
             $(_comp_awk '! /\*/ { print $NF }' /etc/filesystems 2> /dev/null)";
    else
        _fss="$(_comp_awk '/^[ \t]*[^#]/ { print $3 }' /etc/fstab 2> /dev/null)
             $(_comp_awk '/^[ \t]*[^#]/ { print $3 }' /etc/mnttab 2> /dev/null)
             $(_comp_awk '/^[ \t]*[^#]/ { print $4 }' /etc/vfstab 2> /dev/null)
             $(_comp_awk '{ print $1 }' /etc/dfs/fstypes 2> /dev/null)
             $(lsvfs 2> /dev/null | _comp_awk '$1 !~ /^(Filesystem|[^a-zA-Z])/ { print $1 }')
             $([[ -d /etc/fs ]] && command ls /etc/fs)";
    fi;
    [[ -n $_fss ]] && _comp_compgen_split -- "$_fss"
}
_comp_compgen_gids ()
{
    if type getent &> /dev/null; then
        _comp_compgen_split -- "$(getent group | cut -d: -f3)";
    else
        if type perl &> /dev/null; then
            _comp_compgen_split -- "$(perl -e 'while (($gid) = (getgrent)[2]) { print $gid . "\n" }')";
        else
            _comp_compgen_split -- "$(cut -d: -f3 /etc/group)";
        fi;
    fi
}
_comp_compgen_help ()
{
    (($#)) || set -- -- --help;
    local -a _lines;
    _comp_compgen_help__get_help_lines "$@" || return "$?";
    local -a options=();
    local _line;
    for _line in "${_lines[@]}";
    do
        [[ $_line == *([[:blank:]])-* ]] || continue;
        while [[ $_line =~ ((^|[^-])-[A-Za-z0-9?][[:space:]]+)\[?[A-Z0-9]+([,_-]+[A-Z0-9]+)?(\.\.+)?\]? ]]; do
            _line=${_line/"${BASH_REMATCH[0]}"/"${BASH_REMATCH[1]}"};
        done;
        _comp_compgen_help__parse "${_line// or /, }";
    done;
    ((${#options[@]})) || return 1;
    _comp_compgen -U options -- -W '"${options[@]}"';
    return 0
}
_comp_compgen_help__get_help_lines ()
{
    local -a help_cmd;
    case ${1-} in
        -)
            if (($# > 1)); then
                printf 'bash_completion: %s -: extra arguments for -\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -c cmd args...\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s [-- args...]\n' "${FUNCNAME[1]}" 1>&2;
                return 2;
            fi;
            help_cmd=(exec cat)
        ;;
        -c)
            if (($# < 2)); then
                printf 'bash_completion: %s -c: no command is specified\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -c cmd args...\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s [-- args...]\n' "${FUNCNAME[1]}" 1>&2;
                return 2;
            fi;
            help_cmd=("${@:2}")
        ;;
        --)
            shift 1
        ;&
        *)
            local REPLY;
            _comp_dequote "${comp_args[0]-}" || REPLY=${comp_args[0]-};
            help_cmd=("${REPLY:-false}" "$@")
        ;;
    esac;
    local REPLY;
    _comp_split -l REPLY "$(LC_ALL=C "${help_cmd[@]}" 2>&1)" && _lines=("${REPLY[@]}")
}
_comp_compgen_help__parse ()
{
    local option option2 i;
    option=;
    local -a array;
    if _comp_split -F '
,/|' array "$1"; then
        for i in "${array[@]}";
        do
            case "$i" in
                ---*)
                    break
                ;;
                --?*)
                    option=$i;
                    break
                ;;
                -?*)
                    [[ -n $option ]] || option=$i
                ;;
                *)
                    break
                ;;
            esac;
        done;
    fi;
    [[ -n $option ]] || return 1;
    if [[ $option =~ (\[((no|dont)-?)\]). ]]; then
        option2=${option/"${BASH_REMATCH[1]}"/};
        option2=${option2%%[<{().[]*};
        options+=("${option2/=*/=}");
        option=${option/"${BASH_REMATCH[1]}"/"${BASH_REMATCH[2]}"};
    fi;
    [[ $option =~ ^([^=<{().[]|\.[A-Za-z0-9])+=? ]] && options+=("$BASH_REMATCH")
}
_comp_compgen_inserted_kernel_modules ()
{
    _comp_compgen -c "${1:-$cur}" split -- "$(PATH="$PATH:/sbin" lsmod | _comp_awk '{if (NR != 1) print $1}')"
}
_comp_compgen_ip_addresses ()
{
    local _n;
    case ${1-} in
        -a)
            _n='6\{0,1\}'
        ;;
        -6)
            _n='6'
        ;;
        *)
            _n=
        ;;
    esac;
    local PATH=$PATH:/sbin;
    local addrs;
    _comp_compgen -v addrs split -- "$({ ip -c=never addr show || ip addr show || LC_ALL=C ifconfig -a; } 2> /dev/null | command sed -e 's/[[:space:]]addr:/ /' -ne "s|.*inet${_n}[[:space:]]\{1,\}\([^[:space:]/]*\).*|\1|p")" || return;
    if [[ ! -n $_n ]]; then
        _comp_compgen -U addrs set "${addrs[@]}";
    else
        _comp_compgen -U addrs ltrim_colon "${addrs[@]}";
    fi
}
_comp_compgen_kernel_modules ()
{
    local _modpath=/lib/modules/$1;
    _comp_compgen_split -- "$(command ls -RL "$_modpath" 2> /dev/null | command sed -ne 's/^\(.*\)\.k\{0,1\}o\(\.[gx]z\)\{0,1\}$/\1/p' -e 's/^\(.*\)\.ko\.zst$/\1/p')"
}
_comp_compgen_kernel_versions ()
{
    _comp_compgen_split -- "$(command ls /lib/modules)"
}
_comp_compgen_known_hosts ()
{
    local known_hosts;
    _comp_compgen_known_hosts__impl "$@" || return "$?";
    _comp_compgen -U known_hosts set "${known_hosts[@]}"
}
_comp_compgen_known_hosts__impl ()
{
    known_hosts=();
    local configfile="" flag prefix="";
    local cur suffix="" aliases="" i host ipv4="" ipv6="";
    local -a kh tmpkh=() khd=() config=();
    local OPTIND=1;
    while getopts "ac46F:p:" flag "$@"; do
        case $flag in
            a)
                aliases=set
            ;;
            c)
                suffix=':'
            ;;
            F)
                if [[ ! -n $OPTARG ]]; then
                    echo "bash_completion: $FUNCNAME: -F: an empty filename is specified" 1>&2;
                    return 2;
                fi;
                configfile=$OPTARG
            ;;
            p)
                prefix=$OPTARG
            ;;
            4)
                ipv4=set
            ;;
            6)
                ipv6=set
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    if (($# < OPTIND)); then
        echo "bash_completion: $FUNCNAME: missing mandatory argument CWORD" 1>&2;
        return 2;
    fi;
    cur=${!OPTIND};
    ((OPTIND += 1));
    if (($# >= OPTIND)); then
        echo "bash_completion: $FUNCNAME($*): unprocessed arguments:" "$(while (($# >= OPTIND)); do
    printf '%s ' ${!OPTIND}
shift;
done)" 1>&2;
        return 2;
    fi;
    [[ $cur == *@* ]] && prefix=$prefix${cur%@*}@ && cur=${cur#*@};
    kh=();
    if [[ -n $configfile ]]; then
        [[ -r $configfile && ! -d $configfile ]] && config+=("$configfile");
    else
        for i in /etc/ssh/ssh_config ~/.ssh/config ~/.ssh2/config;
        do
            [[ -r $i && ! -d $i ]] && config+=("$i");
        done;
    fi;
    if ((${#config[@]} > 0)); then
        for i in "${config[@]}";
        do
            _comp__included_ssh_config_files "$i";
        done;
    fi;
    if ((${#config[@]} > 0)); then
        if _comp_split -l tmpkh "$(_comp_awk 'sub("^[ \t]*([Gg][Ll][Oo][Bb][Aa][Ll]|[Uu][Ss][Ee][Rr])[Kk][Nn][Oo][Ww][Nn][Hh][Oo][Ss][Tt][Ss][Ff][Ii][Ll][Ee][ \t=]+", "") { print $0 }' "${config[@]}" | sort -u)"; then
            local tmpkh2 j REPLY;
            for i in "${tmpkh[@]}";
            do
                while [[ $i =~ ^([^\"]*)\"([^\"]*)\"(.*)$ ]]; do
                    i=${BASH_REMATCH[1]}${BASH_REMATCH[3]};
                    _comp_expand_tilde "${BASH_REMATCH[2]}";
                    [[ -r $REPLY ]] && kh+=("$REPLY");
                done;
                _comp_split tmpkh2 "$i" || continue;
                for j in "${tmpkh2[@]}";
                do
                    _comp_expand_tilde "$j";
                    [[ -r $REPLY ]] && kh+=("$REPLY");
                done;
            done;
        fi;
    fi;
    if [[ ! -n $configfile ]]; then
        for i in /etc/ssh/ssh_known_hosts /etc/ssh/ssh_known_hosts2 /etc/known_hosts /etc/known_hosts2 ~/.ssh/known_hosts ~/.ssh/known_hosts2;
        do
            [[ -r $i && ! -d $i ]] && kh+=("$i");
        done;
        for i in /etc/ssh2/knownhosts ~/.ssh2/hostkeys;
        do
            [[ -d $i ]] || continue;
            _comp_expand_glob tmpkh '"$i"/*.pub' && khd+=("${tmpkh[@]}");
        done;
    fi;
    if ((${#kh[@]} + ${#khd[@]} > 0)); then
        if ((${#kh[@]} > 0)); then
            for i in "${kh[@]}";
            do
                while read -ra tmpkh; do
                    ((${#tmpkh[@]} == 0)) && continue;
                    [[ ${tmpkh[0]} == [\|\#]* ]] && continue;
                    local host_list=${tmpkh[0]};
                    [[ ${tmpkh[0]} == @* ]] && host_list=${tmpkh[1]-};
                    local -a hosts;
                    if _comp_split -F , hosts "$host_list"; then
                        for host in "${hosts[@]}";
                        do
                            [[ $host == *[*?]* ]] && continue;
                            host=${host#[};
                            host=${host%]?(:+([0-9]))};
                            [[ -n $host ]] && known_hosts+=("$host");
                        done;
                    fi;
                done < "$i";
            done;
        fi;
        if ((${#khd[@]} > 0)); then
            for i in "${khd[@]}";
            do
                if [[ $i == *key_22_*.pub && -r $i ]]; then
                    host=${i/#*key_22_/};
                    host=${host/%.pub/};
                    [[ -n $host ]] && known_hosts+=("$host");
                fi;
            done;
        fi;
        ((${#known_hosts[@]})) && _comp_compgen -v known_hosts -- -W '"${known_hosts[@]}"' -P "$prefix" -S "$suffix";
    fi;
    if [[ ${#config[@]} -gt 0 && -n $aliases ]]; then
        local -a hosts;
        if _comp_split hosts "$(command sed -ne 's/^[[:blank:]]*[Hh][Oo][Ss][Tt][[:blank:]=]\{1,\}\(.*\)$/\1/p' "${config[@]}")"; then
            _comp_compgen -av known_hosts -- -P "$prefix" -S "$suffix" -W '"${hosts[@]%%[*?%]*}"' -X '@(\!*|)';
        fi;
    fi;
    if [[ -n ${BASH_COMPLETION_KNOWN_HOSTS_WITH_AVAHI-} ]] && type avahi-browse &> /dev/null; then
        local generated=$(avahi-browse -cprak 2> /dev/null | _comp_awk -F ';' '/^=/ && $5 ~ /^_(ssh|workstation)\._tcp$/ { print $7 }' | sort -u);
        _comp_compgen -av known_hosts -- -P "$prefix" -S "$suffix" -W '$generated';
    fi;
    if type ruptime &> /dev/null; then
        local generated=$(ruptime 2> /dev/null | _comp_awk '!/^ruptime:/ { print $1 }');
        _comp_compgen -av known_hosts -- -W '$generated';
    fi;
    if [[ -n ${BASH_COMPLETION_KNOWN_HOSTS_WITH_HOSTFILE-set} ]]; then
        _comp_compgen -av known_hosts -- -A hostname -P "$prefix" -S "$suffix";
    fi;
    ((${#known_hosts[@]})) || return 1;
    if [[ -n $ipv4 ]]; then
        known_hosts=("${known_hosts[@]/*:*$suffix/}");
    fi;
    if [[ -n $ipv6 ]]; then
        known_hosts=("${known_hosts[@]/+([0-9]).+([0-9]).+([0-9]).+([0-9])$suffix/}");
    fi;
    if [[ -n $ipv4 || -n $ipv6 ]]; then
        for i in "${!known_hosts[@]}";
        do
            [[ -n ${known_hosts[i]} ]] || unset -v 'known_hosts[i]';
        done;
    fi;
    ((${#known_hosts[@]})) || return 1;
    _comp_compgen -v known_hosts -c "$prefix$cur" ltrim_colon "${known_hosts[@]}"
}
_comp_compgen_ltrim_colon ()
{
    (($#)) || return 0;
    local -a _tmp;
    _tmp=("$@");
    if [[ $cur == *:* && $COMP_WORDBREAKS == *:* ]]; then
        local _colon_word=${cur%"${cur##*:}"};
        _tmp=("${_tmp[@]#"$_colon_word"}");
    fi;
    _comp_compgen_set "${_tmp[@]}"
}
_comp_compgen_mac_addresses ()
{
    local _re='\([A-Fa-f0-9]\{2\}:\)\{5\}[A-Fa-f0-9]\{2\}';
    local PATH="$PATH:/sbin:/usr/sbin";
    local -a addresses;
    _comp_compgen -v addresses split -- "$({ ip -c=never link show || ip link show || LC_ALL=C ifconfig -a; } 2> /dev/null | command sed -ne "s/.*[[:space:]]HWaddr[[:space:]]\{1,\}\($_re\)[[:space:]].*/\1/p" -ne "s/.*[[:space:]]HWaddr[[:space:]]\{1,\}\($_re\)[[:space:]]*$/\1/p" -ne "s|.*[[:space:]]\(link/\)\{0,1\}ether[[:space:]]\{1,\}\($_re\)[[:space:]].*|\2|p" -ne "s|.*[[:space:]]\(link/\)\{0,1\}ether[[:space:]]\{1,\}\($_re\)[[:space:]]*$|\2|p")";
    _comp_compgen -av addresses split -- "$({ arp -an || ip -c=never neigh show || ip neigh show; } 2> /dev/null | command sed -ne "s/.*[[:space:]]\($_re\)[[:space:]].*/\1/p" -ne "s/.*[[:space:]]\($_re\)[[:space:]]*$/\1/p")";
    _comp_compgen -av addresses split -- "$(command sed -ne "s/^[[:space:]]*\($_re\)[[:space:]].*/\1/p" /etc/ethers 2> /dev/null)";
    _comp_compgen -U addresses ltrim_colon "${addresses[@]}"
}
_comp_compgen_pci_ids ()
{
    _comp_compgen_split -- "$(PATH="$PATH:/sbin" lspci -n | _comp_awk '{print $3}')"
}
_comp_compgen_pgids ()
{
    _comp_compgen_split -- "$(command ps ax -o pgid=)"
}
_comp_compgen_pids ()
{
    _comp_compgen_split -- "$(command ps ax -o pid=)"
}
_comp_compgen_pnames ()
{
    local -a procs=();
    if [[ ${1-} == -s ]]; then
        _comp_split procs "$(command ps ax -o comm | command sed -e 1d)";
    else
        local -a psout;
        _comp_split -l psout "$({ command ps ax -o command= || command ps ax -o comm=; } 2> /dev/null)";
        local line i=-1;
        for line in "${psout[@]}";
        do
            if ((i == -1)); then
                if [[ $line =~ ^(.*[[:space:]])COMMAND([[:space:]]|$) ]]; then
                    i=${#BASH_REMATCH[1]};
                else
                    break;
                fi;
            else
                line=${line:i};
                line=${line%% *};
                [[ -n $line ]] && procs+=("$line");
            fi;
        done;
        if ((i == -1)); then
            for line in "${psout[@]}";
            do
                if [[ $line =~ ^[[(](.+)[])]$ ]]; then
                    procs+=("${BASH_REMATCH[1]}");
                else
                    line=${line%% *};
                    line=${line##@(*/|-)};
                    [[ -n $line ]] && procs+=("$line");
                fi;
            done;
        fi;
    fi;
    ((${#procs[@]})) && _comp_compgen -U procs -- -X "<defunct>" -W '"${procs[@]}"'
}
_comp_compgen_selinux_users ()
{
    _comp_compgen_split -- "$(semanage user -nl 2> /dev/null | _comp_awk '{ print $1 }')"
}
_comp_compgen_services ()
{
    local sysvdirs;
    _comp_sysvdirs || return 1;
    local services;
    _comp_expand_glob services '${sysvdirs[0]}/!($_comp_backup_glob|functions|README)';
    local _generated=$({ systemctl list-units --full --all || systemctl list-unit-files; } 2> /dev/null | _comp_awk '$1 ~ /\.service$/ { sub("\\.service$", "", $1); print $1 }');
    _comp_split -la services "$_generated";
    if [[ -x /sbin/upstart-udev-bridge ]]; then
        _comp_split -la services "$(initctl list 2> /dev/null | cut -d' ' -f1)";
    fi;
    ((${#services[@]})) || return 1;
    _comp_compgen -U services -U sysvdirs -- -W '"${services[@]#${sysvdirs[0]}/}"'
}
_comp_compgen_set ()
{
    local _append=${_comp_compgen__append-};
    local _var=${_comp_compgen__var-COMPREPLY};
    eval -- "$_var${_append:++}=(\"\$@\")";
    (($#))
}
_comp_compgen_shells ()
{
    local -a shells=();
    local _shell _rest;
    while read -r _shell _rest; do
        [[ $_shell == /* ]] && shells+=("$_shell");
    done 2> /dev/null < "${1-}"/etc/shells;
    _comp_compgen -U shells -- -W '"${shells[@]}"'
}
_comp_compgen_signals ()
{
    local -a sigs;
    _comp_compgen -v sigs -c "SIG${cur#"${1-}"}" -- -A signal && _comp_compgen -RU sigs -- -P "${1-}" -W '"${sigs[@]#SIG}"'
}
_comp_compgen_split ()
{
    local _ifs='
';
    local -a _compgen_options=();
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':lF:X:S:P:o:' _opt "$@"; do
        case $_opt in
            l)
                _ifs='
'
            ;;
            F)
                _ifs=$OPTARG
            ;;
            [XSPo])
                _compgen_options+=("-$_opt" "$OPTARG")
            ;;
            *)
                printf 'bash_completion: usage: %s [-l|-F sep] [--] str\n' "$FUNCNAME" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    if (($# != 1)); then
        printf 'bash_completion: %s: unexpected number of arguments.\n' "$FUNCNAME" 1>&2;
        printf 'usage: %s [-l|-F sep] [--] str' "$FUNCNAME" 1>&2;
        return 2;
    fi;
    local input=$1 IFS='
';
    _comp_compgen -F "$_ifs" -U input -- ${_compgen_options[@]+"${_compgen_options[@]}"} -W '$input'
}
_comp_compgen_terms ()
{
    _comp_compgen_split -- "$({ command sed -ne 's/^\([^[:space:]#|]\{2,\}\)|.*/\1/p' /etc/termcap
{ toe -a || toe; } | _comp_awk '{ print $1 }'
_comp_expand_glob dirs '/{etc,lib,usr/lib,usr/share}/terminfo/?' && find "${dirs[@]}" -type f -maxdepth 1 | _comp_awk -F / '{ print $NF }'; } 2> /dev/null)"
}
_comp_compgen_tilde ()
{
    if [[ ${cur-} == \~* && $cur != */* ]]; then
        if _comp_compgen -c "${cur#\~}" -- -P '~' -u; then
            compopt -o filenames 2> /dev/null;
            return 0;
        fi;
    fi;
    return 1
}
_comp_compgen_uids ()
{
    if type getent &> /dev/null; then
        _comp_compgen_split -- "$(getent passwd | cut -d: -f3)";
    else
        if type perl &> /dev/null; then
            _comp_compgen_split -- "$(perl -e 'while (($uid) = (getpwent)[2]) { print $uid . "\n" }')";
        else
            _comp_compgen_split -- "$(cut -d: -f3 /etc/passwd)";
        fi;
    fi
}
_comp_compgen_usage ()
{
    (($#)) || set -- -- --usage;
    local -a _lines;
    _comp_compgen_help__get_help_lines "$@" || return "$?";
    local -a options=();
    local _line _match _option _i _char;
    for _line in "${_lines[@]}";
    do
        while [[ $_line =~ \[[[:space:]]*(-[^]]+)[[:space:]]*\] ]]; do
            _match=${BASH_REMATCH[0]};
            _option=${BASH_REMATCH[1]};
            case $_option in
                -?(\[)+([a-zA-Z0-9?]))
                    for ((_i = 1; _i < ${#_option}; _i++))
                    do
                        _char=${_option:_i:1};
                        [[ $_char != '[' ]] && options+=("-$_char");
                    done
                ;;
                *)
                    _comp_compgen_help__parse "$_option"
                ;;
            esac;
            _line=${_line#*"$_match"};
        done;
    done;
    ((${#options[@]})) || return 1;
    _comp_compgen -U options -- -W '"${options[@]}"';
    return 0
}
_comp_compgen_usb_ids ()
{
    _comp_compgen_split -- "$(PATH="$PATH:/sbin" lsusb | _comp_awk '{print $6}')"
}
_comp_compgen_usergroups ()
{
    if [[ $cur == *\\\\* || $cur == *:*:* ]]; then
        return;
    else
        if [[ $cur == *\\:* ]]; then
            local tmp;
            if [[ ${1-} == -u ]]; then
                _comp_compgen -v tmp -c "${cur#*:}" allowed_groups;
            else
                _comp_compgen -v tmp -c "${cur#*:}" -- -g;
            fi;
            if ((${#tmp[@]})); then
                local _prefix=${cur%%*([^:])};
                _prefix=${_prefix//\\/};
                _comp_compgen -Rv tmp -- -P "$_prefix" -W '"${tmp[@]}"';
                _comp_compgen -U tmp set "${tmp[@]}";
            fi;
        else
            if [[ $cur == *:* ]]; then
                if [[ ${1-} == -u ]]; then
                    _comp_compgen -c "${cur#*:}" allowed_groups;
                else
                    _comp_compgen -c "${cur#*:}" -- -g;
                fi;
            else
                if [[ ${1-} == -u ]]; then
                    _comp_compgen_allowed_users;
                else
                    _comp_compgen -- -u;
                fi;
            fi;
        fi;
    fi
}
_comp_compgen_variables ()
{
    if [[ $cur =~ ^(\$(\{[!#]?)?)([A-Za-z0-9_]*)$ ]]; then
        if [[ $cur == '${'* ]]; then
            local arrs vars;
            _comp_compgen -v vars -c "${BASH_REMATCH[3]}" -- -A variable -P "${BASH_REMATCH[1]}" -S '}';
            _comp_compgen -v arrs -c "${BASH_REMATCH[3]}" -- -A arrayvar -P "${BASH_REMATCH[1]}" -S '[';
            if ((${#vars[@]} == 1 && ${#arrs[@]} != 0)); then
                compopt -o nospace;
                _comp_compgen -U vars -U arrs -R -- -W '"${arrs[@]}"';
            else
                _comp_compgen -U vars -U arrs -R -- -W '"${vars[@]}"';
            fi;
        else
            _comp_compgen -ac "${BASH_REMATCH[3]}" -- -A variable -P '$';
        fi;
        return 0;
    else
        if [[ $cur =~ ^(\$\{[#!]?)([A-Za-z0-9_]*)\[([^]]*)$ ]]; then
            local vars;
            _comp_compgen -v vars -c "${BASH_REMATCH[3]}" -- -W '"${!'"${BASH_REMATCH[2]}"'[@]}"' -P "${BASH_REMATCH[1]}${BASH_REMATCH[2]}[" -S ']}';
            if [[ ${BASH_REMATCH[3]} == [@*] ]]; then
                vars+=("${BASH_REMATCH[1]}${BASH_REMATCH[2]}[${BASH_REMATCH[3]}]}");
            fi;
            if ((${#vars[@]})); then
                _comp_compgen -U vars -c "$cur" ltrim_colon "${vars[@]}";
            else
                _comp_compgen_set;
            fi;
            return 0;
        else
            if [[ $cur =~ ^\$\{[#!]?[A-Za-z0-9_]*\[.*\]$ ]]; then
                _comp_compgen -c "$cur" ltrim_colon "$cur}";
                return 0;
            fi;
        fi;
    fi;
    return 1
}
_comp_compgen_xinetd_services ()
{
    local xinetddir=${_comp__test_xinetd_dir:-/etc/xinetd.d};
    if [[ -d $xinetddir ]]; then
        local -a svcs;
        if _comp_expand_glob svcs '$xinetddir/!($_comp_backup_glob)'; then
            _comp_compgen -U svcs -U xinetddir -- -W '"${svcs[@]#$xinetddir/}"';
        fi;
    fi
}
_comp_complete_filedir_xspec ()
{
    local cur prev words cword comp_args;
    _comp_initialize -- "$@" || return;
    _comp_compgen_filedir_xspec "$1"
}
_comp_complete_known_hosts ()
{
    local cur prev words cword comp_args;
    _comp_initialize -n : -- "$@" || return;
    local -a options=();
    [[ ${1-} == -a || ${2-} == -a ]] && options+=(-a);
    [[ ${1-} == -c || ${2-} == -c ]] && options+=(-c);
    local IFS='
';
    _comp_compgen_known_hosts ${options[@]+"${options[@]}"} -- "$cur"
}
_comp_complete_load ()
{
    local cmd=${1:-_EmptycmD_};
    _comp_load -D -- "$cmd" && return 124
}
_comp_complete_longopt ()
{
    local cur prev words cword was_split comp_args;
    _comp_initialize -s -- "$@" || return;
    case "${prev,,}" in
        --help | --usage | --version)
            return
        ;;
        --!(no-*)dir*)
            _comp_compgen -a filedir -d;
            return
        ;;
        --!(no-*)@(file|path)*)
            _comp_compgen -a filedir;
            return
        ;;
        --+([-a-z0-9_]))
            local argtype=$(LC_ALL=C $1 --help 2>&1 | command sed -ne "s|.*$prev\[\{0,1\}=[<[]\{0,1\}\([-A-Za-z0-9_]\{1,\}\).*|\1|p");
            case ${argtype,,} in
                *dir*)
                    _comp_compgen -a filedir -d;
                    return
                ;;
                *file* | *path*)
                    _comp_compgen -a filedir;
                    return
                ;;
            esac
        ;;
    esac;
    [[ -n $was_split ]] && return;
    if [[ $cur == -* ]]; then
        _comp_compgen_split -- "$(LC_ALL=C $1 --help 2>&1 | while read -r line; do
    [[ $line =~ --[A-Za-z0-9]+([-_][A-Za-z0-9]+)*=? ]] && printf '%s\n' "${BASH_REMATCH[0]}";
done)";
        [[ ${COMPREPLY-} == *= ]] && compopt -o nospace;
    else
        if [[ $1 == *@(rmdir|chroot) ]]; then
            _comp_compgen -a filedir -d;
        else
            [[ $1 == *mkdir ]] && compopt -o nospace;
            _comp_compgen -a filedir;
        fi;
    fi
}
_comp_complete_minimal ()
{
    local cur prev words cword comp_args;
    _comp_initialize -- "$@" || return;
    compopt -o bashdefault -o default
}
_comp_complete_service ()
{
    local cur prev words cword comp_args;
    _comp_initialize -- "$@" || return;
    ((cword > 2)) && return;
    if [[ $cword -eq 1 && $prev == ?(*/)service ]]; then
        _comp_compgen_services;
        [[ -e /etc/mandrake-release ]] && _comp_compgen_xinetd_services;
    else
        local sysvdirs;
        _comp_sysvdirs || return 1;
        _comp_compgen_split -l -- "$(command sed -e 'y/|/ /' -ne 's/^.*\(U\|msg_u\)sage.*{\(.*\)}.*$/\2/p' "${sysvdirs[0]}/${prev##*/}" 2> /dev/null) start stop";
    fi
}
_comp_complete_user_at_host ()
{
    local cur prev words cword comp_args;
    _comp_initialize -n : -- "$@" || return;
    if [[ $cur == *@* ]]; then
        _comp_compgen_known_hosts "$cur";
    else
        _comp_compgen -- -u -S @;
        compopt -o nospace;
    fi
}
_comp_count_args ()
{
    local has_optarg="" has_exclude="" exclude="" glob_include="";
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':a:n:i:' _opt "$@"; do
        case $_opt in
            a)
                has_optarg=$OPTARG
            ;;
            n)
                has_exclude=set exclude+=$OPTARG
            ;;
            i)
                glob_include=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    if [[ -n $has_exclude ]]; then
        local cword words;
        _comp__reassemble_words "$exclude<>&" words cword;
    fi;
    local i;
    REPLY=1;
    for ((i = 1; i < cword; i++))
    do
        if [[ -n $has_optarg && ${words[i]} == $has_optarg ]]; then
            ((i++));
        else
            if [[ ${words[i]} != -?* || -n $glob_include && ${words[i]} == $glob_include ]]; then
                ((REPLY++));
            else
                if [[ ${words[i]} == -- ]]; then
                    ((REPLY += cword - i - 1));
                    break;
                fi;
            fi;
        fi;
    done
}
_comp_delimited ()
{
    local prefix="" delimiter=$1 deduplicate=set;
    shift;
    if [[ $delimiter == -k ]]; then
        deduplicate="";
        delimiter=$1;
        shift;
    fi;
    [[ $cur == *"$delimiter"* ]] && prefix=${cur%"$delimiter"*}$delimiter;
    if [[ -n $deduplicate ]]; then
        _comp_compgen -R -- "$@";
        local -a existing;
        _comp_split -F "$delimiter" existing "$cur";
        [[ ! -n $cur || $cur == *"$delimiter" ]] || unset -v "existing[${#existing[@]}-1]";
        if ((${#COMPREPLY[@]})); then
            local x i;
            for x in ${existing+"${existing[@]}"};
            do
                for i in "${!COMPREPLY[@]}";
                do
                    if [[ $x == "${COMPREPLY[i]}" ]]; then
                        unset -v 'COMPREPLY[i]';
                        continue 2;
                    fi;
                done;
            done;
            ((${#COMPREPLY[@]})) && _comp_compgen -c "${cur##*"$delimiter"}" -- -W '"${COMPREPLY[@]}"';
        fi;
    else
        _comp_compgen -c "${cur##*"$delimiter"}" -- "$@";
    fi;
    local i;
    for i in "${!COMPREPLY[@]}";
    do
        COMPREPLY[i]="$prefix${COMPREPLY[i]}";
    done;
    [[ $delimiter != : ]] || _comp_ltrim_colon_completions "$cur"
}
_comp_deprecate_func ()
{
    if (($# != 3)); then
        printf 'bash_completion: %s: usage: %s DEPRECATION_VERSION OLD_NAME NEW_NAME\n' "$FUNCNAME" "$FUNCNAME";
        return 2;
    fi;
    if [[ $2 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
        printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$2: invalid function name '$1'" 1>&2;
        return 2;
    else
        if [[ $3 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
            printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$3: invalid function name '$2'" 1>&2;
            return 2;
        fi;
    fi;
    eval -- "$2() { $3 \"\$@\"; }"
}
_comp_deprecate_var ()
{
    if (($# != 3)); then
        printf 'bash_completion: %s: usage: %s DEPRECATION_VERSION OLD_NAME NEW_NAME\n' "$FUNCNAME" "$FUNCNAME";
        return 2;
    fi;
    if [[ $2 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
        printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$2: invalid variable name '$1'" 1>&2;
        return 2;
    else
        if [[ $3 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
            printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$3: invalid variable name '$2'" 1>&2;
            return 2;
        fi;
    fi;
    if ((BASH_VERSINFO[0] >= 5 || BASH_VERSINFO[0] == 4 && BASH_VERSINFO[1] >= 3)); then
        eval "declare -gn $2=$3";
    else
        if [[ -v $2 && ! -v $3 ]]; then
            printf -v "$3" %s "$2";
        fi;
    fi
}
_comp_dequote ()
{
    REPLY=();
    [[ $1 =~ $_comp_dequote__regex_safe_word ]] || return 1;
    eval "REPLY=($1)" 2> /dev/null
}
_comp_expand ()
{
    case ${cur-} in
        ~*/*)
            local REPLY;
            _comp_expand_tilde "$cur";
            cur=$REPLY
        ;;
        ~*)
            _comp_compgen -v COMPREPLY tilde && eval "COMPREPLY[0]=$(printf ~%q "${COMPREPLY[0]#\~}")" && return 1
        ;;
    esac;
    return 0
}
_comp_expand_glob ()
{
    if (($# != 2)); then
        printf 'bash-completion: %s: unexpected number of arguments\n' "$FUNCNAME" 1>&2;
        printf 'usage: %s ARRAY_NAME PATTERN\n' "$FUNCNAME" 1>&2;
        return 2;
    else
        if [[ $1 == @(GLOBIGNORE|GLOBSORT|_*|*[^_a-zA-Z0-9]*|[0-9]*|'') ]]; then
            printf 'bash-completion: %s: invalid array name "%s"\n' "$FUNCNAME" "$1" 1>&2;
            return 2;
        fi;
    fi;
    local _original_opts=$SHELLOPTS:$BASHOPTS;
    set +o noglob;
    shopt -s nullglob;
    shopt -u failglob dotglob;
    local GLOBIGNORE="" GLOBSORT=name;
    local LC_COLLATE=C LC_CTYPE=${LC_ALL:-${LC_CTYPE:-${LANG-}}} LC_ALL=;
    eval -- "$1=()";
    eval -- "$1=($2)";
    _comp_unlocal GLOBIGNORE;
    if [[ :$_original_opts: == *:dotglob:* ]]; then
        shopt -s dotglob;
    else
        shopt -u dotglob;
    fi;
    [[ :$_original_opts: == *:nullglob:* ]] || shopt -u nullglob;
    [[ :$_original_opts: == *:failglob:* ]] && shopt -s failglob;
    [[ :$_original_opts: == *:noglob:* ]] && set -o noglob;
    eval "((\${#$1[@]}))"
}
_comp_expand_tilde ()
{
    REPLY=$1;
    if [[ $1 == \~* ]]; then
        printf -v REPLY '~%q' "${1#\~}";
        eval "REPLY=$REPLY";
    fi
}
_comp_get_first_arg ()
{
    _comp_locate_first_arg "$@" && REPLY=${words[REPLY]}
}
_comp_get_ncpus ()
{
    local var=NPROCESSORS_ONLN;
    [[ $OSTYPE == *@(linux|msys|cygwin)* ]] && var=_$var;
    if REPLY=$(getconf $var 2> /dev/null) && ((REPLY >= 1)); then
        return 0;
    else
        REPLY=1;
        return 1;
    fi
}
_comp_get_words ()
{
    local exclude="" flag i OPTIND=1;
    local cur cword words=();
    local upargs=() upvars=() vcur="" vcword="" vprev="" vwords="";
    while getopts "c:i:n:p:w:" flag "$@"; do
        case $flag in
            [cipw])
                if [[ $OPTARG != [a-zA-Z_]*([a-zA-Z_0-9])?(\[*\]) ]]; then
                    echo "bash_completion: $FUNCNAME: -$flag: invalid variable name \`$OPTARG'" 1>&2;
                    return 1;
                fi
            ;;&
            c)
                vcur=$OPTARG
            ;;
            i)
                vcword=$OPTARG
            ;;
            n)
                exclude=$OPTARG
            ;;
            p)
                vprev=$OPTARG
            ;;
            w)
                vwords=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 1
            ;;
        esac;
    done;
    while [[ $# -ge $OPTIND ]]; do
        case ${!OPTIND} in
            cur)
                vcur=cur
            ;;
            prev)
                vprev=prev
            ;;
            cword)
                vcword=cword
            ;;
            words)
                vwords=words
            ;;
            *)
                echo "bash_completion: $FUNCNAME: \`${!OPTIND}':" "unknown argument" 1>&2;
                return 1
            ;;
        esac;
        ((OPTIND += 1));
    done;
    _comp__get_cword_at_cursor "${exclude-}" words cword cur;
    [[ -n $vcur ]] && {
        upvars+=("$vcur");
        upargs+=(-v "$vcur" "$cur")
    };
    [[ -n $vcword ]] && {
        upvars+=("$vcword");
        upargs+=(-v "$vcword" "$cword")
    };
    [[ -n $vprev ]] && {
        local value="";
        ((cword >= 1)) && value=${words[cword - 1]};
        upvars+=("$vprev");
        upargs+=(-v "$vprev" "$value")
    };
    [[ -n $vwords ]] && {
        local IFS='
';
        upvars+=("$vwords");
        upargs+=(-a"${#words[@]}" "$vwords" ${words+"${words[@]}"})
    };
    ((${#upvars[@]})) && local "${upvars[@]}" && _comp_upvars "${upargs[@]}"
}
_comp_have_command ()
{
    PATH=$PATH:/usr/sbin:/sbin:/usr/local/sbin type "$1" &> /dev/null
}
_comp_initialize ()
{
    local exclude="" opt_split="" outx="" errx="" inx="";
    local flag OPTIND=1 OPTARG="" OPTERR=0;
    while getopts "n:e:o:i:s" flag "$@"; do
        case $flag in
            n)
                exclude+=$OPTARG
            ;;
            e)
                errx=$OPTARG
            ;;
            o)
                outx=$OPTARG
            ;;
            i)
                inx=$OPTARG
            ;;
            s)
                opt_split="set";
                was_split="";
                exclude+="="
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 1
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    (($#)) && comp_args=("$@");
    COMPREPLY=();
    local redir='@(?(+([0-9])|{[a-zA-Z_]*([a-zA-Z_0-9])})@(>?([>|&])|<?([>&])|<<?([-<]))|&>?(>))';
    _comp_get_words -n "$exclude<>&" cur prev words cword;
    _comp_compgen_variables && return 1;
    if [[ $cur == $redir* || ${prev-} == $redir ]]; then
        local xspec;
        case $cur in
            2'>'*)
                xspec=${errx-}
            ;;
            *'>'*)
                xspec=${outx-}
            ;;
            *'<'*)
                xspec=${inx-}
            ;;
            *)
                case $prev in
                    2'>'*)
                        xspec=${errx-}
                    ;;
                    *'>'*)
                        xspec=${outx-}
                    ;;
                    *'<'*)
                        xspec=${inx-}
                    ;;
                esac
            ;;
        esac;
        cur=${cur##$redir};
        _comp_compgen_filedir "$xspec";
        return 1;
    fi;
    local i skip;
    for ((i = 1; i < ${#words[@]}; 1))
    do
        if [[ ${words[i]} == $redir* ]]; then
            [[ ${words[i]} == $redir ]] && skip=2 || skip=1;
            words=("${words[@]:0:i}" "${words[@]:i+skip}");
            ((i <= cword)) && ((cword -= skip));
        else
            ((i++));
        fi;
    done;
    ((cword <= 0)) && return 1;
    prev=${words[cword - 1]};
    [[ -n $opt_split ]] && _comp__split_longopt && was_split="set";
    return 0
}
_comp_load ()
{
    local flag_fallback_default="" IFS='
';
    local OPTIND=1 OPTARG="" OPTERR=0 opt;
    while getopts ':D' opt "$@"; do
        case $opt in
            D)
                flag_fallback_default=set
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    local cmd=$1 cmdname=${1##*/} dir compfile;
    local -a paths;
    [[ -n $cmdname ]] || return 1;
    local backslash=;
    if [[ $cmd == \\* ]]; then
        cmd=${cmd:1};
        $(complete -p -- "$cmd" 2> /dev/null || echo false) "\\$cmd" && return 0;
        backslash=\\;
    fi;
    local REPLY pathcmd origcmd=$cmd;
    if pathcmd=$(type -P -- "$cmd"); then
        _comp_abspath "$pathcmd";
        cmd=$REPLY;
    fi;
    local -a dirs=();
    if [[ -n ${BASH_COMPLETION_USER_DIR-} ]]; then
        _comp_split -F : paths "$BASH_COMPLETION_USER_DIR" && dirs+=("${paths[@]/%//completions}");
    else
        dirs=("${XDG_DATA_HOME:-$HOME/.local/share}/bash-completion/completions");
    fi;
    dirs+=("$_comp__base_directory/completions");
    paths=();
    [[ $cmd == /* ]] && paths+=("${cmd%/*}");
    _comp_realcommand "$cmd" && paths+=("${REPLY%/*}");
    _comp_split -aF : paths "$PATH";
    for dir in "${paths[@]%/}";
    do
        [[ $dir == ?*/@(bin|sbin) ]] && dirs+=("${dir%/*}/share/bash-completion/completions");
    done;
    _comp_split -F : paths "${XDG_DATA_DIRS:-/usr/local/share:/usr/share}" && dirs+=("${paths[@]/%//bash-completion/completions}");
    local IFS='
';
    shift;
    local i prefix compspec;
    for prefix in "" _;
    do
        for i in ${!dirs[*]};
        do
            dir=${dirs[i]};
            if [[ ! -d $dir ]]; then
                unset -v 'dirs[i]';
                continue;
            fi;
            for compfile in "$prefix$cmdname" "$prefix$cmdname.bash";
            do
                compfile="$dir/$compfile";
                if [[ -d $compfile ]]; then
                    [[ $compfile == */.?(.) ]] || echo "bash_completion: $compfile: is a directory" 1>&2;
                else
                    if [[ -e $compfile ]] && . "$compfile" "$cmd" "$@"; then
                        if compspec=$(complete -p -- "$cmd" 2> /dev/null); then
                            [[ -n $backslash ]] && eval "$compspec \"\$backslash\$cmd\"";
                            [[ $origcmd != */* ]] && ! complete -p -- "$origcmd" &> /dev/null && eval "$compspec \"\$origcmd\"";
                            return 0;
                        fi;
                        if [[ $cmdname != "$cmd" ]] && compspec=$(complete -p -- "$cmdname" 2> /dev/null); then
                            [[ $cmd == /* ]] && eval "$compspec \"\$cmd\"";
                            return 0;
                        fi;
                    fi;
                fi;
            done;
        done;
    done;
    [[ -v _comp_xspecs[$cmdname] || -v _xspecs[$cmdname] ]] && complete -F _comp_complete_filedir_xspec "$cmdname" "$backslash$cmdname" && return 0;
    if [[ -n $flag_fallback_default ]]; then
        complete -F _comp_complete_minimal -- "$origcmd" && return 0;
    fi;
    return 1
}
_comp_locate_first_arg ()
{
    local has_optarg="";
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':a:' _opt "$@"; do
        case $_opt in
            a)
                has_optarg=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    local i;
    REPLY=;
    for ((i = 1; i < cword; i++))
    do
        if [[ -n $has_optarg && ${words[i]} == $has_optarg ]]; then
            ((i++));
        else
            if [[ ${words[i]} != -?* ]]; then
                REPLY=$i;
                return 0;
            else
                if [[ ${words[i]} == -- ]]; then
                    ((i + 1 < cword)) && REPLY=$((i + 1)) && return 0;
                    break;
                fi;
            fi;
        fi;
    done;
    return 1
}
_comp_looks_like_path ()
{
    [[ ${1-} == @(*/|[.~])* ]]
}
_comp_ltrim_colon_completions ()
{
    ((${#COMPREPLY[@]})) || return 0;
    _comp_compgen -c "$1" ltrim_colon "${COMPREPLY[@]}"
}
_comp_quote ()
{
    REPLY=\'${1//\'/\'\\\'\'}\'
}
_comp_quote_compgen ()
{
    if [[ $1 == \'* ]]; then
        REPLY=${1:1};
    else
        printf -v REPLY %q "$1";
        if [[ $REPLY == \$\'*\' ]]; then
            local value=${REPLY:2:-1};
            value=${value//'%'/%%};
            printf -v REPLY "$value";
        fi;
    fi
}
_comp_readline_variable_on ()
{
    [[ $(bind -v) == *$1+([[:space:]])on* ]]
}
_comp_realcommand ()
{
    REPLY="";
    local file;
    file=$(type -P -- "$1") || return $?;
    if type -p realpath > /dev/null; then
        REPLY=$(realpath "$file");
    else
        if type -p greadlink > /dev/null; then
            REPLY=$(greadlink -f "$file");
        else
            if type -p readlink > /dev/null; then
                REPLY=$(readlink -f "$file");
            else
                _comp_abspath "$file";
            fi;
        fi;
    fi
}
_comp_root_command ()
{
    local PATH=$PATH:/sbin:/usr/sbin:/usr/local/sbin;
    local _comp_root_command=$1;
    _comp_command
}
_comp_split ()
{
    local _append="" IFS='
';
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':alF:' _opt "$@"; do
        case $_opt in
            a)
                _append=set
            ;;
            l)
                IFS='
'
            ;;
            F)
                IFS=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    if (($# != 2)); then
        printf '%s\n' "bash_completion: $FUNCNAME: unexpected number of arguments" 1>&2;
        printf '%s\n' "usage: $FUNCNAME [-al] [-F SEP] ARRAY_NAME TEXT" 1>&2;
        return 2;
    else
        if [[ $1 == @(*[^_a-zA-Z0-9]*|[0-9]*|''|_*|IFS|OPTIND|OPTARG|OPTERR) ]]; then
            printf '%s\n' "bash_completion: $FUNCNAME: invalid array name '$1'" 1>&2;
            return 2;
        fi;
    fi;
    local _original_opts=$SHELLOPTS;
    set -o noglob;
    local _old_size _new_size;
    if [[ -n $_append ]]; then
        eval "$1+=()";
        eval "_old_size=\${#$1[@]}";
        eval "$1+=(\$2)";
    else
        _old_size=0;
        eval "$1=(\$2)";
    fi;
    eval "_new_size=\${#$1[@]}";
    [[ :$_original_opts: == *:noglob:* ]] || set +o noglob;
    ((_new_size > _old_size))
}
_comp_sysvdirs ()
{
    sysvdirs=();
    [[ -d /etc/rc.d/init.d ]] && sysvdirs+=(/etc/rc.d/init.d);
    [[ -d /etc/init.d ]] && sysvdirs+=(/etc/init.d);
    [[ -f /etc/slackware-version ]] && sysvdirs=(/etc/rc.d);
    ((${#sysvdirs[@]}))
}
_comp_try_faketty ()
{
    if type unbuffer &> /dev/null; then
        unbuffer -p "$@";
    else
        if script --version 2>&1 | command grep -qF util-linux; then
            script -qaefc "$*" /dev/null;
        else
            "$@";
        fi;
    fi
}
_comp_unlocal ()
{
    if ((BASH_VERSINFO[0] >= 5)) && shopt -q localvar_unset; then
        shopt -u localvar_unset;
        unset -v "$@";
        shopt -s localvar_unset;
    else
        unset -v "$@";
    fi
}
_comp_upvars ()
{
    if ! (($#)); then
        echo "bash_completion: $FUNCNAME: usage: $FUNCNAME" "[-v varname value] | [-aN varname [value ...]] ..." 1>&2;
        return 2;
    fi;
    while (($#)); do
        case $1 in
            -a*)
                [[ -n ${1#-a} ]] || {
                    echo "bash_completion: $FUNCNAME:" "\`$1': missing number specifier" 1>&2;
                    return 1
                };
                printf %d "${1#-a}" &> /dev/null || {
                    echo bash_completion: "$FUNCNAME: \`$1': invalid number specifier" 1>&2;
                    return 1
                };
                [[ -n $2 ]] && unset -v "$2" && eval "$2"=\(\"\$"{@:3:${1#-a}}"\"\) && shift $((${1#-a} + 2)) || {
                    echo bash_completion: "$FUNCNAME: \`$1${2+ }$2': missing argument(s)" 1>&2;
                    return 1
                }
            ;;
            -v)
                [[ -n $2 ]] && unset -v "$2" && eval "$2"=\"\$3\" && shift 3 || {
                    echo "bash_completion: $FUNCNAME: $1:" "missing argument(s)" 1>&2;
                    return 1
                }
            ;;
            *)
                echo "bash_completion: $FUNCNAME: $1: invalid option" 1>&2;
                return 1
            ;;
        esac;
    done
}
_comp_userland ()
{
    local userland=$(uname -s);
    [[ $userland == @(Linux|GNU/*) ]] && userland=GNU;
    [[ $userland == "$1" ]]
}
_comp_variable_assignments ()
{
    local cur=${1-} i;
    if [[ $cur =~ ^([A-Za-z_][A-Za-z0-9_]*)=(.*)$ ]]; then
        prev=${BASH_REMATCH[1]};
        cur=${BASH_REMATCH[2]};
    else
        return 1;
    fi;
    case $prev in
        TZ)
            cur=/usr/share/zoneinfo/$cur;
            _comp_compgen_filedir;
            if ((${#COMPREPLY[@]})); then
                for i in "${!COMPREPLY[@]}";
                do
                    if [[ ${COMPREPLY[i]} == *.tab ]]; then
                        unset -v 'COMPREPLY[i]';
                        continue;
                    else
                        if [[ -d ${COMPREPLY[i]} ]]; then
                            COMPREPLY[i]+=/;
                            compopt -o nospace;
                        fi;
                    fi;
                    COMPREPLY[i]=${COMPREPLY[i]#/usr/share/zoneinfo/};
                done;
            fi
        ;;
        TERM)
            _comp_compgen_terms
        ;;
        LANG | LC_*)
            _comp_compgen_split -- "$(locale -a 2> /dev/null)"
        ;;
        LANGUAGE)
            _comp_delimited : -W '$(locale -a 2>/dev/null)'
        ;;
        *)
            _comp_compgen_variables && return 0;
            _comp_compgen -a filedir
        ;;
    esac;
    return 0
}
_comp_xfunc ()
{
    local xfunc_name=$2;
    [[ $xfunc_name == _* ]] || xfunc_name=_comp_xfunc_${1//[^a-zA-Z0-9_]/_}_$xfunc_name;
    declare -F -- "$xfunc_name" &> /dev/null || _comp_load -- "$1";
    "$xfunc_name" "${@:3}"
}
_complete_as_root ()
{
    _comp_as_root "$@"
}
_completion_loader ()
{
    _comp_complete_load "$@"
}
_configured_interfaces ()
{
    _comp_compgen_configured_interfaces "$@"
}
_count_args ()
{
    local i cword words;
    _comp__reassemble_words "${1-}" words cword;
    args=1;
    for ((i = 1; i < cword; i++))
    do
        if [[ ${words[i]} != -* && ${words[i - 1]} != ${2-} || ${words[i]} == ${3-} ]]; then
            ((args++));
        fi;
    done
}
_dvd_devices ()
{
    _comp_compgen -a dvd_devices
}
_expand ()
{
    _comp_expand "$@"
}
_filedir ()
{
    _comp_compgen -a filedir "$@"
}
_filedir_xspec ()
{
    _comp_complete_filedir_xspec "$@"
}
_fstypes ()
{
    _comp_compgen -a fstypes
}
_get_comp_words_by_ref ()
{
    _comp_get_words "$@"
}
_get_cword ()
{
    local LC_CTYPE=C;
    local cword words;
    _comp__reassemble_words "${1-}" words cword;
    if [[ -n ${2-} && -n ${2//[^0-9]/} ]]; then
        printf "%s" "${words[cword - $2]}";
    else
        if ((${#words[cword]} == 0 && COMP_POINT == ${#COMP_LINE})); then
            :;
        else
            local i;
            local cur=$COMP_LINE;
            local index=$COMP_POINT;
            for ((i = 0; i <= cword; ++i))
            do
                while [[ ${#cur} -ge ${#words[i]} && ${cur:0:${#words[i]}} != "${words[i]}" ]]; do
                    cur=${cur:1};
                    ((index > 0)) && ((index--));
                done;
                if ((i < cword)); then
                    local old_size=${#cur};
                    cur=${cur#"${words[i]}"};
                    local new_size=${#cur};
                    ((index -= old_size - new_size));
                fi;
            done;
            if [[ ${words[cword]:0:${#cur}} != "$cur" ]]; then
                printf "%s" "${words[cword]}";
            else
                printf "%s" "${cur:0:index}";
            fi;
        fi;
    fi
}
_get_first_arg ()
{
    local i;
    arg=;
    for ((i = 1; i < COMP_CWORD; i++))
    do
        if [[ ${COMP_WORDS[i]} != -* ]]; then
            arg=${COMP_WORDS[i]};
            break;
        fi;
    done
}
_get_pword ()
{
    if ((COMP_CWORD >= 1)); then
        _get_cword "${@-}" 1;
    fi
}
_gids ()
{
    _comp_compgen_gids "$@"
}
_have ()
{
    _comp_have_command "$@"
}
_init_completion ()
{
    local was_split;
    _comp_initialize "$@";
    local rc=$?;
    local flag OPTIND=1 OPTARG="" OPTERR=0;
    while getopts "n:e:o:i:s" flag "$@"; do
        case $flag in
            [neoi])

            ;;
            s)
                if [[ -n $was_split ]]; then
                    split=true;
                else
                    split=false;
                fi;
                break
            ;;
        esac;
    done;
    return "$rc"
}
_installed_modules ()
{
    _comp_compgen_inserted_kernel_modules "$@"
}
_ip_addresses ()
{
    _comp_compgen_ip_addresses "$@"
}
_kernel_versions ()
{
    _comp_compgen_kernel_versions "$@"
}
_known_hosts ()
{
    _comp_complete_known_hosts "$@"
}
_known_hosts_real ()
{
    _comp_compgen_known_hosts "$@"
}
_longopt ()
{
    _comp_complete_longopt "$@"
}
_mac_addresses ()
{
    _comp_compgen_mac_addresses "$@"
}
_minimal ()
{
    _comp_complete_minimal "$@"
}
_modules ()
{
    _comp_compgen_kernel_modules "$@"
}
_ncpus ()
{
    local REPLY;
    _comp_get_ncpus;
    printf %s "$REPLY"
}
_parse_help ()
{
    local -a args;
    if [[ $1 == - ]]; then
        args=(-);
    else
        local REPLY opt IFS='
';
        _comp_dequote "$1";
        _comp_split opt "${2:---help}";
        args=(-c "$REPLY" ${opt[@]+"${opt[@]}"});
    fi;
    local -a REPLY=();
    _comp_compgen -Rv REPLY help "${args[@]}" || return 1;
    ((${#REPLY[@]})) && printf '%s\n' "${REPLY[@]}";
    return 0
}
_parse_usage ()
{
    local -a args;
    if [[ $1 == - ]]; then
        args=(-);
    else
        local REPLY opt IFS='
';
        _comp_dequote "$1";
        _comp_split opt "${2:---usage}";
        args=(-c "$REPLY" ${opt[@]+"${opt[@]}"});
    fi;
    local -a REPLY=();
    _comp_compgen -Rv REPLY usage "${args[@]}" || return 1;
    ((${#REPLY[@]})) && printf '%s\n' "${REPLY[@]}";
    return 0
}
_pci_ids ()
{
    _comp_compgen -a pci_ids
}
_pgids ()
{
    _comp_compgen_pgids "$@"
}
_pids ()
{
    _comp_compgen_pids "$@"
}
_pnames ()
{
    _comp_compgen_pnames "$@"
}
_quote_readline_by_ref ()
{
    [[ $2 == REPLY ]] || local REPLY;
    _comp_quote_compgen "$1";
    [[ $2 == REPLY ]] || printf -v "$2" %s "$REPLY"
}
_realcommand ()
{
    local REPLY;
    _comp_realcommand "$1";
    local rc=$?;
    printf "%s\n" "$REPLY";
    return $rc
}
_rl_enabled ()
{
    _comp_readline_variable_on "$@"
}
_root_command ()
{
    _comp_root_command "$@"
}
_service ()
{
    _comp_complete_service "$@"
}
_services ()
{
    _comp_compgen_services "$@"
}
_shells ()
{
    _comp_compgen -a shells
}
_signals ()
{
    _comp_compgen_signals "$@"
}
_sysvdirs ()
{
    _comp_sysvdirs "$@"
}
_terms ()
{
    _comp_compgen -a terms
}
_tilde ()
{
    ! _comp_compgen -c "$1" tilde
}
_uids ()
{
    _comp_compgen_uids "$@"
}
_upvar ()
{
    echo "bash_completion: $FUNCNAME: deprecated function," "use _comp_upvars instead" 1>&2;
    if unset -v "$1"; then
        if (($# == 2)); then
            eval "$1"=\"\$2\";
        else
            eval "$1"=\(\"\$"{@:2}"\"\);
        fi;
    fi
}
_upvars ()
{
    _comp_upvars "$@"
}
_usb_ids ()
{
    _comp_compgen -a usb_ids
}
_user_at_host ()
{
    _comp_complete_user_at_host "$@"
}
_usergroup ()
{
    _comp_compgen_usergroups "$@"
}
_userland ()
{
    _comp_userland "$@"
}
_variables ()
{
    _comp_compgen_variables "$@"
}
_xfunc ()
{
    _comp_xfunc "$@"
}
_xinetd_services ()
{
    _comp_compgen_xinetd_services "$@"
}
command_not_found_handle ()
{
    if [ -x /usr/lib/command-not-found ]; then
        /usr/lib/command-not-found -- "$1";
        return $?;
    else
        if [ -x /usr/share/command-not-found/command-not-found ]; then
            /usr/share/command-not-found/command-not-found -- "$1";
            return $?;
        else
            printf "%s: command not found\n" "$1" 1>&2;
            return 127;
        fi;
    fi
}
dequote ()
{
    local REPLY;
    _comp_dequote "$1";
    local rc=$?;
    printf %s "$REPLY";
    return $rc
}
quote ()
{
    local quoted=${1//\'/\'\\\'\'};
    printf "'%s'" "$quoted"
}
quote_readline ()
{
    local REPLY;
    _comp_quote_compgen "$1";
    printf %s "$REPLY"
}
ossau@LAPTOP-2HK683AM:~$ declare
BASH=/usr/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:globasciiranges:globskipdots:histappend:interactive_comments:patsub_replacement:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=([0]="0")
BASH_ARGV=()
BASH_CMDS=()
BASH_COMPLETION_VERSINFO=([0]="2" [1]="16" [2]="0")
BASH_LINENO=()
BASH_LOADABLES_PATH=/usr/local/lib/bash:/usr/lib/bash:/opt/local/lib/bash:/usr/pkg/lib/bash:/opt/pkg/lib/bash:.
BASH_SOURCE=()
BASH_VERSINFO=([0]="5" [1]="3" [2]="9" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
BASH_VERSION='5.3.9(1)-release'
COLUMNS=133
COMP_FILEDIR_FALLBACK=BASH_COMPLETION_FILEDIR_FALLBACK
COMP_KNOWN_HOSTS_WITH_AVAHI=BASH_COMPLETION_KNOWN_HOSTS_WITH_AVAHI
COMP_KNOWN_HOSTS_WITH_HOSTFILE=BASH_COMPLETION_KNOWN_HOSTS_WITH_HOSTFILE
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
DIRSTACK=()
DISPLAY=:0
EUID=1000
GROUPS=()
HISTCONTROL=ignoreboth
HISTFILE=/home/ossau/.bash_history
HISTFILESIZE=2000
HISTSIZE=1000
HOME=/home/ossau
HOSTNAME=LAPTOP-2HK683AM
HOSTTYPE=x86_64
IFS=$' \t\n'
LANG=C.UTF-8
LESSCLOSE='/usr/bin/lesspipe %s %s'
LESSOPEN='| /usr/bin/lesspipe %s'
LINES=33
LOGNAME=ossau
LS_COLORS='rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:'
MACHTYPE=x86_64-pc-linux-gnu
MAILCHECK=60
NAME=LAPTOP-2HK683AM
OLDPWD=/
OPTERR=1
OPTIND=1
OSTYPE=linux-gnu
PATH='/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Program Files/WindowsApps/MicrosoftCorporationII.WindowsSubsystemForLinux_3.0.5.0_x64__8wekyb3d8bbwe:/mnt/c/Program Files/Common Files/Oracle/Java/javapath:/mnt/c/WINDOWS/system32:/mnt/c/WINDOWS:/mnt/c/WINDOWS/System32/Wbem:/mnt/c/WINDOWS/System32/WindowsPowerShell/v1.0/:/mnt/c/WINDOWS/System32/OpenSSH/:/mnt/c/Program Files/Git/cmd:/mnt/c/Program Files/WSL/:/mnt/c/Users/Ossau/AppData/Local/Microsoft/WindowsApps:/snap/bin'
PIPESTATUS=([0]="0")
PPID=605
PS1='\[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
PS2='> '
PS4='+ '
PULSE_SERVER=unix:/mnt/wslg/PulseServer
PWD=/home/ossau
SHELL=/bin/bash
SHELLOPTS=braceexpand:emacs:hashall:histexpand:history:interactive-comments:monitor
SHLVL=2
TERM=xterm-256color
UID=1000
USER=ossau
WAYLAND_DISPLAY=wayland-0
WSL2_GUI_APPS_ENABLED=1
WSLENV=
WSL_DISTRO_NAME=Ubuntu
WSL_INTEROP=/run/WSL/604_interop
XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
XDG_RUNTIME_DIR=/run/user/1000
_=declare
__git_CRLF=$'\r\n'
__git_ESC=$'\E'
__git_LF=$'\n'
__git_SOH=$'\001'
__git_STX=$'\002'
__git_printf_supports_v=yes
_backup_glob='@(#*#|*@(~|.@(bak|orig|rej|swp|@(dpkg|ucf)-*|rpm@(orig|new|save))))'
_comp__base_directory=/usr/share/bash-completion
_comp_backup_glob='@(#*#|*@(~|.@(bak|orig|rej|swp|@(dpkg|ucf)-*|rpm@(orig|new|save))))'
_comp_dequote__regex_safe_word='^([^\'\''"$`;&|<>()!]|\\.|'\''[^'\'']*'\''|\$?"([^\"$`!]|\$([_a-zA-Z][_a-zA-Z0-9]*|[-*@#?$!0-9_])|\$\{[!#]?([_a-zA-Z][_a-zA-Z0-9]*(\[([0-9]+|[*@])\])?|[-*@#?$!0-9_])\}|\\.)*"|\$'\''([^\'\'']|\\.)*'\''|\$([_a-zA-Z][_a-zA-Z0-9]*|[-*@#?$!0-9_])|\$\{[!#]?([_a-zA-Z][_a-zA-Z0-9]*(\[([0-9]+|[*@])\])?|[-*@#?$!0-9_])\})*$'
_comp_xspecs=([tex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [freeamp]="!*.@(mp3|og[ag]|pls|m3u)" [gqmpeg]="!*.@(mp3|og[ag]|pls|m3u)" [texi2html]="!*.texi*" [hbpp]="!*.@([Pp][Rr][Gg]|[Cc][Ll][Pp])" [lowriter]="!*.@(sxw|stw|sxg|sgl|doc?([mx])|dot?([mx])|rtf|txt|htm|html|?(f)odt|ott|odm|pdf)" [rpm2cpio]="!*.[rs]pm" [localc]="!*.@(sxc|stc|xls?([bmx])|xlw|xlt?([mx])|[ct]sv|?(f)ods|ots)" [hbrun]="!*.[Hh][Rr][Bb]" [vi]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [latex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [view]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [madplay]="!*.mp3" [compress]="*.Z" [pdfjadetex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [pbunzip2]="!*.?(t)bz?(2)" [lrunzip]="!*.lrz" [gunzip]="!*.@(Z|[gGd]z|t[ag]z)" [oowriter]="!*.@(sxw|stw|sxg|sgl|doc?([mx])|dot?([mx])|rtf|txt|htm|html|?(f)odt|ott|odm|pdf)" [epiphany]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [acroread]="!*.[pf]df" [znew]="*.Z" [kwrite]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [xemacs]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [gview]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [lzfgrep]="!*.@(tlz|lzma)" [lzless]="!*.@(tlz|lzma)" [cdiff]="!*.@(dif?(f)|?(d)patch)?(.@([gx]z|bz2|lzma))" [zipinfo]="!*.@(zip|[aegjkswx]ar|exe|pk3|wsz|zargo|xpi|s[tx][cdiw]|sx[gm]|o[dt][tspgfc]|od[bm]|oxt|?(o)xps|epub|cbz|apk|aab|ipa|do[ct][xm]|p[op]t[mx]|xl[st][xm]|pyz|vsix|whl|[Ff][Cc][Ss]td)" [pdflatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [portecle]="!@(*.@(ks|jks|jceks|p12|pfx|bks|ubr|gkr|cer|crt|cert|p7b|pkipath|pem|p10|csr|crl)|cacerts)" [modplugplay]="!*.@(669|abc|am[fs]|d[bs]m|dmf|far|it|mdl|m[eo]d|mid?(i)|mt[2m]|oct|okt?(a)|p[st]m|s[3t]m|ult|umx|wav|xm)" [lokalize]="!*.po" [lbzcat]="!*.?(t)bz?(2)" [qiv]="!*.@(gif|jp?(e)g|tif?(f)|png|p[bgp]m|bmp|x[bp]m|rle|rgb|pcx|fits|pm|svg)" [totem]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|opus|OPUS|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM|iso|ISO)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [ps2pdfwr]="!*.@(?(e)ps|pdf)" [dvitype]="!*.dvi" [unpigz]="!*.@(Z|[gGdz]z|t[ag]z)" [mozilla]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [pdfunite]="!*.pdf" [gpdf]="!*.[pf]df" [texi2dvi]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [bunzip2]="!*.?(t)bz?(2)" [zathura]="!*.@(cb[rz7t]|djv?(u)|?(e)ps|pdf)" [kaffeine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|opus|OPUS|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM|iso|ISO)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [mpg123]="!*.mp3" [lzegrep]="!*.@(tlz|lzma)" [xv]="!*.@(gif|jp?(e)g?(2)|j2[ck]|jp[2f]|tif?(f)|png|p[bgpn]m|webp|bmp|x[bp]m|rle|rgb|pcx|fits|pm|?(e)ps)" [xdvi]="!*.@(dvi|DVI)?(.@(gz|Z|bz2))" [xfig]="!*.fig" [xpdf]="!*.@(pdf|fdf)?(.@(gz|Z|xz|lzma|bz2))" [oobase]="!*.odb" [xelatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [gharbour]="!*.@([Pp][Rr][Gg]|[Cc][Ll][Pp])" [bzcat]="!*.?(t)bz?(2)" [dragon]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|opus|OPUS|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM|iso|ISO)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [xanim]="!*.@(mpg|mpeg|avi|mov|qt)" [lualatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [rgview]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [rvim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [xetex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [lomath]="!*.@(sxm|smf|mml|odf)" [zcat]="!*.@(Z|[gGd]z|t[ag]z)" [lynx]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [uncompress]="!*.Z" [xzcat]="!*.@(?(t)xz|tlz|lzma)" [vim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [loimpress]="!*.@(sxi|sti|pps?(x)|ppt?([mx])|pot?([mx])|?(f)odp|otp)" [dvipdf]="!*.dvi" [mpg321]="!*.mp3" [jadetex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [lobase]="!*.odb" [epdfview]="!*.pdf" [ps2pdf14]="!*.@(?(e)ps|pdf)" [ps2pdf13]="!*.@(?(e)ps|pdf)" [ps2pdf12]="!*.@(?(e)ps|pdf)" [poedit]="!*.po" [luatex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [kbabel]="!*.po" [bzme]="!*.@(zip|z|gz|tgz)" [dviselect]="!*.dvi" [realplay]="!*.@(rm?(j)|ra?(m)|smi?(l))" [kdvi]="!*.@(dvi|DVI)?(.@(gz|Z|bz2))" [elinks]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [kghostview]="!*.@(@(?(e)ps|?(E)PS|pdf|PDF)?(.gz|.GZ|.bz2|.BZ2|.Z))" [gtranslator]="!*.po" [unzip]="!*.@(zip|[aegjkswx]ar|exe|pk3|wsz|zargo|xpi|s[tx][cdiw]|sx[gm]|o[dt][tspgfc]|od[bm]|oxt|?(o)xps|epub|cbz|apk|aab|ipa|do[ct][xm]|p[op]t[mx]|xl[st][xm]|pyz|vsix|whl|[Ff][Cc][Ss]td)" [ggv]="!*.@(@(?(e)ps|?(E)PS|pdf|PDF)?(.gz|.GZ|.bz2|.BZ2|.Z))" [oomath]="!*.@(sxm|smf|mml|odf)" [dvipdfmx]="!*.dvi" [makeinfo]="!*.texi*" [okular]="!*.@(okular|@(?(e|x)ps|?(E|X)PS|[pf]df|[PF]DF|dvi|DVI|cb[rz]|CB[RZ]|djv?(u)|DJV?(U)|dvi|DVI|gif|jp?(e)g|miff|tif?(f)|pn[gm]|p[bgp]m|bmp|xpm|ico|xwd|tga|pcx|GIF|JP?(E)G|MIFF|TIF?(F)|PN[GM]|P[BGP]M|BMP|XPM|ICO|XWD|TGA|PCX|epub|EPUB|odt|ODT|fb?(2)|FB?(2)|mobi|MOBI|g3|G3|chm|CHM|md|markdown)?(.?(gz|GZ|bz2|BZ2|xz|XZ)))" [cacaxine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [sxemacs]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [aviplay]="!*.@(avi|asf|wmv)" [rgvim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [dvipdfm]="!*.dvi" [ly2dvi]="!*.ly" [oodraw]="!*.@(sxd|std|sda|sdd|?(f)odg|otg)" [kpdf]="!*.@(?(e)ps|pdf)" [bibtex]="!*.aux" [netscape]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [emacs]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [rview]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [galeon]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [dillo]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [fbxine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [oocalc]="!*.@(sxc|stc|xls?([bmx])|xlw|xlt?([mx])|[ct]sv|?(f)ods|ots)" [harbour]="!*.@([Pp][Rr][Gg]|[Cc][Ll][Pp])" [lodraw]="!*.@(sxd|std|sda|sdd|?(f)odg|otg)" [dvips]="!*.dvi" [ps2pdf]="!*.@(?(e)ps|pdf)" [kate]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [kid3-qt]="!*.@(mp[234c]|og[ag]|@(fl|a)ac|m4[abp]|spx|tta|w?(a)v|wma|aif?(f)|asf|ape)" [pdftex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [gvim]="*.@([ao]|so|so.!(conf|*/*)|[rs]pm|gif|jp?(e)g|mp3|mp?(e)g|avi|asf|ogg|class)" [timidity]="!*.@(mid?(i)|rmi|rcp|[gr]36|g18|mod|xm|it|x3m|s[3t]m|kar)" [ogg123]="!*.@(og[ag]|m3u|flac|spx)" [lzgrep]="!*.@(tlz|lzma)" [ee]="!*.@(gif|jp?(e)g|miff|tif?(f)|pn[gm]|p[bgp]m|bmp|xpm|ico|xwd|tga|pcx)" [unlzma]="!*.@(tlz|lzma)" [lbunzip2]="!*.?(t)bz?(2)" [ooimpress]="!*.@(sxi|sti|pps?(x)|ppt?([mx])|pot?([mx])|?(f)odp|otp)" [xine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [amaya]="!*.@(?([xX]|[sS])[hH][tT][mM]?([lL]))" [gv]="!*.@(@(?(e)ps|?(E)PS|pdf|PDF)?(.gz|.GZ|.bz2|.BZ2|.Z))" [kid3]="!*.@(mp[234c]|og[ag]|@(fl|a)ac|m4[abp]|spx|tta|w?(a)v|wma|aif?(f)|asf|ape)" [lilypond]="!*.ly" [modplug123]="!*.@(669|abc|am[fs]|d[bs]m|dmf|far|it|mdl|m[eo]d|mid?(i)|mt[2m]|oct|okt?(a)|p[st]m|s[3t]m|ult|umx|wav|xm)" [pbzcat]="!*.?(t)bz?(2)" [unxz]="!*.@(?(t)xz|tlz|lzma)" [playmidi]="!*.@(mid?(i)|cmf)" [lzcat]="!*.@(tlz|lzma)" [slitex]="!*.@(?(la)tex|texi|dtx|ins|ltx|dbj)" [aaxine]="!*@(.@(mp?(e)g|MP?(E)G|wm[av]|WM[AV]|avi|AVI|asf|vob|VOB|bin|dat|divx|DIVX|vcd|ps|pes|fli|flv|FLV|fxm|FXM|viv|rm|ram|yuv|mov|MOV|qt|QT|web[am]|WEB[AM]|mp[234]|MP[234]|m?(p)4[av]|M?(P)4[AV]|mkv|MKV|og[agmvx]|OG[AGMVX]|t[ps]|T[PS]|m2t?(s)|M2T?(S)|mts|MTS|wav|WAV|flac|FLAC|asx|ASX|mng|MNG|srt|m[eo]d|M[EO]D|s[3t]m|S[3T]M|it|IT|xm|XM)|+([0-9]).@(vdr|VDR))?(.@(crdownload|part))" [advi]="!*.dvi" [lzmore]="!*.@(tlz|lzma)" )
__expand_tilde_by_ref ()
{
    [[ -n ${1+set} ]] || return 0;
    [[ $1 == REPLY ]] || local REPLY;
    _comp_expand_tilde "${!1-}";
    [[ $1 == REPLY ]] || printf -v "$1" "$REPLY"
}
__git_eread ()
{
    test -r "$1" && IFS=$__git_CRLF read -r "$2" < "$1"
}
__git_ps1 ()
{
    local exit="$?";
    local pcmode=no;
    local detached=no;
    local ps1pc_start='\u@\h:\w ';
    local ps1pc_end='\$ ';
    local printf_format=' (%s)';
    case "$#" in
        2 | 3)
            pcmode=yes;
            ps1pc_start="$1";
            ps1pc_end="$2";
            printf_format="${3:-$printf_format}";
            PS1="$ps1pc_start$ps1pc_end"
        ;;
        0 | 1)
            printf_format="${1:-$printf_format}"
        ;;
        *)
            return "$exit"
        ;;
    esac;
    local ps1_expanded=yes;
    [ -z "${ZSH_VERSION-}" ] || eval '[[ -o PROMPT_SUBST ]]' || ps1_expanded=no;
    [ -z "${BASH_VERSION-}" ] || shopt -q promptvars || ps1_expanded=no;
    local repo_info rev_parse_exit_code;
    repo_info="$(git rev-parse --git-dir --is-inside-git-dir --is-bare-repository --is-inside-work-tree --show-ref-format --short HEAD 2> /dev/null)";
    rev_parse_exit_code="$?";
    if [ -z "$repo_info" ]; then
        return "$exit";
    fi;
    local LF="$__git_LF";
    local short_sha="";
    if [ "$rev_parse_exit_code" = "0" ]; then
        short_sha="${repo_info##*$LF}";
        repo_info="${repo_info%$LF*}";
    fi;
    local ref_format="${repo_info##*$LF}";
    repo_info="${repo_info%$LF*}";
    local inside_worktree="${repo_info##*$LF}";
    repo_info="${repo_info%$LF*}";
    local bare_repo="${repo_info##*$LF}";
    repo_info="${repo_info%$LF*}";
    local inside_gitdir="${repo_info##*$LF}";
    local g="${repo_info%$LF*}";
    if [ "true" = "$inside_worktree" ] && [ -n "${GIT_PS1_HIDE_IF_PWD_IGNORED-}" ] && [ "$(git config --bool bash.hideIfPwdIgnored)" != "false" ] && git check-ignore -q .; then
        return "$exit";
    fi;
    local sparse="";
    if [ -z "${GIT_PS1_COMPRESSSPARSESTATE-}" ] && [ -z "${GIT_PS1_OMITSPARSESTATE-}" ] && [ "$(git config --bool core.sparseCheckout)" = "true" ]; then
        sparse="|SPARSE";
    fi;
    local r="";
    local b="";
    local step="";
    local total="";
    if [ -d "$g/rebase-merge" ]; then
        __git_eread "$g/rebase-merge/head-name" b;
        __git_eread "$g/rebase-merge/msgnum" step;
        __git_eread "$g/rebase-merge/end" total;
        r="|REBASE";
    else
        if [ -d "$g/rebase-apply" ]; then
            __git_eread "$g/rebase-apply/next" step;
            __git_eread "$g/rebase-apply/last" total;
            if [ -f "$g/rebase-apply/rebasing" ]; then
                __git_eread "$g/rebase-apply/head-name" b;
                r="|REBASE";
            else
                if [ -f "$g/rebase-apply/applying" ]; then
                    r="|AM";
                else
                    r="|AM/REBASE";
                fi;
            fi;
        else
            if [ -f "$g/MERGE_HEAD" ]; then
                r="|MERGING";
            else
                if __git_sequencer_status; then
                    :;
                else
                    if [ -f "$g/BISECT_LOG" ]; then
                        r="|BISECTING";
                    fi;
                fi;
            fi;
        fi;
        if [ -n "$b" ]; then
            :;
        else
            if [ -h "$g/HEAD" ]; then
                b="$(git symbolic-ref HEAD 2> /dev/null)";
            else
                local head="";
                case "$ref_format" in
                    files)
                        if ! __git_eread "$g/HEAD" head; then
                            return "$exit";
                        fi;
                        case $head in
                            "ref: "*)
                                head="${head#ref: }"
                            ;;
                            *)
                                head=""
                            ;;
                        esac
                    ;;
                    *)
                        head="$(git symbolic-ref HEAD 2> /dev/null)"
                    ;;
                esac;
                if test -z "$head"; then
                    detached=yes;
                    b="$(case "${GIT_PS1_DESCRIBE_STYLE-}" in contains)
        git describe --contains HEAD
    ;;
    branch)
        git describe --contains --all HEAD
    ;;
    tag)
        git describe --tags HEAD
    ;;
    describe)
        git describe HEAD
    ;;
    * | default)
        git describe --tags --exact-match HEAD
    ;;
esac 2> /dev/null)" || b="$short_sha...";
                    b="($b)";
                else
                    b="$head";
                fi;
            fi;
        fi;
    fi;
    if [ -n "$step" ] && [ -n "$total" ]; then
        r="$r $step/$total";
    fi;
    local conflict="";
    if [ "${GIT_PS1_SHOWCONFLICTSTATE-}" = "yes" ] && [ "$(git ls-files --unmerged 2> /dev/null)" ]; then
        conflict="|CONFLICT";
    fi;
    local w="";
    local i="";
    local s="";
    local u="";
    local h="";
    local c="";
    local p="";
    local upstream="";
    if [ "true" = "$inside_gitdir" ]; then
        if [ "true" = "$bare_repo" ]; then
            c="BARE:";
        else
            b="GIT_DIR!";
        fi;
    else
        if [ "true" = "$inside_worktree" ]; then
            if [ -n "${GIT_PS1_SHOWDIRTYSTATE-}" ] && [ "$(git config --bool bash.showDirtyState)" != "false" ]; then
                git diff --no-ext-diff --quiet || w="*";
                git diff --no-ext-diff --cached --quiet || i="+";
                if [ -z "$short_sha" ] && [ -z "$i" ]; then
                    i="#";
                fi;
            fi;
            if [ -n "${GIT_PS1_SHOWSTASHSTATE-}" ] && git rev-parse --verify --quiet refs/stash > /dev/null; then
                s="$";
            fi;
            if [ -n "${GIT_PS1_SHOWUNTRACKEDFILES-}" ] && [ "$(git config --bool bash.showUntrackedFiles)" != "false" ] && git ls-files --others --exclude-standard --directory --no-empty-directory --error-unmatch -- ':/*' > /dev/null 2> /dev/null; then
                u="%${ZSH_VERSION+%}";
            fi;
            if [ -n "${GIT_PS1_COMPRESSSPARSESTATE-}" ] && [ "$(git config --bool core.sparseCheckout)" = "true" ]; then
                h="?";
            fi;
            if [ -n "${GIT_PS1_SHOWUPSTREAM-}" ]; then
                __git_ps1_show_upstream;
            fi;
        fi;
    fi;
    local z="${GIT_PS1_STATESEPARATOR- }";
    b=${b##refs/heads/};
    if [ "$pcmode" = yes ] && [ "$ps1_expanded" = yes ]; then
        __git_ps1_branch_name=$b;
        b="\${__git_ps1_branch_name}";
    fi;
    if [ -n "${GIT_PS1_SHOWCOLORHINTS-}" ]; then
        __git_ps1_colorize_gitstring;
    fi;
    local f="$h$w$i$s$u$p";
    local gitstring="$c$b${f:+$z$f}${sparse}$r${upstream}${conflict}";
    if [ "$pcmode" = yes ]; then
        if [ "${__git_printf_supports_v-}" != yes ]; then
            gitstring=$(printf -- "$printf_format" "$gitstring");
        else
            printf -v gitstring -- "$printf_format" "$gitstring";
        fi;
        PS1="$ps1pc_start$gitstring$ps1pc_end";
    else
        printf -- "$printf_format" "$gitstring";
    fi;
    return "$exit"
}
__git_ps1_colorize_gitstring ()
{
    if [ -n "${ZSH_VERSION-}" ]; then
        local c_red='%F{red}';
        local c_green='%F{green}';
        local c_lblue='%F{blue}';
        local c_clear='%f';
    else
        local c_pre="${GIT_PS1_COLOR_PRE-$__git_SOH}${__git_ESC}[";
        local c_post="m${GIT_PS1_COLOR_POST-$__git_STX}";
        local c_red="${c_pre}31${c_post}";
        local c_green="${c_pre}32${c_post}";
        local c_lblue="${c_pre}1;34${c_post}";
        local c_clear="${c_pre}0${c_post}";
    fi;
    local bad_color="$c_red";
    local ok_color="$c_green";
    local flags_color="$c_lblue";
    local branch_color="";
    if [ "$detached" = no ]; then
        branch_color="$ok_color";
    else
        branch_color="$bad_color";
    fi;
    if [ -n "$c" ]; then
        c="$branch_color$c$c_clear";
    fi;
    b="$branch_color$b$c_clear";
    if [ -n "$w" ]; then
        w="$bad_color$w$c_clear";
    fi;
    if [ -n "$i" ]; then
        i="$ok_color$i$c_clear";
    fi;
    if [ -n "$s" ]; then
        s="$flags_color$s$c_clear";
    fi;
    if [ -n "$u" ]; then
        u="$bad_color$u$c_clear";
    fi
}
__git_ps1_show_upstream ()
{
    local key value;
    local svn_remotes="" svn_url_pattern="" count n;
    local upstream_type=git legacy="" verbose="" name="";
    local LF="$__git_LF";
    local output="$(git config -z --get-regexp '^(svn-remote\..*\.url|bash\.showupstream)$' 2> /dev/null | tr '\0\n' '\n ')";
    while read -r key value; do
        case "$key" in
            bash.showupstream)
                GIT_PS1_SHOWUPSTREAM="$value";
                if [ -z "${GIT_PS1_SHOWUPSTREAM}" ]; then
                    p="";
                    return;
                fi
            ;;
            svn-remote.*.url)
                svn_remotes=${svn_remotes}${value}${LF};
                svn_url_pattern="$svn_url_pattern\\|$value";
                upstream_type=svn+git
            ;;
        esac;
    done <<-OUTPUT
$output
OUTPUT

    local option
    for option in ${GIT_PS1_SHOWUPSTREAM-};
    do
        case "$option" in
            git | svn)
                upstream_type="$option"
            ;;
            verbose)
                verbose=1
            ;;
            legacy)
                legacy=1
            ;;
            name)
                name=1
            ;;
        esac;
    done;
    case "$upstream_type" in
        git)
            upstream_type="@{upstream}"
        ;;
        svn*)
            local svn_upstream="$(git log --first-parent -1 --grep="^git-svn-id: \(${svn_url_pattern#??}\)" 2> /dev/null)";
            if [ -n "$svn_upstream" ]; then
                svn_upstream=${svn_upstream##*$LF};
                svn_upstream=${svn_upstream#*: };
                svn_upstream=${svn_upstream%@*};
                case ${LF}${svn_remotes} in
                    *"${LF}${svn_upstream}${LF}"*)
                        upstream_type=${GIT_SVN_ID:-git-svn}
                    ;;
                    *)
                        upstream_type=${svn_upstream#/}
                    ;;
                esac;
            else
                if [ "svn+git" = "$upstream_type" ]; then
                    upstream_type="@{upstream}";
                fi;
            fi
        ;;
    esac;
    if [ -z "$legacy" ]; then
        count="$(git rev-list --count --left-right "$upstream_type"...HEAD 2> /dev/null)";
    else
        local commits;
        if commits="$(git rev-list --left-right "$upstream_type"...HEAD 2> /dev/null)"; then
            local commit behind=0 ahead=0;
            for commit in $commits;
            do
                case "$commit" in
                    "<"*)
                        behind=$((behind+1))
                    ;;
                    *)
                        ahead=$((ahead+1))
                    ;;
                esac;
            done;
            count="$behind      $ahead";
        else
            count="";
        fi;
    fi;
    if [ -z "$verbose" ]; then
        case "$count" in
            "")
                p=""
            ;;
            "0  0")
                p="="
            ;;
            "0  "*)
                p=">"
            ;;
            *"  0")
                p="<"
            ;;
            *)
                p="<>"
            ;;
        esac;
    else
        case "$count" in
            "")
                upstream=""
            ;;
            "0  0")
                upstream="|u="
            ;;
            "0  "*)
                upstream="|u+${count#0  }"
            ;;
            *"  0")
                upstream="|u-${count%   0}"
            ;;
            *)
                upstream="|u+${count#*  }-${count%      *}"
            ;;
        esac;
        if [ -n "$count" ] && [ -n "$name" ]; then
            __git_ps1_upstream_name=$(git rev-parse --abbrev-ref "$upstream_type" 2> /dev/null);
            if [ "$pcmode" = yes ] && [ "$ps1_expanded" = yes ]; then
                upstream="$upstream \${__git_ps1_upstream_name}";
            else
                upstream="$upstream ${__git_ps1_upstream_name}";
                unset __git_ps1_upstream_name;
            fi;
        fi;
    fi
}
__git_sequencer_status ()
{
    local todo;
    if test -f "$g/CHERRY_PICK_HEAD"; then
        r="|CHERRY-PICKING";
        return 0;
    else
        if test -f "$g/REVERT_HEAD"; then
            r="|REVERTING";
            return 0;
        else
            if __git_eread "$g/sequencer/todo" todo; then
                case "$todo" in
                    p[\ \       ] | pick[\ \    ]*)
                        r="|CHERRY-PICKING";
                        return 0
                    ;;
                    revert[\ \  ]*)
                        r="|REVERTING";
                        return 0
                    ;;
                esac;
            fi;
        fi;
    fi;
    return 1
}
__load_completion ()
{
    _comp_load "$@"
}
__ltrim_colon_completions ()
{
    _comp_ltrim_colon_completions "$@"
}
__parse_options ()
{
    local -a _options=();
    _comp_compgen_help__parse "$1";
    printf '%s\n' "${_options[@]}"
}
_allowed_groups ()
{
    _comp_compgen -c "${1:-$cur}" allowed_groups
}
_allowed_users ()
{
    _comp_compgen -c "${1:-$cur}" allowed_users
}
_available_interfaces ()
{
    _comp_compgen_available_interfaces "$@"
}
_bashcomp_try_faketty ()
{
    _comp_try_faketty "$@"
}
_cd ()
{
    declare -F _comp_cmd_cd &> /dev/null || __load_completion cd;
    _comp_cmd_cd "$@"
}
_cd_devices ()
{
    _comp_compgen -a cd_devices
}
_command ()
{
    _comp_command "$@"
}
_command_offset ()
{
    local words;
    unset -v words;
    _comp_command_offset "$@"
}
_comp__find_original_word ()
{
    REPLY=$1;
    [[ -v cword && -v words ]] || return 0;
    local reassembled_offset=$1 i=0 j;
    for ((j = 0; j < reassembled_offset; j++))
    do
        local word=${words[j]};
        while [[ -n $word && i -lt ${#COMP_WORDS[@]} && $word == *"${COMP_WORDS[i]}"* ]]; do
            word=${word#*"${COMP_WORDS[i++]}"};
        done;
    done;
    REPLY=$i
}
_comp__get_cword_at_cursor ()
{
    local cword words=();
    _comp__reassemble_words "$1" words cword;
    local i cur="" index=$COMP_POINT lead=${COMP_LINE:0:COMP_POINT};
    if [[ $index -gt 0 && ( -n $lead && -n ${lead//[[:space:]]/} ) ]]; then
        cur=$COMP_LINE;
        for ((i = 0; i <= cword; ++i))
        do
            while [[ ${#cur} -ge ${#words[i]} && ${cur:0:${#words[i]}} != "${words[i]-}" ]]; do
                cur=${cur:1};
                ((index > 0)) && ((index--));
            done;
            if ((i < cword)); then
                local old_size=${#cur};
                cur=${cur#"${words[i]}"};
                local new_size=${#cur};
                ((index -= old_size - new_size));
            fi;
        done;
        [[ -n $cur && ! -n ${cur//[[:space:]]/} ]] && cur=;
        ((index < 0)) && index=0;
    fi;
    local IFS='
';
    local "$2" "$3" "$4" && _comp_upvars -a"${#words[@]}" "$2" ${words[@]+"${words[@]}"} -v "$3" "$cword" -v "$4" "${cur:0:index}"
}
_comp__included_ssh_config_files ()
{
    (($# < 1)) && echo "bash_completion: $FUNCNAME: missing mandatory argument CONFIG" 1>&2;
    local configfile i files f REPLY;
    configfile=$1;
    local relative_include_base;
    if [[ $configfile == /etc/ssh* ]]; then
        relative_include_base="/etc/ssh";
    else
        relative_include_base="$HOME/.ssh";
    fi;
    local depth=1;
    local -a included;
    local -a include_files;
    included=("$configfile");
    local max_depth=16;
    while ((${#included[@]} > 0 && depth++ < max_depth)); do
        _comp_split include_files "$(command sed -ne 's/^[[:blank:]]*[Ii][Nn][Cc][Ll][Uu][Dd][Ee][[:blank:]]\(.*\)$/\1/p' "${included[@]}")" || return;
        included=();
        for i in "${include_files[@]}";
        do
            if [[ $i != [~/]* ]]; then
                i="${relative_include_base}/${i}";
            fi;
            _comp_expand_tilde "$i";
            if _comp_expand_glob files '$REPLY'; then
                for f in "${files[@]}";
                do
                    if [[ -r $f && ! -d $f ]]; then
                        config+=("$f");
                        included+=("$f");
                    fi;
                done;
            fi;
        done;
    done
}
_comp__reassemble_words ()
{
    local exclude="" i j line ref;
    if [[ -n $1 ]]; then
        exclude="[${1//[^$COMP_WORDBREAKS]/}]";
    fi;
    printf -v "$3" %s "$COMP_CWORD";
    if [[ -n $exclude ]]; then
        line=$COMP_LINE;
        for ((i = 0, j = 0; i < ${#COMP_WORDS[@]}; i++, j++))
        do
            while [[ $i -gt 0 && ${COMP_WORDS[i]} == +($exclude) ]]; do
                [[ $line != [[:blank:]]* ]] && ((j >= 2)) && ((j--));
                ref="$2[$j]";
                printf -v "$ref" %s "${!ref-}${COMP_WORDS[i]}";
                ((i == COMP_CWORD)) && printf -v "$3" %s "$j";
                line=${line#*"${COMP_WORDS[i]}"};
                if ((i < ${#COMP_WORDS[@]} - 1)); then
                    ((i++));
                else
                    break 2;
                fi;
                [[ $line == [[:blank:]]* ]] && ((j++));
            done;
            ref="$2[$j]";
            printf -v "$ref" %s "${!ref-}${COMP_WORDS[i]}";
            line=${line#*"${COMP_WORDS[i]}"};
            ((i == COMP_CWORD)) && printf -v "$3" %s "$j";
        done;
        ((i == COMP_CWORD)) && printf -v "$3" %s "$j";
    else
        for i in "${!COMP_WORDS[@]}";
        do
            printf -v "$2[i]" %s "${COMP_WORDS[i]}";
        done;
    fi
}
_comp__split_longopt ()
{
    if [[ $cur == --?*=* ]]; then
        prev=${cur%%?(\\)=*};
        cur=${cur#*=};
        return 0;
    fi;
    return 1
}
_comp_abspath ()
{
    REPLY=$1;
    [[ $REPLY == /* ]] || REPLY=$PWD/$REPLY;
    REPLY=${REPLY//+(\/)/\/};
    while true; do
        case $REPLY in
            */./*)
                REPLY=${REPLY//\/.\//\/}
            ;;
            */.)
                REPLY=${REPLY%/.}
            ;;
            /..?(/*))
                REPLY=${REPLY#/..}
            ;;
            */+([^/])/../*)
                REPLY=${REPLY/\/+([^\/])\/..\//\/}
            ;;
            */+([^/])/..)
                REPLY=${REPLY%/+([^/])/..}
            ;;
            *)
                break
            ;;
        esac;
    done;
    [[ -n $REPLY ]] || REPLY=/
}
_comp_as_root ()
{
    [[ $EUID -eq 0 || -n ${_comp_root_command-} ]]
}
_comp_awk ()
{
    command awk "$@"
}
_comp_command ()
{
    local words;
    unset -v words;
    local offset i;
    offset=1;
    for ((i = 1; i <= COMP_CWORD; i++))
    do
        if [[ ${COMP_WORDS[i]} != -* ]]; then
            offset=$i;
            break;
        fi;
    done;
    _comp_command_offset $offset
}
_comp_command_offset ()
{
    local REPLY;
    _comp__find_original_word "$1";
    local word_offset=$REPLY;
    local COMP_LINE=$COMP_LINE COMP_POINT=$COMP_POINT COMP_CWORD=$COMP_CWORD;
    local -a comp_words=("${COMP_WORDS[@]}");
    local -a COMP_WORDS=("${comp_words[@]}");
    local i tail;
    for ((i = 0; i < word_offset; i++))
    do
        tail=${COMP_LINE#*"${COMP_WORDS[i]}"};
        ((COMP_POINT -= ${#COMP_LINE} - ${#tail}));
        COMP_LINE=$tail;
    done;
    COMP_WORDS=("${COMP_WORDS[@]:word_offset}");
    ((COMP_CWORD -= word_offset));
    COMPREPLY=();
    local cur;
    _comp_get_words cur;
    if ((COMP_CWORD == 0)); then
        _comp_compgen_commands;
    else
        _comp_dequote "${COMP_WORDS[0]}" || REPLY=${COMP_WORDS[0]};
        local cmd=$REPLY compcmd=$REPLY;
        local cspec=$(complete -p -- "$cmd" 2> /dev/null);
        if [[ ! -n $cspec && $cmd == */* ]]; then
            cspec=$(complete -p -- "${cmd##*/}" 2> /dev/null);
            [[ -n $cspec ]] && compcmd=${cmd##*/};
        fi;
        if [[ ! -n $cspec ]]; then
            compcmd=${cmd##*/};
            _comp_load -D -- "$compcmd";
            cspec=$(complete -p -- "$compcmd" 2> /dev/null);
        fi;
        local retry_count=0;
        while true; do
            local args original_cur=${comp_args[1]-$cur};
            if ((${#COMP_WORDS[@]} >= 2)); then
                args=("$cmd" "$original_cur" "${COMP_WORDS[-2]}");
            else
                args=("$cmd" "$original_cur");
            fi;
            if [[ ! -n $cspec ]]; then
                if ((${#COMPREPLY[@]} == 0)); then
                    _comp_complete_minimal "${args[@]}";
                fi;
            else
                if [[ $cspec == *\ -[CF]\ * ]]; then
                    if [[ $cspec == *' -F '* ]]; then
                        local func=${cspec#* -F };
                        func=${func%% *};
                        $func "${args[@]}";
                        if (($? == 124 && retry_count++ == 0)); then
                            COMPREPLY=();
                            cspec=$(complete -p -- "$compcmd" 2> /dev/null);
                            [[ -n $cspec ]] || break;
                            continue;
                        fi;
                    else
                        local completer=${cspec#* -C \'};
                        if ! _comp_dequote "'$completer"; then
                            _minimal "${args[@]}";
                            break;
                        fi;
                        completer=${REPLY[0]};
                        local -a suggestions;
                        local IFS='
';
                        local reset_monitor=$(shopt -po monitor) reset_lastpipe=$(shopt -p lastpipe) reset_noglob=$(shopt -po noglob);
                        set +o monitor;
                        shopt -s lastpipe;
                        set -o noglob;
                        COMP_KEY="$COMP_KEY" COMP_LINE="$COMP_LINE" COMP_POINT="$COMP_POINT" COMP_TYPE="$COMP_TYPE" $completer "${args[@]}" | mapfile -t suggestions;
                        $reset_monitor;
                        $reset_lastpipe;
                        $reset_noglob;
                        _comp_unlocal IFS;
                        local suggestion;
                        local i=0;
                        COMPREPLY=();
                        for suggestion in "${suggestions[@]}";
                        do
                            COMPREPLY[i]+=${COMPREPLY[i]+'
'}$suggestion;
                            if [[ $suggestion != *\\ ]]; then
                                ((i++));
                            fi;
                        done;
                    fi;
                    local opt;
                    while [[ $cspec == *" -o "* ]]; do
                        cspec=${cspec#*-o };
                        opt=${cspec%% *};
                        compopt -o "$opt";
                        cspec=${cspec#"$opt"};
                    done;
                else
                    cspec=${cspec#complete};
                    cspec=${cspec%%@("$compcmd"|"'${compcmd//\'/\'\\\'\'}'")};
                    eval "_comp_compgen -- $cspec";
                fi;
            fi;
            break;
        done;
    fi
}
_comp_compgen ()
{
    local _append=;
    local _var=;
    local _cur=${_comp_compgen__cur-${cur-}};
    local _dir="";
    local _ifs='
' _has_ifs="";
    local _icmd="" _xcmd="";
    local -a _upvars=();
    local _old_nocasematch="";
    if shopt -q nocasematch; then
        _old_nocasematch=set;
        shopt -u nocasematch;
    fi;
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':av:U:Rc:C:lF:i:x:' _opt "$@"; do
        case $_opt in
            a)
                _append=set
            ;;
            v)
                if [[ $OPTARG == @(*[^_a-zA-Z0-9]*|[0-9]*|''|_*|IFS|OPTIND|OPTARG|OPTERR|cur) ]]; then
                    printf 'bash_completion: %s: -v: invalid array name `%s'\''\n' "$FUNCNAME" "$OPTARG" 1>&2;
                    return 2;
                fi;
                _var=$OPTARG
            ;;
            U)
                if [[ $OPTARG == @(*[^_a-zA-Z0-9]*|[0-9]*|'') ]]; then
                    printf 'bash_completion: %s: -U: invalid variable name `%s'\''\n' "$FUNCNAME" "$OPTARG" 1>&2;
                    return 2;
                else
                    if [[ $OPTARG == @(_*|IFS|OPTIND|OPTARG|OPTERR|cur) ]]; then
                        printf 'bash_completion: %s: -U: unnecessary to mark `%s'\'' as upvar\n' "$FUNCNAME" "$OPTARG" 1>&2;
                        return 2;
                    fi;
                fi;
                _upvars+=("$OPTARG")
            ;;
            c)
                _cur=$OPTARG
            ;;
            R)
                _cur=""
            ;;
            C)
                if [[ ! -n $OPTARG ]]; then
                    printf 'bash_completion: %s: -C: invalid directory name `%s'\''\n' "$FUNCNAME" "$OPTARG" 1>&2;
                    return 2;
                fi;
                _dir=$OPTARG
            ;;
            l)
                _has_ifs=set _ifs='
'
            ;;
            F)
                _has_ifs=set _ifs=$OPTARG
            ;;
            [ix])
                if [[ ! -n $OPTARG ]]; then
                    printf 'bash_completion: %s: -%s: invalid command name `%s'\''\n' "$FUNCNAME" "$_opt" "$OPTARG" 1>&2;
                    return 2;
                else
                    if [[ -n $_icmd ]]; then
                        printf 'bash_completion: %s: -%s: `-i %s'\'' is already specified\n' "$FUNCNAME" "$_opt" "$_icmd" 1>&2;
                        return 2;
                    else
                        if [[ -n $_xcmd ]]; then
                            printf 'bash_completion: %s: -%s: `-x %s'\'' is already specified\n' "$FUNCNAME" "$_opt" "$_xcmd" 1>&2;
                            return 2;
                        fi;
                    fi;
                fi
            ;;&
            i)
                _icmd=$OPTARG
            ;;
            x)
                _xcmd=$OPTARG
            ;;
            *)
                printf 'bash_completion: %s: usage error\n' "$FUNCNAME" 1>&2;
                return 2
            ;;
        esac;
    done;
    [[ -n $_old_nocasematch ]] && shopt -s nocasematch;
    shift "$((OPTIND - 1))";
    if (($# == 0)); then
        printf 'bash_completion: %s: unexpected number of arguments\n' "$FUNCNAME" 1>&2;
        printf 'usage: %s [-alR|-F SEP|-v ARR|-c CUR] -- ARGS...' "$FUNCNAME" 1>&2;
        return 2;
    fi;
    if [[ ! -n $_var ]]; then
        _var=${_comp_compgen__var-COMPREPLY};
        [[ -n $_append ]] || _append=${_comp_compgen__append-};
    fi;
    if [[ $1 != -* ]]; then
        if [[ -n $_has_ifs ]]; then
            printf 'bash_completion: %s: `-l'\'' and `-F sep'\'' are not supported for generators\n' "$FUNCNAME" 1>&2;
            return 2;
        fi;
        local -a _generator;
        if [[ -n $_icmd ]]; then
            _generator=("_comp_cmd_${_icmd//[^a-zA-Z0-9_]/_}__compgen_$1");
        else
            if [[ -n $_xcmd ]]; then
                _generator=(_comp_xfunc "$_xcmd" "compgen_$1");
            else
                _generator=("_comp_compgen_$1");
            fi;
        fi;
        if ! declare -F -- "${_generator[0]}" &> /dev/null; then
            printf 'bash_completion: %s: unrecognized generator `%s'\'' (function %s not found)\n' "$FUNCNAME" "$1" "${_generator[0]}" 1>&2;
            return 2;
        fi;
        shift;
        _comp_compgen__call_generator "$@";
    else
        if [[ -n $_icmd || -n $_xcmd ]]; then
            printf 'bash_completion: %s: generator name is unspecified for `%s'\''\n' "$FUNCNAME" "${_icmd:+-i $_icmd}${_xcmd:+x $_xcmd}" 1>&2;
            return 2;
        fi;
        local IFS='
';
        if [[ $* == *\$[0-9]* || $* == *\$\{[0-9]* ]]; then
            printf 'bash_completion: %s: positional parameter $1, $2, ... do not work inside this function\n' "$FUNCNAME" 1>&2;
            return 2;
        fi;
        _comp_compgen__call_builtin "$@";
    fi
}
_comp_compgen__call_builtin ()
{
    if [[ -n $_dir ]]; then
        local _original_pwd=$PWD;
        local PWD=${PWD-} OLDPWD=${OLDPWD-};
        command cd -- "$_dir" &> /dev/null || {
            _comp_compgen__error_fallback;
            return
        };
    fi;
    local -a _result=();
    IFS=$_ifs compgen -V _result -X '' "$@" ${_cur:+-- "$_cur"} || {
        _comp_compgen__error_fallback;
        return
    };
    [[ -n $_dir ]] && command cd -- "$_original_pwd";
    ((${#_upvars[@]})) && _comp_unlocal "${_upvars[@]}";
    ((${#_result[@]})) || return;
    if [[ -n $_append ]]; then
        eval -- "$_var+=(\"\${_result[@]}\")";
    else
        eval -- "$_var=(\"\${_result[@]}\")";
    fi;
    return
}
_comp_compgen__call_generator ()
{
    ((${#_upvars[@]})) && _comp_unlocal "${_upvars[@]}";
    if [[ -n $_dir ]]; then
        local _original_pwd=$PWD;
        local PWD=${PWD-} OLDPWD=${OLDPWD-};
        command cd -- "$_dir" &> /dev/null || {
            _comp_compgen__error_fallback;
            return
        };
    fi;
    local _comp_compgen__append=$_append;
    local _comp_compgen__var=$_var;
    local _comp_compgen__cur=$_cur cur=$_cur;
    "${_generator[@]}" "$@";
    local _status=$?;
    [[ -n $_dir ]] && command cd -- "$_original_pwd";
    return "$_status"
}
_comp_compgen__error_fallback ()
{
    local _status=$?;
    if [[ -n $_append ]]; then
        eval -- "$_var+=()";
    else
        eval -- "$_var=()";
    fi;
    return "$_status"
}
_comp_compgen_allowed_groups ()
{
    if _comp_as_root; then
        _comp_compgen -- -g;
    else
        _comp_compgen_split -- "$(id -Gn 2> /dev/null || groups 2> /dev/null)";
    fi
}
_comp_compgen_allowed_users ()
{
    if _comp_as_root; then
        _comp_compgen -- -u;
    else
        _comp_compgen_split -- "$(id -un 2> /dev/null || whoami 2> /dev/null)";
    fi
}
_comp_compgen_available_interfaces ()
{
    local PATH=$PATH:/sbin;
    local generated;
    _comp_compgen -v generated split -- "$({ if [[ ${1-} == -w ]]; then
    iwconfig;
else
    if [[ ${1-} == -a ]]; then
        ip -c=never link show up || ip link show up || ifconfig;
    else
        ip -c=never link show || ip link show || ifconfig -a;
    fi;
fi; } 2> /dev/null | _comp_awk '/^[^ \t]/ { if ($1 ~ /^[0-9]+:/) { print $2 } else { print $1 } }')" && _comp_compgen -U generated set "${generated[@]%:}"
}
_comp_compgen_cd_devices ()
{
    _comp_compgen -c "${cur:-/dev/}" -- -f -d -X "!*/?([amrs])cd!(c-*)"
}
_comp_compgen_commands ()
{
    [[ ! -n ${cur-} ]] && shopt -q no_empty_cmd_completion && return 1;
    _comp_compgen -- -c -o plusdirs && compopt -o filenames
}
_comp_compgen_configured_interfaces ()
{
    local -a files;
    if [[ -f /etc/debian_version ]]; then
        _comp_expand_glob files '/etc/network/interfaces /etc/network/interfaces.d/*' || return 0;
        _comp_compgen -U files split -- "$(command sed -ne 's|^iface \([^ ]\{1,\}\).*$|\1|p' "${files[@]}" 2> /dev/null)";
    else
        if [[ -f /etc/SuSE-release ]]; then
            _comp_expand_glob files '/etc/sysconfig/network/ifcfg-*' || return 0;
            _comp_compgen -U files split -- "$(printf '%s\n' "${files[@]}" | command sed -ne 's|.*ifcfg-\([^*].*\)$|\1|p')";
        else
            if [[ -f /etc/pld-release ]]; then
                _comp_compgen -U files split -- "$(command ls -B /etc/sysconfig/interfaces | command sed -ne 's|.*ifcfg-\([^*].*\)$|\1|p')";
            else
                _comp_expand_glob files '/etc/sysconfig/network-scripts/ifcfg-*' || return 0;
                _comp_compgen -U files split -- "$(printf '%s\n' "${files[@]}" | command sed -ne 's|.*ifcfg-\([^*].*\)$|\1|p')";
            fi;
        fi;
    fi
}
_comp_compgen_dvd_devices ()
{
    _comp_compgen -c "${cur:-/dev/}" -- -f -d -X "!*/?(r)dvd*"
}
_comp_compgen_filedir ()
{
    _comp_compgen_tilde && return;
    local -a toks;
    local _arg=${1-};
    if [[ $_arg == -d ]]; then
        _comp_compgen -v toks -- -d;
    else
        local REPLY;
        _comp_quote_compgen "${cur-}";
        local _quoted=$REPLY;
        _comp_unlocal REPLY;
        [[ $_quoted == "''" ]] && _quoted="";
        local _xspec=${_arg:+"!*.@($_arg|${_arg^^})"} _plusdirs=();
        local _opts=(-f -X "$_xspec");
        [[ -n $_xspec ]] && _plusdirs=(-o plusdirs);
        [[ -n ${BASH_COMPLETION_FILEDIR_FALLBACK-} || ! -n ${_plusdirs-} ]] || _opts+=("${_plusdirs[@]}");
        _comp_compgen -v toks -c "$_quoted" -- "${_opts[@]}";
        [[ -n ${BASH_COMPLETION_FILEDIR_FALLBACK-} && -n $_arg && ${#toks[@]} -lt 1 ]] && _comp_compgen -av toks -c "$_quoted" -- -f ${_plusdirs+"${_plusdirs[@]}"};
    fi;
    if ((${#toks[@]} != 0)); then
        if [[ $cur != ?(*/).. ]]; then
            _comp_compgen -Rv toks -- -X '?(*/)@(.|..)' -W '"${toks[@]}"';
        fi;
    fi;
    if ((${#toks[@]} != 0)); then
        compopt -o filenames 2> /dev/null;
    fi;
    local IFS='
';
    _comp_compgen -U toks set ${toks[@]+"${toks[@]}"}
}
_comp_compgen_filedir_xspec ()
{
    _comp_compgen_tilde && return;
    local REPLY;
    _comp_quote_compgen "$cur";
    local quoted=$REPLY;
    local xspec=${_comp_xspecs[${1##*/}]-${_xspecs[${1##*/}]-}};
    local -a toks;
    _comp_compgen -v toks -c "$quoted" -- -d;
    eval xspec="${xspec}";
    local matchop=!;
    if [[ $xspec == !* ]]; then
        xspec=${xspec#!};
        matchop=@;
    fi;
    xspec="$matchop($xspec|${xspec^^})";
    _comp_compgen -av toks -c "$quoted" -- -f -X "@(|!($xspec))";
    [[ -n ${BASH_COMPLETION_FILEDIR_FALLBACK-} && ${#toks[@]} -lt 1 ]] && _comp_compgen -av toks -c "$quoted" -- -f;
    ((${#toks[@]})) || return 1;
    if [[ $cur != ?(*/).. ]]; then
        _comp_compgen -Rv toks -- -X '?(*/)@(.|..)' -W '"${toks[@]}"' || return 1;
    fi;
    compopt -o filenames;
    _comp_compgen -RU toks -- -W '"${toks[@]}"'
}
_comp_compgen_fstypes ()
{
    local _fss;
    if [[ -e /proc/filesystems ]]; then
        _fss="$(cut -d' ' -f2 /proc/filesystems)
             $(_comp_awk '! /\*/ { print $NF }' /etc/filesystems 2> /dev/null)";
    else
        _fss="$(_comp_awk '/^[ \t]*[^#]/ { print $3 }' /etc/fstab 2> /dev/null)
             $(_comp_awk '/^[ \t]*[^#]/ { print $3 }' /etc/mnttab 2> /dev/null)
             $(_comp_awk '/^[ \t]*[^#]/ { print $4 }' /etc/vfstab 2> /dev/null)
             $(_comp_awk '{ print $1 }' /etc/dfs/fstypes 2> /dev/null)
             $(lsvfs 2> /dev/null | _comp_awk '$1 !~ /^(Filesystem|[^a-zA-Z])/ { print $1 }')
             $([[ -d /etc/fs ]] && command ls /etc/fs)";
    fi;
    [[ -n $_fss ]] && _comp_compgen_split -- "$_fss"
}
_comp_compgen_gids ()
{
    if type getent &> /dev/null; then
        _comp_compgen_split -- "$(getent group | cut -d: -f3)";
    else
        if type perl &> /dev/null; then
            _comp_compgen_split -- "$(perl -e 'while (($gid) = (getgrent)[2]) { print $gid . "\n" }')";
        else
            _comp_compgen_split -- "$(cut -d: -f3 /etc/group)";
        fi;
    fi
}
_comp_compgen_help ()
{
    (($#)) || set -- -- --help;
    local -a _lines;
    _comp_compgen_help__get_help_lines "$@" || return "$?";
    local -a options=();
    local _line;
    for _line in "${_lines[@]}";
    do
        [[ $_line == *([[:blank:]])-* ]] || continue;
        while [[ $_line =~ ((^|[^-])-[A-Za-z0-9?][[:space:]]+)\[?[A-Z0-9]+([,_-]+[A-Z0-9]+)?(\.\.+)?\]? ]]; do
            _line=${_line/"${BASH_REMATCH[0]}"/"${BASH_REMATCH[1]}"};
        done;
        _comp_compgen_help__parse "${_line// or /, }";
    done;
    ((${#options[@]})) || return 1;
    _comp_compgen -U options -- -W '"${options[@]}"';
    return 0
}
_comp_compgen_help__get_help_lines ()
{
    local -a help_cmd;
    case ${1-} in
        -)
            if (($# > 1)); then
                printf 'bash_completion: %s -: extra arguments for -\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -c cmd args...\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s [-- args...]\n' "${FUNCNAME[1]}" 1>&2;
                return 2;
            fi;
            help_cmd=(exec cat)
        ;;
        -c)
            if (($# < 2)); then
                printf 'bash_completion: %s -c: no command is specified\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s -c cmd args...\n' "${FUNCNAME[1]}" 1>&2;
                printf 'usage: %s [-- args...]\n' "${FUNCNAME[1]}" 1>&2;
                return 2;
            fi;
            help_cmd=("${@:2}")
        ;;
        --)
            shift 1
        ;&
        *)
            local REPLY;
            _comp_dequote "${comp_args[0]-}" || REPLY=${comp_args[0]-};
            help_cmd=("${REPLY:-false}" "$@")
        ;;
    esac;
    local REPLY;
    _comp_split -l REPLY "$(LC_ALL=C "${help_cmd[@]}" 2>&1)" && _lines=("${REPLY[@]}")
}
_comp_compgen_help__parse ()
{
    local option option2 i;
    option=;
    local -a array;
    if _comp_split -F '
,/|' array "$1"; then
        for i in "${array[@]}";
        do
            case "$i" in
                ---*)
                    break
                ;;
                --?*)
                    option=$i;
                    break
                ;;
                -?*)
                    [[ -n $option ]] || option=$i
                ;;
                *)
                    break
                ;;
            esac;
        done;
    fi;
    [[ -n $option ]] || return 1;
    if [[ $option =~ (\[((no|dont)-?)\]). ]]; then
        option2=${option/"${BASH_REMATCH[1]}"/};
        option2=${option2%%[<{().[]*};
        options+=("${option2/=*/=}");
        option=${option/"${BASH_REMATCH[1]}"/"${BASH_REMATCH[2]}"};
    fi;
    [[ $option =~ ^([^=<{().[]|\.[A-Za-z0-9])+=? ]] && options+=("$BASH_REMATCH")
}
_comp_compgen_inserted_kernel_modules ()
{
    _comp_compgen -c "${1:-$cur}" split -- "$(PATH="$PATH:/sbin" lsmod | _comp_awk '{if (NR != 1) print $1}')"
}
_comp_compgen_ip_addresses ()
{
    local _n;
    case ${1-} in
        -a)
            _n='6\{0,1\}'
        ;;
        -6)
            _n='6'
        ;;
        *)
            _n=
        ;;
    esac;
    local PATH=$PATH:/sbin;
    local addrs;
    _comp_compgen -v addrs split -- "$({ ip -c=never addr show || ip addr show || LC_ALL=C ifconfig -a; } 2> /dev/null | command sed -e 's/[[:space:]]addr:/ /' -ne "s|.*inet${_n}[[:space:]]\{1,\}\([^[:space:]/]*\).*|\1|p")" || return;
    if [[ ! -n $_n ]]; then
        _comp_compgen -U addrs set "${addrs[@]}";
    else
        _comp_compgen -U addrs ltrim_colon "${addrs[@]}";
    fi
}
_comp_compgen_kernel_modules ()
{
    local _modpath=/lib/modules/$1;
    _comp_compgen_split -- "$(command ls -RL "$_modpath" 2> /dev/null | command sed -ne 's/^\(.*\)\.k\{0,1\}o\(\.[gx]z\)\{0,1\}$/\1/p' -e 's/^\(.*\)\.ko\.zst$/\1/p')"
}
_comp_compgen_kernel_versions ()
{
    _comp_compgen_split -- "$(command ls /lib/modules)"
}
_comp_compgen_known_hosts ()
{
    local known_hosts;
    _comp_compgen_known_hosts__impl "$@" || return "$?";
    _comp_compgen -U known_hosts set "${known_hosts[@]}"
}
_comp_compgen_known_hosts__impl ()
{
    known_hosts=();
    local configfile="" flag prefix="";
    local cur suffix="" aliases="" i host ipv4="" ipv6="";
    local -a kh tmpkh=() khd=() config=();
    local OPTIND=1;
    while getopts "ac46F:p:" flag "$@"; do
        case $flag in
            a)
                aliases=set
            ;;
            c)
                suffix=':'
            ;;
            F)
                if [[ ! -n $OPTARG ]]; then
                    echo "bash_completion: $FUNCNAME: -F: an empty filename is specified" 1>&2;
                    return 2;
                fi;
                configfile=$OPTARG
            ;;
            p)
                prefix=$OPTARG
            ;;
            4)
                ipv4=set
            ;;
            6)
                ipv6=set
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    if (($# < OPTIND)); then
        echo "bash_completion: $FUNCNAME: missing mandatory argument CWORD" 1>&2;
        return 2;
    fi;
    cur=${!OPTIND};
    ((OPTIND += 1));
    if (($# >= OPTIND)); then
        echo "bash_completion: $FUNCNAME($*): unprocessed arguments:" "$(while (($# >= OPTIND)); do
    printf '%s ' ${!OPTIND}
shift;
done)" 1>&2;
        return 2;
    fi;
    [[ $cur == *@* ]] && prefix=$prefix${cur%@*}@ && cur=${cur#*@};
    kh=();
    if [[ -n $configfile ]]; then
        [[ -r $configfile && ! -d $configfile ]] && config+=("$configfile");
    else
        for i in /etc/ssh/ssh_config ~/.ssh/config ~/.ssh2/config;
        do
            [[ -r $i && ! -d $i ]] && config+=("$i");
        done;
    fi;
    if ((${#config[@]} > 0)); then
        for i in "${config[@]}";
        do
            _comp__included_ssh_config_files "$i";
        done;
    fi;
    if ((${#config[@]} > 0)); then
        if _comp_split -l tmpkh "$(_comp_awk 'sub("^[ \t]*([Gg][Ll][Oo][Bb][Aa][Ll]|[Uu][Ss][Ee][Rr])[Kk][Nn][Oo][Ww][Nn][Hh][Oo][Ss][Tt][Ss][Ff][Ii][Ll][Ee][ \t=]+", "") { print $0 }' "${config[@]}" | sort -u)"; then
            local tmpkh2 j REPLY;
            for i in "${tmpkh[@]}";
            do
                while [[ $i =~ ^([^\"]*)\"([^\"]*)\"(.*)$ ]]; do
                    i=${BASH_REMATCH[1]}${BASH_REMATCH[3]};
                    _comp_expand_tilde "${BASH_REMATCH[2]}";
                    [[ -r $REPLY ]] && kh+=("$REPLY");
                done;
                _comp_split tmpkh2 "$i" || continue;
                for j in "${tmpkh2[@]}";
                do
                    _comp_expand_tilde "$j";
                    [[ -r $REPLY ]] && kh+=("$REPLY");
                done;
            done;
        fi;
    fi;
    if [[ ! -n $configfile ]]; then
        for i in /etc/ssh/ssh_known_hosts /etc/ssh/ssh_known_hosts2 /etc/known_hosts /etc/known_hosts2 ~/.ssh/known_hosts ~/.ssh/known_hosts2;
        do
            [[ -r $i && ! -d $i ]] && kh+=("$i");
        done;
        for i in /etc/ssh2/knownhosts ~/.ssh2/hostkeys;
        do
            [[ -d $i ]] || continue;
            _comp_expand_glob tmpkh '"$i"/*.pub' && khd+=("${tmpkh[@]}");
        done;
    fi;
    if ((${#kh[@]} + ${#khd[@]} > 0)); then
        if ((${#kh[@]} > 0)); then
            for i in "${kh[@]}";
            do
                while read -ra tmpkh; do
                    ((${#tmpkh[@]} == 0)) && continue;
                    [[ ${tmpkh[0]} == [\|\#]* ]] && continue;
                    local host_list=${tmpkh[0]};
                    [[ ${tmpkh[0]} == @* ]] && host_list=${tmpkh[1]-};
                    local -a hosts;
                    if _comp_split -F , hosts "$host_list"; then
                        for host in "${hosts[@]}";
                        do
                            [[ $host == *[*?]* ]] && continue;
                            host=${host#[};
                            host=${host%]?(:+([0-9]))};
                            [[ -n $host ]] && known_hosts+=("$host");
                        done;
                    fi;
                done < "$i";
            done;
        fi;
        if ((${#khd[@]} > 0)); then
            for i in "${khd[@]}";
            do
                if [[ $i == *key_22_*.pub && -r $i ]]; then
                    host=${i/#*key_22_/};
                    host=${host/%.pub/};
                    [[ -n $host ]] && known_hosts+=("$host");
                fi;
            done;
        fi;
        ((${#known_hosts[@]})) && _comp_compgen -v known_hosts -- -W '"${known_hosts[@]}"' -P "$prefix" -S "$suffix";
    fi;
    if [[ ${#config[@]} -gt 0 && -n $aliases ]]; then
        local -a hosts;
        if _comp_split hosts "$(command sed -ne 's/^[[:blank:]]*[Hh][Oo][Ss][Tt][[:blank:]=]\{1,\}\(.*\)$/\1/p' "${config[@]}")"; then
            _comp_compgen -av known_hosts -- -P "$prefix" -S "$suffix" -W '"${hosts[@]%%[*?%]*}"' -X '@(\!*|)';
        fi;
    fi;
    if [[ -n ${BASH_COMPLETION_KNOWN_HOSTS_WITH_AVAHI-} ]] && type avahi-browse &> /dev/null; then
        local generated=$(avahi-browse -cprak 2> /dev/null | _comp_awk -F ';' '/^=/ && $5 ~ /^_(ssh|workstation)\._tcp$/ { print $7 }' | sort -u);
        _comp_compgen -av known_hosts -- -P "$prefix" -S "$suffix" -W '$generated';
    fi;
    if type ruptime &> /dev/null; then
        local generated=$(ruptime 2> /dev/null | _comp_awk '!/^ruptime:/ { print $1 }');
        _comp_compgen -av known_hosts -- -W '$generated';
    fi;
    if [[ -n ${BASH_COMPLETION_KNOWN_HOSTS_WITH_HOSTFILE-set} ]]; then
        _comp_compgen -av known_hosts -- -A hostname -P "$prefix" -S "$suffix";
    fi;
    ((${#known_hosts[@]})) || return 1;
    if [[ -n $ipv4 ]]; then
        known_hosts=("${known_hosts[@]/*:*$suffix/}");
    fi;
    if [[ -n $ipv6 ]]; then
        known_hosts=("${known_hosts[@]/+([0-9]).+([0-9]).+([0-9]).+([0-9])$suffix/}");
    fi;
    if [[ -n $ipv4 || -n $ipv6 ]]; then
        for i in "${!known_hosts[@]}";
        do
            [[ -n ${known_hosts[i]} ]] || unset -v 'known_hosts[i]';
        done;
    fi;
    ((${#known_hosts[@]})) || return 1;
    _comp_compgen -v known_hosts -c "$prefix$cur" ltrim_colon "${known_hosts[@]}"
}
_comp_compgen_ltrim_colon ()
{
    (($#)) || return 0;
    local -a _tmp;
    _tmp=("$@");
    if [[ $cur == *:* && $COMP_WORDBREAKS == *:* ]]; then
        local _colon_word=${cur%"${cur##*:}"};
        _tmp=("${_tmp[@]#"$_colon_word"}");
    fi;
    _comp_compgen_set "${_tmp[@]}"
}
_comp_compgen_mac_addresses ()
{
    local _re='\([A-Fa-f0-9]\{2\}:\)\{5\}[A-Fa-f0-9]\{2\}';
    local PATH="$PATH:/sbin:/usr/sbin";
    local -a addresses;
    _comp_compgen -v addresses split -- "$({ ip -c=never link show || ip link show || LC_ALL=C ifconfig -a; } 2> /dev/null | command sed -ne "s/.*[[:space:]]HWaddr[[:space:]]\{1,\}\($_re\)[[:space:]].*/\1/p" -ne "s/.*[[:space:]]HWaddr[[:space:]]\{1,\}\($_re\)[[:space:]]*$/\1/p" -ne "s|.*[[:space:]]\(link/\)\{0,1\}ether[[:space:]]\{1,\}\($_re\)[[:space:]].*|\2|p" -ne "s|.*[[:space:]]\(link/\)\{0,1\}ether[[:space:]]\{1,\}\($_re\)[[:space:]]*$|\2|p")";
    _comp_compgen -av addresses split -- "$({ arp -an || ip -c=never neigh show || ip neigh show; } 2> /dev/null | command sed -ne "s/.*[[:space:]]\($_re\)[[:space:]].*/\1/p" -ne "s/.*[[:space:]]\($_re\)[[:space:]]*$/\1/p")";
    _comp_compgen -av addresses split -- "$(command sed -ne "s/^[[:space:]]*\($_re\)[[:space:]].*/\1/p" /etc/ethers 2> /dev/null)";
    _comp_compgen -U addresses ltrim_colon "${addresses[@]}"
}
_comp_compgen_pci_ids ()
{
    _comp_compgen_split -- "$(PATH="$PATH:/sbin" lspci -n | _comp_awk '{print $3}')"
}
_comp_compgen_pgids ()
{
    _comp_compgen_split -- "$(command ps ax -o pgid=)"
}
_comp_compgen_pids ()
{
    _comp_compgen_split -- "$(command ps ax -o pid=)"
}
_comp_compgen_pnames ()
{
    local -a procs=();
    if [[ ${1-} == -s ]]; then
        _comp_split procs "$(command ps ax -o comm | command sed -e 1d)";
    else
        local -a psout;
        _comp_split -l psout "$({ command ps ax -o command= || command ps ax -o comm=; } 2> /dev/null)";
        local line i=-1;
        for line in "${psout[@]}";
        do
            if ((i == -1)); then
                if [[ $line =~ ^(.*[[:space:]])COMMAND([[:space:]]|$) ]]; then
                    i=${#BASH_REMATCH[1]};
                else
                    break;
                fi;
            else
                line=${line:i};
                line=${line%% *};
                [[ -n $line ]] && procs+=("$line");
            fi;
        done;
        if ((i == -1)); then
            for line in "${psout[@]}";
            do
                if [[ $line =~ ^[[(](.+)[])]$ ]]; then
                    procs+=("${BASH_REMATCH[1]}");
                else
                    line=${line%% *};
                    line=${line##@(*/|-)};
                    [[ -n $line ]] && procs+=("$line");
                fi;
            done;
        fi;
    fi;
    ((${#procs[@]})) && _comp_compgen -U procs -- -X "<defunct>" -W '"${procs[@]}"'
}
_comp_compgen_selinux_users ()
{
    _comp_compgen_split -- "$(semanage user -nl 2> /dev/null | _comp_awk '{ print $1 }')"
}
_comp_compgen_services ()
{
    local sysvdirs;
    _comp_sysvdirs || return 1;
    local services;
    _comp_expand_glob services '${sysvdirs[0]}/!($_comp_backup_glob|functions|README)';
    local _generated=$({ systemctl list-units --full --all || systemctl list-unit-files; } 2> /dev/null | _comp_awk '$1 ~ /\.service$/ { sub("\\.service$", "", $1); print $1 }');
    _comp_split -la services "$_generated";
    if [[ -x /sbin/upstart-udev-bridge ]]; then
        _comp_split -la services "$(initctl list 2> /dev/null | cut -d' ' -f1)";
    fi;
    ((${#services[@]})) || return 1;
    _comp_compgen -U services -U sysvdirs -- -W '"${services[@]#${sysvdirs[0]}/}"'
}
_comp_compgen_set ()
{
    local _append=${_comp_compgen__append-};
    local _var=${_comp_compgen__var-COMPREPLY};
    eval -- "$_var${_append:++}=(\"\$@\")";
    (($#))
}
_comp_compgen_shells ()
{
    local -a shells=();
    local _shell _rest;
    while read -r _shell _rest; do
        [[ $_shell == /* ]] && shells+=("$_shell");
    done 2> /dev/null < "${1-}"/etc/shells;
    _comp_compgen -U shells -- -W '"${shells[@]}"'
}
_comp_compgen_signals ()
{
    local -a sigs;
    _comp_compgen -v sigs -c "SIG${cur#"${1-}"}" -- -A signal && _comp_compgen -RU sigs -- -P "${1-}" -W '"${sigs[@]#SIG}"'
}
_comp_compgen_split ()
{
    local _ifs='
';
    local -a _compgen_options=();
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':lF:X:S:P:o:' _opt "$@"; do
        case $_opt in
            l)
                _ifs='
'
            ;;
            F)
                _ifs=$OPTARG
            ;;
            [XSPo])
                _compgen_options+=("-$_opt" "$OPTARG")
            ;;
            *)
                printf 'bash_completion: usage: %s [-l|-F sep] [--] str\n' "$FUNCNAME" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    if (($# != 1)); then
        printf 'bash_completion: %s: unexpected number of arguments.\n' "$FUNCNAME" 1>&2;
        printf 'usage: %s [-l|-F sep] [--] str' "$FUNCNAME" 1>&2;
        return 2;
    fi;
    local input=$1 IFS='
';
    _comp_compgen -F "$_ifs" -U input -- ${_compgen_options[@]+"${_compgen_options[@]}"} -W '$input'
}
_comp_compgen_terms ()
{
    _comp_compgen_split -- "$({ command sed -ne 's/^\([^[:space:]#|]\{2,\}\)|.*/\1/p' /etc/termcap
{ toe -a || toe; } | _comp_awk '{ print $1 }'
_comp_expand_glob dirs '/{etc,lib,usr/lib,usr/share}/terminfo/?' && find "${dirs[@]}" -type f -maxdepth 1 | _comp_awk -F / '{ print $NF }'; } 2> /dev/null)"
}
_comp_compgen_tilde ()
{
    if [[ ${cur-} == \~* && $cur != */* ]]; then
        if _comp_compgen -c "${cur#\~}" -- -P '~' -u; then
            compopt -o filenames 2> /dev/null;
            return 0;
        fi;
    fi;
    return 1
}
_comp_compgen_uids ()
{
    if type getent &> /dev/null; then
        _comp_compgen_split -- "$(getent passwd | cut -d: -f3)";
    else
        if type perl &> /dev/null; then
            _comp_compgen_split -- "$(perl -e 'while (($uid) = (getpwent)[2]) { print $uid . "\n" }')";
        else
            _comp_compgen_split -- "$(cut -d: -f3 /etc/passwd)";
        fi;
    fi
}
_comp_compgen_usage ()
{
    (($#)) || set -- -- --usage;
    local -a _lines;
    _comp_compgen_help__get_help_lines "$@" || return "$?";
    local -a options=();
    local _line _match _option _i _char;
    for _line in "${_lines[@]}";
    do
        while [[ $_line =~ \[[[:space:]]*(-[^]]+)[[:space:]]*\] ]]; do
            _match=${BASH_REMATCH[0]};
            _option=${BASH_REMATCH[1]};
            case $_option in
                -?(\[)+([a-zA-Z0-9?]))
                    for ((_i = 1; _i < ${#_option}; _i++))
                    do
                        _char=${_option:_i:1};
                        [[ $_char != '[' ]] && options+=("-$_char");
                    done
                ;;
                *)
                    _comp_compgen_help__parse "$_option"
                ;;
            esac;
            _line=${_line#*"$_match"};
        done;
    done;
    ((${#options[@]})) || return 1;
    _comp_compgen -U options -- -W '"${options[@]}"';
    return 0
}
_comp_compgen_usb_ids ()
{
    _comp_compgen_split -- "$(PATH="$PATH:/sbin" lsusb | _comp_awk '{print $6}')"
}
_comp_compgen_usergroups ()
{
    if [[ $cur == *\\\\* || $cur == *:*:* ]]; then
        return;
    else
        if [[ $cur == *\\:* ]]; then
            local tmp;
            if [[ ${1-} == -u ]]; then
                _comp_compgen -v tmp -c "${cur#*:}" allowed_groups;
            else
                _comp_compgen -v tmp -c "${cur#*:}" -- -g;
            fi;
            if ((${#tmp[@]})); then
                local _prefix=${cur%%*([^:])};
                _prefix=${_prefix//\\/};
                _comp_compgen -Rv tmp -- -P "$_prefix" -W '"${tmp[@]}"';
                _comp_compgen -U tmp set "${tmp[@]}";
            fi;
        else
            if [[ $cur == *:* ]]; then
                if [[ ${1-} == -u ]]; then
                    _comp_compgen -c "${cur#*:}" allowed_groups;
                else
                    _comp_compgen -c "${cur#*:}" -- -g;
                fi;
            else
                if [[ ${1-} == -u ]]; then
                    _comp_compgen_allowed_users;
                else
                    _comp_compgen -- -u;
                fi;
            fi;
        fi;
    fi
}
_comp_compgen_variables ()
{
    if [[ $cur =~ ^(\$(\{[!#]?)?)([A-Za-z0-9_]*)$ ]]; then
        if [[ $cur == '${'* ]]; then
            local arrs vars;
            _comp_compgen -v vars -c "${BASH_REMATCH[3]}" -- -A variable -P "${BASH_REMATCH[1]}" -S '}';
            _comp_compgen -v arrs -c "${BASH_REMATCH[3]}" -- -A arrayvar -P "${BASH_REMATCH[1]}" -S '[';
            if ((${#vars[@]} == 1 && ${#arrs[@]} != 0)); then
                compopt -o nospace;
                _comp_compgen -U vars -U arrs -R -- -W '"${arrs[@]}"';
            else
                _comp_compgen -U vars -U arrs -R -- -W '"${vars[@]}"';
            fi;
        else
            _comp_compgen -ac "${BASH_REMATCH[3]}" -- -A variable -P '$';
        fi;
        return 0;
    else
        if [[ $cur =~ ^(\$\{[#!]?)([A-Za-z0-9_]*)\[([^]]*)$ ]]; then
            local vars;
            _comp_compgen -v vars -c "${BASH_REMATCH[3]}" -- -W '"${!'"${BASH_REMATCH[2]}"'[@]}"' -P "${BASH_REMATCH[1]}${BASH_REMATCH[2]}[" -S ']}';
            if [[ ${BASH_REMATCH[3]} == [@*] ]]; then
                vars+=("${BASH_REMATCH[1]}${BASH_REMATCH[2]}[${BASH_REMATCH[3]}]}");
            fi;
            if ((${#vars[@]})); then
                _comp_compgen -U vars -c "$cur" ltrim_colon "${vars[@]}";
            else
                _comp_compgen_set;
            fi;
            return 0;
        else
            if [[ $cur =~ ^\$\{[#!]?[A-Za-z0-9_]*\[.*\]$ ]]; then
                _comp_compgen -c "$cur" ltrim_colon "$cur}";
                return 0;
            fi;
        fi;
    fi;
    return 1
}
_comp_compgen_xinetd_services ()
{
    local xinetddir=${_comp__test_xinetd_dir:-/etc/xinetd.d};
    if [[ -d $xinetddir ]]; then
        local -a svcs;
        if _comp_expand_glob svcs '$xinetddir/!($_comp_backup_glob)'; then
            _comp_compgen -U svcs -U xinetddir -- -W '"${svcs[@]#$xinetddir/}"';
        fi;
    fi
}
_comp_complete_filedir_xspec ()
{
    local cur prev words cword comp_args;
    _comp_initialize -- "$@" || return;
    _comp_compgen_filedir_xspec "$1"
}
_comp_complete_known_hosts ()
{
    local cur prev words cword comp_args;
    _comp_initialize -n : -- "$@" || return;
    local -a options=();
    [[ ${1-} == -a || ${2-} == -a ]] && options+=(-a);
    [[ ${1-} == -c || ${2-} == -c ]] && options+=(-c);
    local IFS='
';
    _comp_compgen_known_hosts ${options[@]+"${options[@]}"} -- "$cur"
}
_comp_complete_load ()
{
    local cmd=${1:-_EmptycmD_};
    _comp_load -D -- "$cmd" && return 124
}
_comp_complete_longopt ()
{
    local cur prev words cword was_split comp_args;
    _comp_initialize -s -- "$@" || return;
    case "${prev,,}" in
        --help | --usage | --version)
            return
        ;;
        --!(no-*)dir*)
            _comp_compgen -a filedir -d;
            return
        ;;
        --!(no-*)@(file|path)*)
            _comp_compgen -a filedir;
            return
        ;;
        --+([-a-z0-9_]))
            local argtype=$(LC_ALL=C $1 --help 2>&1 | command sed -ne "s|.*$prev\[\{0,1\}=[<[]\{0,1\}\([-A-Za-z0-9_]\{1,\}\).*|\1|p");
            case ${argtype,,} in
                *dir*)
                    _comp_compgen -a filedir -d;
                    return
                ;;
                *file* | *path*)
                    _comp_compgen -a filedir;
                    return
                ;;
            esac
        ;;
    esac;
    [[ -n $was_split ]] && return;
    if [[ $cur == -* ]]; then
        _comp_compgen_split -- "$(LC_ALL=C $1 --help 2>&1 | while read -r line; do
    [[ $line =~ --[A-Za-z0-9]+([-_][A-Za-z0-9]+)*=? ]] && printf '%s\n' "${BASH_REMATCH[0]}";
done)";
        [[ ${COMPREPLY-} == *= ]] && compopt -o nospace;
    else
        if [[ $1 == *@(rmdir|chroot) ]]; then
            _comp_compgen -a filedir -d;
        else
            [[ $1 == *mkdir ]] && compopt -o nospace;
            _comp_compgen -a filedir;
        fi;
    fi
}
_comp_complete_minimal ()
{
    local cur prev words cword comp_args;
    _comp_initialize -- "$@" || return;
    compopt -o bashdefault -o default
}
_comp_complete_service ()
{
    local cur prev words cword comp_args;
    _comp_initialize -- "$@" || return;
    ((cword > 2)) && return;
    if [[ $cword -eq 1 && $prev == ?(*/)service ]]; then
        _comp_compgen_services;
        [[ -e /etc/mandrake-release ]] && _comp_compgen_xinetd_services;
    else
        local sysvdirs;
        _comp_sysvdirs || return 1;
        _comp_compgen_split -l -- "$(command sed -e 'y/|/ /' -ne 's/^.*\(U\|msg_u\)sage.*{\(.*\)}.*$/\2/p' "${sysvdirs[0]}/${prev##*/}" 2> /dev/null) start stop";
    fi
}
_comp_complete_user_at_host ()
{
    local cur prev words cword comp_args;
    _comp_initialize -n : -- "$@" || return;
    if [[ $cur == *@* ]]; then
        _comp_compgen_known_hosts "$cur";
    else
        _comp_compgen -- -u -S @;
        compopt -o nospace;
    fi
}
_comp_count_args ()
{
    local has_optarg="" has_exclude="" exclude="" glob_include="";
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':a:n:i:' _opt "$@"; do
        case $_opt in
            a)
                has_optarg=$OPTARG
            ;;
            n)
                has_exclude=set exclude+=$OPTARG
            ;;
            i)
                glob_include=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    if [[ -n $has_exclude ]]; then
        local cword words;
        _comp__reassemble_words "$exclude<>&" words cword;
    fi;
    local i;
    REPLY=1;
    for ((i = 1; i < cword; i++))
    do
        if [[ -n $has_optarg && ${words[i]} == $has_optarg ]]; then
            ((i++));
        else
            if [[ ${words[i]} != -?* || -n $glob_include && ${words[i]} == $glob_include ]]; then
                ((REPLY++));
            else
                if [[ ${words[i]} == -- ]]; then
                    ((REPLY += cword - i - 1));
                    break;
                fi;
            fi;
        fi;
    done
}
_comp_delimited ()
{
    local prefix="" delimiter=$1 deduplicate=set;
    shift;
    if [[ $delimiter == -k ]]; then
        deduplicate="";
        delimiter=$1;
        shift;
    fi;
    [[ $cur == *"$delimiter"* ]] && prefix=${cur%"$delimiter"*}$delimiter;
    if [[ -n $deduplicate ]]; then
        _comp_compgen -R -- "$@";
        local -a existing;
        _comp_split -F "$delimiter" existing "$cur";
        [[ ! -n $cur || $cur == *"$delimiter" ]] || unset -v "existing[${#existing[@]}-1]";
        if ((${#COMPREPLY[@]})); then
            local x i;
            for x in ${existing+"${existing[@]}"};
            do
                for i in "${!COMPREPLY[@]}";
                do
                    if [[ $x == "${COMPREPLY[i]}" ]]; then
                        unset -v 'COMPREPLY[i]';
                        continue 2;
                    fi;
                done;
            done;
            ((${#COMPREPLY[@]})) && _comp_compgen -c "${cur##*"$delimiter"}" -- -W '"${COMPREPLY[@]}"';
        fi;
    else
        _comp_compgen -c "${cur##*"$delimiter"}" -- "$@";
    fi;
    local i;
    for i in "${!COMPREPLY[@]}";
    do
        COMPREPLY[i]="$prefix${COMPREPLY[i]}";
    done;
    [[ $delimiter != : ]] || _comp_ltrim_colon_completions "$cur"
}
_comp_deprecate_func ()
{
    if (($# != 3)); then
        printf 'bash_completion: %s: usage: %s DEPRECATION_VERSION OLD_NAME NEW_NAME\n' "$FUNCNAME" "$FUNCNAME";
        return 2;
    fi;
    if [[ $2 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
        printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$2: invalid function name '$1'" 1>&2;
        return 2;
    else
        if [[ $3 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
            printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$3: invalid function name '$2'" 1>&2;
            return 2;
        fi;
    fi;
    eval -- "$2() { $3 \"\$@\"; }"
}
_comp_deprecate_var ()
{
    if (($# != 3)); then
        printf 'bash_completion: %s: usage: %s DEPRECATION_VERSION OLD_NAME NEW_NAME\n' "$FUNCNAME" "$FUNCNAME";
        return 2;
    fi;
    if [[ $2 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
        printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$2: invalid variable name '$1'" 1>&2;
        return 2;
    else
        if [[ $3 != [a-zA-Z_]*([a-zA-Z_0-9]) ]]; then
            printf 'bash_completion: %s: %s\n' "$FUNCNAME" "\$3: invalid variable name '$2'" 1>&2;
            return 2;
        fi;
    fi;
    if ((BASH_VERSINFO[0] >= 5 || BASH_VERSINFO[0] == 4 && BASH_VERSINFO[1] >= 3)); then
        eval "declare -gn $2=$3";
    else
        if [[ -v $2 && ! -v $3 ]]; then
            printf -v "$3" %s "$2";
        fi;
    fi
}
_comp_dequote ()
{
    REPLY=();
    [[ $1 =~ $_comp_dequote__regex_safe_word ]] || return 1;
    eval "REPLY=($1)" 2> /dev/null
}
_comp_expand ()
{
    case ${cur-} in
        ~*/*)
            local REPLY;
            _comp_expand_tilde "$cur";
            cur=$REPLY
        ;;
        ~*)
            _comp_compgen -v COMPREPLY tilde && eval "COMPREPLY[0]=$(printf ~%q "${COMPREPLY[0]#\~}")" && return 1
        ;;
    esac;
    return 0
}
_comp_expand_glob ()
{
    if (($# != 2)); then
        printf 'bash-completion: %s: unexpected number of arguments\n' "$FUNCNAME" 1>&2;
        printf 'usage: %s ARRAY_NAME PATTERN\n' "$FUNCNAME" 1>&2;
        return 2;
    else
        if [[ $1 == @(GLOBIGNORE|GLOBSORT|_*|*[^_a-zA-Z0-9]*|[0-9]*|'') ]]; then
            printf 'bash-completion: %s: invalid array name "%s"\n' "$FUNCNAME" "$1" 1>&2;
            return 2;
        fi;
    fi;
    local _original_opts=$SHELLOPTS:$BASHOPTS;
    set +o noglob;
    shopt -s nullglob;
    shopt -u failglob dotglob;
    local GLOBIGNORE="" GLOBSORT=name;
    local LC_COLLATE=C LC_CTYPE=${LC_ALL:-${LC_CTYPE:-${LANG-}}} LC_ALL=;
    eval -- "$1=()";
    eval -- "$1=($2)";
    _comp_unlocal GLOBIGNORE;
    if [[ :$_original_opts: == *:dotglob:* ]]; then
        shopt -s dotglob;
    else
        shopt -u dotglob;
    fi;
    [[ :$_original_opts: == *:nullglob:* ]] || shopt -u nullglob;
    [[ :$_original_opts: == *:failglob:* ]] && shopt -s failglob;
    [[ :$_original_opts: == *:noglob:* ]] && set -o noglob;
    eval "((\${#$1[@]}))"
}
_comp_expand_tilde ()
{
    REPLY=$1;
    if [[ $1 == \~* ]]; then
        printf -v REPLY '~%q' "${1#\~}";
        eval "REPLY=$REPLY";
    fi
}
_comp_get_first_arg ()
{
    _comp_locate_first_arg "$@" && REPLY=${words[REPLY]}
}
_comp_get_ncpus ()
{
    local var=NPROCESSORS_ONLN;
    [[ $OSTYPE == *@(linux|msys|cygwin)* ]] && var=_$var;
    if REPLY=$(getconf $var 2> /dev/null) && ((REPLY >= 1)); then
        return 0;
    else
        REPLY=1;
        return 1;
    fi
}
_comp_get_words ()
{
    local exclude="" flag i OPTIND=1;
    local cur cword words=();
    local upargs=() upvars=() vcur="" vcword="" vprev="" vwords="";
    while getopts "c:i:n:p:w:" flag "$@"; do
        case $flag in
            [cipw])
                if [[ $OPTARG != [a-zA-Z_]*([a-zA-Z_0-9])?(\[*\]) ]]; then
                    echo "bash_completion: $FUNCNAME: -$flag: invalid variable name \`$OPTARG'" 1>&2;
                    return 1;
                fi
            ;;&
            c)
                vcur=$OPTARG
            ;;
            i)
                vcword=$OPTARG
            ;;
            n)
                exclude=$OPTARG
            ;;
            p)
                vprev=$OPTARG
            ;;
            w)
                vwords=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 1
            ;;
        esac;
    done;
    while [[ $# -ge $OPTIND ]]; do
        case ${!OPTIND} in
            cur)
                vcur=cur
            ;;
            prev)
                vprev=prev
            ;;
            cword)
                vcword=cword
            ;;
            words)
                vwords=words
            ;;
            *)
                echo "bash_completion: $FUNCNAME: \`${!OPTIND}':" "unknown argument" 1>&2;
                return 1
            ;;
        esac;
        ((OPTIND += 1));
    done;
    _comp__get_cword_at_cursor "${exclude-}" words cword cur;
    [[ -n $vcur ]] && {
        upvars+=("$vcur");
        upargs+=(-v "$vcur" "$cur")
    };
    [[ -n $vcword ]] && {
        upvars+=("$vcword");
        upargs+=(-v "$vcword" "$cword")
    };
    [[ -n $vprev ]] && {
        local value="";
        ((cword >= 1)) && value=${words[cword - 1]};
        upvars+=("$vprev");
        upargs+=(-v "$vprev" "$value")
    };
    [[ -n $vwords ]] && {
        local IFS='
';
        upvars+=("$vwords");
        upargs+=(-a"${#words[@]}" "$vwords" ${words+"${words[@]}"})
    };
    ((${#upvars[@]})) && local "${upvars[@]}" && _comp_upvars "${upargs[@]}"
}
_comp_have_command ()
{
    PATH=$PATH:/usr/sbin:/sbin:/usr/local/sbin type "$1" &> /dev/null
}
_comp_initialize ()
{
    local exclude="" opt_split="" outx="" errx="" inx="";
    local flag OPTIND=1 OPTARG="" OPTERR=0;
    while getopts "n:e:o:i:s" flag "$@"; do
        case $flag in
            n)
                exclude+=$OPTARG
            ;;
            e)
                errx=$OPTARG
            ;;
            o)
                outx=$OPTARG
            ;;
            i)
                inx=$OPTARG
            ;;
            s)
                opt_split="set";
                was_split="";
                exclude+="="
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 1
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    (($#)) && comp_args=("$@");
    COMPREPLY=();
    local redir='@(?(+([0-9])|{[a-zA-Z_]*([a-zA-Z_0-9])})@(>?([>|&])|<?([>&])|<<?([-<]))|&>?(>))';
    _comp_get_words -n "$exclude<>&" cur prev words cword;
    _comp_compgen_variables && return 1;
    if [[ $cur == $redir* || ${prev-} == $redir ]]; then
        local xspec;
        case $cur in
            2'>'*)
                xspec=${errx-}
            ;;
            *'>'*)
                xspec=${outx-}
            ;;
            *'<'*)
                xspec=${inx-}
            ;;
            *)
                case $prev in
                    2'>'*)
                        xspec=${errx-}
                    ;;
                    *'>'*)
                        xspec=${outx-}
                    ;;
                    *'<'*)
                        xspec=${inx-}
                    ;;
                esac
            ;;
        esac;
        cur=${cur##$redir};
        _comp_compgen_filedir "$xspec";
        return 1;
    fi;
    local i skip;
    for ((i = 1; i < ${#words[@]}; 1))
    do
        if [[ ${words[i]} == $redir* ]]; then
            [[ ${words[i]} == $redir ]] && skip=2 || skip=1;
            words=("${words[@]:0:i}" "${words[@]:i+skip}");
            ((i <= cword)) && ((cword -= skip));
        else
            ((i++));
        fi;
    done;
    ((cword <= 0)) && return 1;
    prev=${words[cword - 1]};
    [[ -n $opt_split ]] && _comp__split_longopt && was_split="set";
    return 0
}
_comp_load ()
{
    local flag_fallback_default="" IFS='
';
    local OPTIND=1 OPTARG="" OPTERR=0 opt;
    while getopts ':D' opt "$@"; do
        case $opt in
            D)
                flag_fallback_default=set
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    local cmd=$1 cmdname=${1##*/} dir compfile;
    local -a paths;
    [[ -n $cmdname ]] || return 1;
    local backslash=;
    if [[ $cmd == \\* ]]; then
        cmd=${cmd:1};
        $(complete -p -- "$cmd" 2> /dev/null || echo false) "\\$cmd" && return 0;
        backslash=\\;
    fi;
    local REPLY pathcmd origcmd=$cmd;
    if pathcmd=$(type -P -- "$cmd"); then
        _comp_abspath "$pathcmd";
        cmd=$REPLY;
    fi;
    local -a dirs=();
    if [[ -n ${BASH_COMPLETION_USER_DIR-} ]]; then
        _comp_split -F : paths "$BASH_COMPLETION_USER_DIR" && dirs+=("${paths[@]/%//completions}");
    else
        dirs=("${XDG_DATA_HOME:-$HOME/.local/share}/bash-completion/completions");
    fi;
    dirs+=("$_comp__base_directory/completions");
    paths=();
    [[ $cmd == /* ]] && paths+=("${cmd%/*}");
    _comp_realcommand "$cmd" && paths+=("${REPLY%/*}");
    _comp_split -aF : paths "$PATH";
    for dir in "${paths[@]%/}";
    do
        [[ $dir == ?*/@(bin|sbin) ]] && dirs+=("${dir%/*}/share/bash-completion/completions");
    done;
    _comp_split -F : paths "${XDG_DATA_DIRS:-/usr/local/share:/usr/share}" && dirs+=("${paths[@]/%//bash-completion/completions}");
    local IFS='
';
    shift;
    local i prefix compspec;
    for prefix in "" _;
    do
        for i in ${!dirs[*]};
        do
            dir=${dirs[i]};
            if [[ ! -d $dir ]]; then
                unset -v 'dirs[i]';
                continue;
            fi;
            for compfile in "$prefix$cmdname" "$prefix$cmdname.bash";
            do
                compfile="$dir/$compfile";
                if [[ -d $compfile ]]; then
                    [[ $compfile == */.?(.) ]] || echo "bash_completion: $compfile: is a directory" 1>&2;
                else
                    if [[ -e $compfile ]] && . "$compfile" "$cmd" "$@"; then
                        if compspec=$(complete -p -- "$cmd" 2> /dev/null); then
                            [[ -n $backslash ]] && eval "$compspec \"\$backslash\$cmd\"";
                            [[ $origcmd != */* ]] && ! complete -p -- "$origcmd" &> /dev/null && eval "$compspec \"\$origcmd\"";
                            return 0;
                        fi;
                        if [[ $cmdname != "$cmd" ]] && compspec=$(complete -p -- "$cmdname" 2> /dev/null); then
                            [[ $cmd == /* ]] && eval "$compspec \"\$cmd\"";
                            return 0;
                        fi;
                    fi;
                fi;
            done;
        done;
    done;
    [[ -v _comp_xspecs[$cmdname] || -v _xspecs[$cmdname] ]] && complete -F _comp_complete_filedir_xspec "$cmdname" "$backslash$cmdname" && return 0;
    if [[ -n $flag_fallback_default ]]; then
        complete -F _comp_complete_minimal -- "$origcmd" && return 0;
    fi;
    return 1
}
_comp_locate_first_arg ()
{
    local has_optarg="";
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':a:' _opt "$@"; do
        case $_opt in
            a)
                has_optarg=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    local i;
    REPLY=;
    for ((i = 1; i < cword; i++))
    do
        if [[ -n $has_optarg && ${words[i]} == $has_optarg ]]; then
            ((i++));
        else
            if [[ ${words[i]} != -?* ]]; then
                REPLY=$i;
                return 0;
            else
                if [[ ${words[i]} == -- ]]; then
                    ((i + 1 < cword)) && REPLY=$((i + 1)) && return 0;
                    break;
                fi;
            fi;
        fi;
    done;
    return 1
}
_comp_looks_like_path ()
{
    [[ ${1-} == @(*/|[.~])* ]]
}
_comp_ltrim_colon_completions ()
{
    ((${#COMPREPLY[@]})) || return 0;
    _comp_compgen -c "$1" ltrim_colon "${COMPREPLY[@]}"
}
_comp_quote ()
{
    REPLY=\'${1//\'/\'\\\'\'}\'
}
_comp_quote_compgen ()
{
    if [[ $1 == \'* ]]; then
        REPLY=${1:1};
    else
        printf -v REPLY %q "$1";
        if [[ $REPLY == \$\'*\' ]]; then
            local value=${REPLY:2:-1};
            value=${value//'%'/%%};
            printf -v REPLY "$value";
        fi;
    fi
}
_comp_readline_variable_on ()
{
    [[ $(bind -v) == *$1+([[:space:]])on* ]]
}
_comp_realcommand ()
{
    REPLY="";
    local file;
    file=$(type -P -- "$1") || return $?;
    if type -p realpath > /dev/null; then
        REPLY=$(realpath "$file");
    else
        if type -p greadlink > /dev/null; then
            REPLY=$(greadlink -f "$file");
        else
            if type -p readlink > /dev/null; then
                REPLY=$(readlink -f "$file");
            else
                _comp_abspath "$file";
            fi;
        fi;
    fi
}
_comp_root_command ()
{
    local PATH=$PATH:/sbin:/usr/sbin:/usr/local/sbin;
    local _comp_root_command=$1;
    _comp_command
}
_comp_split ()
{
    local _append="" IFS='
';
    local OPTIND=1 OPTARG="" OPTERR=0 _opt;
    while getopts ':alF:' _opt "$@"; do
        case $_opt in
            a)
                _append=set
            ;;
            l)
                IFS='
'
            ;;
            F)
                IFS=$OPTARG
            ;;
            *)
                echo "bash_completion: $FUNCNAME: usage error" 1>&2;
                return 2
            ;;
        esac;
    done;
    shift "$((OPTIND - 1))";
    if (($# != 2)); then
        printf '%s\n' "bash_completion: $FUNCNAME: unexpected number of arguments" 1>&2;
        printf '%s\n' "usage: $FUNCNAME [-al] [-F SEP] ARRAY_NAME TEXT" 1>&2;
        return 2;
    else
        if [[ $1 == @(*[^_a-zA-Z0-9]*|[0-9]*|''|_*|IFS|OPTIND|OPTARG|OPTERR) ]]; then
            printf '%s\n' "bash_completion: $FUNCNAME: invalid array name '$1'" 1>&2;
            return 2;
        fi;
    fi;
    local _original_opts=$SHELLOPTS;
    set -o noglob;
    local _old_size _new_size;
    if [[ -n $_append ]]; then
        eval "$1+=()";
        eval "_old_size=\${#$1[@]}";
        eval "$1+=(\$2)";
    else
        _old_size=0;
        eval "$1=(\$2)";
    fi;
    eval "_new_size=\${#$1[@]}";
    [[ :$_original_opts: == *:noglob:* ]] || set +o noglob;
    ((_new_size > _old_size))
}
_comp_sysvdirs ()
{
    sysvdirs=();
    [[ -d /etc/rc.d/init.d ]] && sysvdirs+=(/etc/rc.d/init.d);
    [[ -d /etc/init.d ]] && sysvdirs+=(/etc/init.d);
    [[ -f /etc/slackware-version ]] && sysvdirs=(/etc/rc.d);
    ((${#sysvdirs[@]}))
}
_comp_try_faketty ()
{
    if type unbuffer &> /dev/null; then
        unbuffer -p "$@";
    else
        if script --version 2>&1 | command grep -qF util-linux; then
            script -qaefc "$*" /dev/null;
        else
            "$@";
        fi;
    fi
}
_comp_unlocal ()
{
    if ((BASH_VERSINFO[0] >= 5)) && shopt -q localvar_unset; then
        shopt -u localvar_unset;
        unset -v "$@";
        shopt -s localvar_unset;
    else
        unset -v "$@";
    fi
}
_comp_upvars ()
{
    if ! (($#)); then
        echo "bash_completion: $FUNCNAME: usage: $FUNCNAME" "[-v varname value] | [-aN varname [value ...]] ..." 1>&2;
        return 2;
    fi;
    while (($#)); do
        case $1 in
            -a*)
                [[ -n ${1#-a} ]] || {
                    echo "bash_completion: $FUNCNAME:" "\`$1': missing number specifier" 1>&2;
                    return 1
                };
                printf %d "${1#-a}" &> /dev/null || {
                    echo bash_completion: "$FUNCNAME: \`$1': invalid number specifier" 1>&2;
                    return 1
                };
                [[ -n $2 ]] && unset -v "$2" && eval "$2"=\(\"\$"{@:3:${1#-a}}"\"\) && shift $((${1#-a} + 2)) || {
                    echo bash_completion: "$FUNCNAME: \`$1${2+ }$2': missing argument(s)" 1>&2;
                    return 1
                }
            ;;
            -v)
                [[ -n $2 ]] && unset -v "$2" && eval "$2"=\"\$3\" && shift 3 || {
                    echo "bash_completion: $FUNCNAME: $1:" "missing argument(s)" 1>&2;
                    return 1
                }
            ;;
            *)
                echo "bash_completion: $FUNCNAME: $1: invalid option" 1>&2;
                return 1
            ;;
        esac;
    done
}
_comp_userland ()
{
    local userland=$(uname -s);
    [[ $userland == @(Linux|GNU/*) ]] && userland=GNU;
    [[ $userland == "$1" ]]
}
_comp_variable_assignments ()
{
    local cur=${1-} i;
    if [[ $cur =~ ^([A-Za-z_][A-Za-z0-9_]*)=(.*)$ ]]; then
        prev=${BASH_REMATCH[1]};
        cur=${BASH_REMATCH[2]};
    else
        return 1;
    fi;
    case $prev in
        TZ)
            cur=/usr/share/zoneinfo/$cur;
            _comp_compgen_filedir;
            if ((${#COMPREPLY[@]})); then
                for i in "${!COMPREPLY[@]}";
                do
                    if [[ ${COMPREPLY[i]} == *.tab ]]; then
                        unset -v 'COMPREPLY[i]';
                        continue;
                    else
                        if [[ -d ${COMPREPLY[i]} ]]; then
                            COMPREPLY[i]+=/;
                            compopt -o nospace;
                        fi;
                    fi;
                    COMPREPLY[i]=${COMPREPLY[i]#/usr/share/zoneinfo/};
                done;
            fi
        ;;
        TERM)
            _comp_compgen_terms
        ;;
        LANG | LC_*)
            _comp_compgen_split -- "$(locale -a 2> /dev/null)"
        ;;
        LANGUAGE)
            _comp_delimited : -W '$(locale -a 2>/dev/null)'
        ;;
        *)
            _comp_compgen_variables && return 0;
            _comp_compgen -a filedir
        ;;
    esac;
    return 0
}
_comp_xfunc ()
{
    local xfunc_name=$2;
    [[ $xfunc_name == _* ]] || xfunc_name=_comp_xfunc_${1//[^a-zA-Z0-9_]/_}_$xfunc_name;
    declare -F -- "$xfunc_name" &> /dev/null || _comp_load -- "$1";
    "$xfunc_name" "${@:3}"
}
_complete_as_root ()
{
    _comp_as_root "$@"
}
_completion_loader ()
{
    _comp_complete_load "$@"
}
_configured_interfaces ()
{
    _comp_compgen_configured_interfaces "$@"
}
_count_args ()
{
    local i cword words;
    _comp__reassemble_words "${1-}" words cword;
    args=1;
    for ((i = 1; i < cword; i++))
    do
        if [[ ${words[i]} != -* && ${words[i - 1]} != ${2-} || ${words[i]} == ${3-} ]]; then
            ((args++));
        fi;
    done
}
_dvd_devices ()
{
    _comp_compgen -a dvd_devices
}
_expand ()
{
    _comp_expand "$@"
}
_filedir ()
{
    _comp_compgen -a filedir "$@"
}
_filedir_xspec ()
{
    _comp_complete_filedir_xspec "$@"
}
_fstypes ()
{
    _comp_compgen -a fstypes
}
_get_comp_words_by_ref ()
{
    _comp_get_words "$@"
}
_get_cword ()
{
    local LC_CTYPE=C;
    local cword words;
    _comp__reassemble_words "${1-}" words cword;
    if [[ -n ${2-} && -n ${2//[^0-9]/} ]]; then
        printf "%s" "${words[cword - $2]}";
    else
        if ((${#words[cword]} == 0 && COMP_POINT == ${#COMP_LINE})); then
            :;
        else
            local i;
            local cur=$COMP_LINE;
            local index=$COMP_POINT;
            for ((i = 0; i <= cword; ++i))
            do
                while [[ ${#cur} -ge ${#words[i]} && ${cur:0:${#words[i]}} != "${words[i]}" ]]; do
                    cur=${cur:1};
                    ((index > 0)) && ((index--));
                done;
                if ((i < cword)); then
                    local old_size=${#cur};
                    cur=${cur#"${words[i]}"};
                    local new_size=${#cur};
                    ((index -= old_size - new_size));
                fi;
            done;
            if [[ ${words[cword]:0:${#cur}} != "$cur" ]]; then
                printf "%s" "${words[cword]}";
            else
                printf "%s" "${cur:0:index}";
            fi;
        fi;
    fi
}
_get_first_arg ()
{
    local i;
    arg=;
    for ((i = 1; i < COMP_CWORD; i++))
    do
        if [[ ${COMP_WORDS[i]} != -* ]]; then
            arg=${COMP_WORDS[i]};
            break;
        fi;
    done
}
_get_pword ()
{
    if ((COMP_CWORD >= 1)); then
        _get_cword "${@-}" 1;
    fi
}
_gids ()
{
    _comp_compgen_gids "$@"
}
_have ()
{
    _comp_have_command "$@"
}
_init_completion ()
{
    local was_split;
    _comp_initialize "$@";
    local rc=$?;
    local flag OPTIND=1 OPTARG="" OPTERR=0;
    while getopts "n:e:o:i:s" flag "$@"; do
        case $flag in
            [neoi])

            ;;
            s)
                if [[ -n $was_split ]]; then
                    split=true;
                else
                    split=false;
                fi;
                break
            ;;
        esac;
    done;
    return "$rc"
}
_installed_modules ()
{
    _comp_compgen_inserted_kernel_modules "$@"
}
_ip_addresses ()
{
    _comp_compgen_ip_addresses "$@"
}
_kernel_versions ()
{
    _comp_compgen_kernel_versions "$@"
}
_known_hosts ()
{
    _comp_complete_known_hosts "$@"
}
_known_hosts_real ()
{
    _comp_compgen_known_hosts "$@"
}
_longopt ()
{
    _comp_complete_longopt "$@"
}
_mac_addresses ()
{
    _comp_compgen_mac_addresses "$@"
}
_minimal ()
{
    _comp_complete_minimal "$@"
}
_modules ()
{
    _comp_compgen_kernel_modules "$@"
}
_ncpus ()
{
    local REPLY;
    _comp_get_ncpus;
    printf %s "$REPLY"
}
_parse_help ()
{
    local -a args;
    if [[ $1 == - ]]; then
        args=(-);
    else
        local REPLY opt IFS='
';
        _comp_dequote "$1";
        _comp_split opt "${2:---help}";
        args=(-c "$REPLY" ${opt[@]+"${opt[@]}"});
    fi;
    local -a REPLY=();
    _comp_compgen -Rv REPLY help "${args[@]}" || return 1;
    ((${#REPLY[@]})) && printf '%s\n' "${REPLY[@]}";
    return 0
}
_parse_usage ()
{
    local -a args;
    if [[ $1 == - ]]; then
        args=(-);
    else
        local REPLY opt IFS='
';
        _comp_dequote "$1";
        _comp_split opt "${2:---usage}";
        args=(-c "$REPLY" ${opt[@]+"${opt[@]}"});
    fi;
    local -a REPLY=();
    _comp_compgen -Rv REPLY usage "${args[@]}" || return 1;
    ((${#REPLY[@]})) && printf '%s\n' "${REPLY[@]}";
    return 0
}
_pci_ids ()
{
    _comp_compgen -a pci_ids
}
_pgids ()
{
    _comp_compgen_pgids "$@"
}
_pids ()
{
    _comp_compgen_pids "$@"
}
_pnames ()
{
    _comp_compgen_pnames "$@"
}
_quote_readline_by_ref ()
{
    [[ $2 == REPLY ]] || local REPLY;
    _comp_quote_compgen "$1";
    [[ $2 == REPLY ]] || printf -v "$2" %s "$REPLY"
}
_realcommand ()
{
    local REPLY;
    _comp_realcommand "$1";
    local rc=$?;
    printf "%s\n" "$REPLY";
    return $rc
}
_rl_enabled ()
{
    _comp_readline_variable_on "$@"
}
_root_command ()
{
    _comp_root_command "$@"
}
_service ()
{
    _comp_complete_service "$@"
}
_services ()
{
    _comp_compgen_services "$@"
}
_shells ()
{
    _comp_compgen -a shells
}
_signals ()
{
    _comp_compgen_signals "$@"
}
_sysvdirs ()
{
    _comp_sysvdirs "$@"
}
_terms ()
{
    _comp_compgen -a terms
}
_tilde ()
{
    ! _comp_compgen -c "$1" tilde
}
_uids ()
{
    _comp_compgen_uids "$@"
}
_upvar ()
{
    echo "bash_completion: $FUNCNAME: deprecated function," "use _comp_upvars instead" 1>&2;
    if unset -v "$1"; then
        if (($# == 2)); then
            eval "$1"=\"\$2\";
        else
            eval "$1"=\(\"\$"{@:2}"\"\);
        fi;
    fi
}
_upvars ()
{
    _comp_upvars "$@"
}
_usb_ids ()
{
    _comp_compgen -a usb_ids
}
_user_at_host ()
{
    _comp_complete_user_at_host "$@"
}
_usergroup ()
{
    _comp_compgen_usergroups "$@"
}
_userland ()
{
    _comp_userland "$@"
}
_variables ()
{
    _comp_compgen_variables "$@"
}
_xfunc ()
{
    _comp_xfunc "$@"
}
_xinetd_services ()
{
    _comp_compgen_xinetd_services "$@"
}
command_not_found_handle ()
{
    if [ -x /usr/lib/command-not-found ]; then
        /usr/lib/command-not-found -- "$1";
        return $?;
    else
        if [ -x /usr/share/command-not-found/command-not-found ]; then
            /usr/share/command-not-found/command-not-found -- "$1";
            return $?;
        else
            printf "%s: command not found\n" "$1" 1>&2;
            return 127;
        fi;
    fi
}
dequote ()
{
    local REPLY;
    _comp_dequote "$1";
    local rc=$?;
    printf %s "$REPLY";
    return $rc
}
quote ()
{
    local quoted=${1//\'/\'\\\'\'};
    printf "'%s'" "$quoted"
}
quote_readline ()
{
    local REPLY;
    _comp_quote_compgen "$1";
    printf %s "$REPLY"
}
ossau@LAPTOP-2HK683AM:~$ echo $user

ossau@LAPTOP-2HK683AM:~$ echo $USER
ossau
ossau@LAPTOP-2HK683AM:~$ ls -l
total 8
drwxr-xr-x 2 ossau ossau 4096 Nov 17 11:11 pracatice
drwxr-xr-x 2 ossau ossau 4096 Nov 17 11:12 practice
ossau@LAPTOP-2HK683AM:~$ ls -ln
total 8
drwxr-xr-x 2 1000 1000 4096 Nov 17 11:11 pracatice
drwxr-xr-x 2 1000 1000 4096 Nov 17 11:12 practice
ossau@LAPTOP-2HK683AM:~$ ls -la pracatice
total 8
drwxr-xr-x 2 ossau ossau 4096 Nov 17 11:11 .
drwxr-x--- 7 ossau ossau 4096 Nov 17 15:00 ..
ossau@LAPTOP-2HK683AM:~$ ls -la practice
total 12
drwxr-xr-x 2 ossau ossau 4096 Nov 17 11:12 .
drwxr-x--- 7 ossau ossau 4096 Nov 17 15:00 ..
-rw-r--r-- 1 ossau ossau   31 Nov 17 11:19 notes.txt
ossau@LAPTOP-2HK683AM:~$ rmdir pracatice
ossau@LAPTOP-2HK683AM:~$ ls
practice
ossau@LAPTOP-2HK683AM:~$ ls -l
total 4
drwxr-xr-x 2 ossau ossau 4096 Nov 17 11:12 practice
ossau@LAPTOP-2HK683AM:~$ ls -ln
total 4
drwxr-xr-x 2 1000 1000 4096 Nov 17 11:12 practice
ossau@LAPTOP-2HK683AM:~$ cat notes.txt
cat: notes.txt: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cat notes.txt
I'm learning Linux notes.txt q
ossau@LAPTOP-2HK683AM:~/practice$ nano notes.txt
ossau@LAPTOP-2HK683AM:~/practice$ cat notes.txt
I'm mastering Linux Command Line

ossau@LAPTOP-2HK683AM:~/practice$ echo "fuck" > notes.txt
ossau@LAPTOP-2HK683AM:~/practice$ cat notes.txt
fuck
ossau@LAPTOP-2HK683AM:~/practice$ aptitude moo
Command 'aptitude' not found, but can be installed with:
sudo apt install aptitude
ossau@LAPTOP-2HK683AM:~/practice$ cd ~
ossau@LAPTOP-2HK683AM:~$ aptitude moo
Command 'aptitude' not found, but can be installed with:
sudo apt install aptitude
ossau@LAPTOP-2HK683AM:~$ sudo apt install aptitude
[sudo: authenticate] Password:
Installing:
  aptitude

Installing dependencies:
  aptitude-common  libboost-iostreams1.90.0  libdpkg-perl            libsigc++-2.0-0v5
  bzip2            libcwidget4               libfile-fcntllock-perl  libxapian30

Suggested packages:
  apt-xapian-index  | aptitude-doc  tasksel    libcwidget-dev  debian-tag2upload-keyring  | c-compiler  xapian-tools
  aptitude-doc-en   debtags         bzip2-doc  debian-keyring  gcc                        bzr

Summary:
  Upgrading: 0, Installing: 9, Removing: 0, Not Upgrading: 4
  Download size: 4675 kB
  Space needed: 21.5 MB / 1024 GB available

Continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu resolute/universe amd64 aptitude-common all 0.8.13-7ubuntu5 [1793 kB]
Get:2 http://archive.ubuntu.com/ubuntu resolute/main amd64 libboost-iostreams1.90.0 amd64 1.90.0-6ubuntu1 [253 kB]
Get:3 http://archive.ubuntu.com/ubuntu resolute/main amd64 libsigc++-2.0-0v5 amd64 2.12.1-4build1 [13.1 kB]
Get:4 http://archive.ubuntu.com/ubuntu resolute/universe amd64 libcwidget4 amd64 0.5.18-6build2 [246 kB]
Get:5 http://archive.ubuntu.com/ubuntu resolute/universe amd64 libxapian30 amd64 1.4.31-2 [754 kB]
Get:6 http://archive.ubuntu.com/ubuntu resolute/universe amd64 aptitude amd64 0.8.13-7ubuntu5 [1259 kB]
Get:7 http://archive.ubuntu.com/ubuntu resolute-updates/main amd64 bzip2 amd64 1.0.8-6ubuntu0.1 [34.3 kB]
Get:8 http://archive.ubuntu.com/ubuntu resolute/main amd64 libdpkg-perl all 1.23.7ubuntu1 [289 kB]
Get:9 http://archive.ubuntu.com/ubuntu resolute/main amd64 libfile-fcntllock-perl amd64 0.22-4ubuntu6 [32.8 kB]
Fetched 4675 kB in 10s (459 kB/s)
Selecting previously unselected package aptitude-common.
(Reading database ... 35979 files and directories currently installed.)
Preparing to unpack .../0-aptitude-common_0.8.13-7ubuntu5_all.deb ...
Unpacking aptitude-common (0.8.13-7ubuntu5) ...
Selecting previously unselected package libboost-iostreams1.90.0:amd64.
Preparing to unpack .../1-libboost-iostreams1.90.0_1.90.0-6ubuntu1_amd64.deb ...
Unpacking libboost-iostreams1.90.0:amd64 (1.90.0-6ubuntu1) ...
Selecting previously unselected package libsigc++-2.0-0v5:amd64.
Preparing to unpack .../2-libsigc++-2.0-0v5_2.12.1-4build1_amd64.deb ...
Unpacking libsigc++-2.0-0v5:amd64 (2.12.1-4build1) ...
Selecting previously unselected package libcwidget4:amd64.
Preparing to unpack .../3-libcwidget4_0.5.18-6build2_amd64.deb ...
Unpacking libcwidget4:amd64 (0.5.18-6build2) ...
Selecting previously unselected package libxapian30:amd64.
Preparing to unpack .../4-libxapian30_1.4.31-2_amd64.deb ...
Unpacking libxapian30:amd64 (1.4.31-2) ...
Selecting previously unselected package aptitude.
Preparing to unpack .../5-aptitude_0.8.13-7ubuntu5_amd64.deb ...
Unpacking aptitude (0.8.13-7ubuntu5) ...
Selecting previously unselected package bzip2.
Preparing to unpack .../6-bzip2_1.0.8-6ubuntu0.1_amd64.deb ...
Unpacking bzip2 (1.0.8-6ubuntu0.1) ...
Selecting previously unselected package libdpkg-perl.
Preparing to unpack .../7-libdpkg-perl_1.23.7ubuntu1_all.deb ...
Unpacking libdpkg-perl (1.23.7ubuntu1) ...
Selecting previously unselected package libfile-fcntllock-perl.
Preparing to unpack .../8-libfile-fcntllock-perl_0.22-4ubuntu6_amd64.deb ...
Unpacking libfile-fcntllock-perl (0.22-4ubuntu6) ...
Setting up libxapian30:amd64 (1.4.31-2) ...
Setting up libfile-fcntllock-perl (0.22-4ubuntu6) ...
Setting up bzip2 (1.0.8-6ubuntu0.1) ...
Setting up libsigc++-2.0-0v5:amd64 (2.12.1-4build1) ...
Setting up aptitude-common (0.8.13-7ubuntu5) ...
Setting up libdpkg-perl (1.23.7ubuntu1) ...
Setting up libboost-iostreams1.90.0:amd64 (1.90.0-6ubuntu1) ...
Setting up libcwidget4:amd64 (0.5.18-6build2) ...
Setting up aptitude (0.8.13-7ubuntu5) ...
update-alternatives: using /usr/bin/aptitude-curses to provide /usr/bin/aptitude (aptitude) in auto mode
Processing triggers for man-db (2.13.1-1build1) ...
Processing triggers for libc-bin (2.43-2ubuntu2.7) ...
ossau@LAPTOP-2HK683AM:~$ aptitude moo
There are no Easter Eggs in this program.
ossau@LAPTOP-2HK683AM:~$ aptitude -vv moo
Didn't I already tell you that there are no Easter Eggs in this program?
ossau@LAPTOP-2HK683AM:~$ aptitude -vv mooaptitude -vv moo
Unknown command "mooaptitude"
aptitude 0.8.13
Usage: aptitude [-S fname] [-u|-i]
       aptitude [options] <action> ...

Actions (if none is specified, aptitude will enter interactive mode):

 install         Install/upgrade packages.
 remove          Remove packages.
 purge           Remove packages and their configuration files.
 hold            Place packages on hold.
 unhold          Cancel a hold command for a package.
 markauto        Mark packages as having been automatically installed.
 unmarkauto      Mark packages as having been manually installed.
 forbid-version  Forbid aptitude from upgrading to a specific package version.
 update          Download lists of new/upgradable packages.
 safe-upgrade    Perform a safe upgrade.
 full-upgrade    Perform an upgrade, possibly installing and removing packages.
 build-dep       Install the build-dependencies of packages.
 forget-new      Forget what packages are "new".
 search          Search for a package by name and/or expression.
 show            Display detailed info about a package.
 showsrc         Display detailed info about a source package (apt wrapper).
 versions        Displays the versions of specified packages.
 clean           Erase downloaded package files.
 autoclean       Erase old downloaded package files.
 changelog       View a package's changelog.
 download        Download the .deb file for a package (apt wrapper).
 source          Download source package (apt wrapper).
 reinstall       Reinstall a currently installed package.
 why             Explain why a particular package should be installed.
 why-not         Explain why a particular package cannot be installed.

 add-user-tag    Add user tag to packages/patterns.
 remove-user-tag Remove user tag from packages/patterns.

Options:
 -h              This help text.
 --no-gui        Do not use the GTK GUI even if available.
 -s              Simulate actions, but do not actually perform them.
 -d              Only download packages, do not install or remove anything.
 -P              Always prompt for confirmation of actions.
 -y              Assume that the answer to simple yes/no questions is 'yes'.
 -F format       Specify a format for displaying search results; see the manual.
 -O order        Specify how search results should be sorted; see the manual.
 -w width        Specify the display width for formatting search results.
 -f              Aggressively try to fix broken packages.
 -V              Show which versions of packages are to be installed.
 -D              Show the dependencies of automatically changed packages.
 -Z              Show the change in installed size of each package.
 -v              Display extra information. (may be supplied multiple times).
 -t [release]    Set the release from which packages should be installed.
 -q              In command-line mode, suppress the incremental progress
                  indicators.
 -o key=val      Directly set the configuration option named 'key'.
 --with(out)-recommends     Specify whether or not to treat recommends as
                            strong dependencies.
 -S fname        Read the aptitude extended status info from fname.
 -u              Download new package lists on startup.
                  (terminal interface only)
 -i              Perform an install run on startup.
                  (terminal interface only)

See the manual page for a complete list and description of all the options.

This aptitude does not have Super Cow Powers.
ossau@LAPTOP-2HK683AM:~$ aptitude -vvvvv moo
All right, you win.

                               /----\
                       -------/      \
                      /               \
                     /                |
   -----------------/                  --------\
   ----------------------------------------------
ossau@LAPTOP-2HK683AM:~$ aptitude -vvvvv moo
All right, you win.

                               /----\
                       -------/      \
                      /               \
                     /                |
   -----------------/                  --------\
   ----------------------------------------------
ossau@LAPTOP-2HK683AM:~$ ls -ln
total 4
drwxr-xr-x 2 1000 1000 4096 Nov 17 17:04 practice
ossau@LAPTOP-2HK683AM:~$ pwd -l
bash: pwd: -l: invalid option
pwd: usage: pwd [-LP]
ossau@LAPTOP-2HK683AM:~$ pwd [-l]
/home/ossau
ossau@LAPTOP-2HK683AM:~$ pwd -L
/home/ossau
ossau@LAPTOP-2HK683AM:~$ pwd -P
/home/ossau
ossau@LAPTOP-2HK683AM:~$ pwd -r
bash: pwd: -r: invalid option
pwd: usage: pwd [-LP]
ossau@LAPTOP-2HK683AM:~$ pwd -y
bash: pwd: -y: invalid option
pwd: usage: pwd [-LP]
ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ etc
Command 'etc' not found, did you mean:
  command 'dtc' from snap device-tree-compiler (1.6.1)
  command 'etm' from deb etm (3.2.39-2)
  command 'htc' from deb httptunnel (3.3+dfsg-6build1)
  command 'dtc' from deb device-tree-compiler (1.7.2-2ubuntu1)
  command 'tc' from deb iproute2 (6.19.0-1ubuntu1.1)
  command 'etr' from deb extremetuxracer (0.8.4-2)
  command 'rtc' from deb nvram-wakeup (1.1-5build1)
  command 'atc' from deb bsdgames (2.17-35)
  command 'etcd' from deb etcd-server (3.5.16-10)
  command 'ttc' from deb chordpro (6.090.1+ds-1)
  command 'eta' from deb eta (1.0.1-1)
  command 'qtc' from deb golang-github-valyala-quicktemplate-dev (1.8.0+ds1-2)
See 'snap info <snapname>' for additional versions.
ossau@LAPTOP-2HK683AM:~$ /etc/calendar
bash: /etc/calendar: No such file or directory
ossau@LAPTOP-2HK683AM:~$ ~$
~$: command not found
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ cd Documents
bash: cd: Documents: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd notes.txt
bash: cd: notes.txt: Not a directory
ossau@LAPTOP-2HK683AM:~/practice$ /home/practice
bash: /home/practice: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cd /home/ossau
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd notes
bash: cd: notes: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cat notes.txt
fuck
ossau@LAPTOP-2HK683AM:~/practice$ cd ~
ossau@LAPTOP-2HK683AM:~$ cat notes.txt
cat: notes.txt: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ pwd
/home/ossau/practice
ossau@LAPTOP-2HK683AM:~/practice$ cd ~
ossau@LAPTOP-2HK683AM:~$ cd ossau
bash: cd: ossau: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ mkdir testing
ossau@LAPTOP-2HK683AM:~/practice$ cd testing
ossau@LAPTOP-2HK683AM:~/practice/testing$ cd ..
ossau@LAPTOP-2HK683AM:~/practice$ pwd
/home/ossau/practice
ossau@LAPTOP-2HK683AM:~/practice$ cd ~
ossau@LAPTOP-2HK683AM:~$ ~ testing
bash: /home/ossau: Is a directory
ossau@LAPTOP-2HK683AM:~$ ~testing
~testing: command not found
ossau@LAPTOP-2HK683AM:~$ ~/testing
bash: /home/ossau/testing: No such file or directory
ossau@LAPTOP-2HK683AM:~$ ~/testing.
bash: /home/ossau/testing.: No such file or directory
ossau@LAPTOP-2HK683AM:~$ ~/practice
bash: /home/ossau/practice: Is a directory
ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ ~/testing
bash: /home/ossau/testing: No such file or directory
ossau@LAPTOP-2HK683AM:~$ ~/testing.
bash: /home/ossau/testing.: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd testing
bash: cd: testing: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd ~/testing
bash: cd: /home/ossau/testing: No such file or directory
ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ ls -la~
error: unexpected argument '-~' found

  tip: to pass '-~' as a value, use '-- -~'

Usage: ls [OPTION]... [FILE]...

For more information, try '--help'.
ossau@LAPTOP-2HK683AM:~$ ls -la ~
total 44
drwxr-x--- 6 ossau ossau 4096 Nov 17 16:59 .
drwxr-xr-x 3 root  root  4096 Nov 16 16:15 ..
-rw------- 1 ossau ossau  174 Nov 17 09:37 .bash_history
-rw-r--r-- 1 ossau ossau  220 Nov 16 16:15 .bash_logout
-rw-r--r-- 1 ossau ossau 3771 Nov 16 16:15 .bashrc
drwxr-x--- 4 ossau ossau 4096 Nov 16 16:17 .cache
drwxr-x--- 3 ossau ossau 4096 Nov 16 16:17 .config
-rw------- 1 ossau ossau   20 Nov 16 16:24 .lesshst
drwx------ 3 ossau ossau 4096 Nov 17 14:59 .local
-rw-rw-r-- 1 ossau ossau    0 Nov 17 09:32 .motd_shown
-rw-r--r-- 1 ossau ossau  807 Nov 16 16:15 .profile
drwxr-xr-x 3 ossau ossau 4096 Nov 19 10:01 practice
ossau@LAPTOP-2HK683AM:~$ ~/practice
bash: /home/ossau/practice: Is a directory
ossau@LAPTOP-2HK683AM:~$ cd~
Command 'cd~' not found, did you mean:
  command 'cdi' from deb cdo (2.5.4-1)
  command 'cdv' from deb erlang-observer (1:27.3.4.6+dfsg-1)
  command 'cdp' from deb irpas (0.10-10build1)
  command 'cde' from deb cde (0.1+git9-g551e54d-3)
  command 'cdw' from deb cdw (0.8.1-3build4)
  command 'cdo' from deb cdo (2.5.4-1)
  command 'cdb' from deb tinycdb (0.81-2build1)
  command 'cd5' from deb cd5 (0.1-4build1)
Try: sudo apt install <deb name>
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ /home/practice/
bash: /home/practice/: No such file or directory
ossau@LAPTOP-2HK683AM:~$ ossau/practice
bash: ossau/practice: No such file or directory
ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ cd.
Command 'cd.' not found, did you mean:
  command 'cdb' from deb tinycdb (0.81-2build1)
  command 'cdw' from deb cdw (0.8.1-3build4)
  command 'cdi' from deb cdo (2.5.4-1)
  command 'cd5' from deb cd5 (0.1-4build1)
  command 'cdp' from deb irpas (0.10-10build1)
  command 'cde' from deb cde (0.1+git9-g551e54d-3)
  command 'cdo' from deb cdo (2.5.4-1)
  command 'cdv' from deb erlang-observer (1:27.3.4.6+dfsg-1)
Try: sudo apt install <deb name>
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ ls -d ~/testing
ls: cannot access '/home/ossau/testing': No such file or directory
ossau@LAPTOP-2HK683AM:~$ ls -d ~/practice/testing
/home/ossau/practice/testing
ossau@LAPTOP-2HK683AM:~$ mv ~/practice/testing ~/
ossau@LAPTOP-2HK683AM:~$ ~/testing
bash: /home/ossau/testing: Is a directory
ossau@LAPTOP-2HK683AM:~$ ls -d ~/testing
/home/ossau/testing
ossau@LAPTOP-2HK683AM:~$ ls -d ~/practice/testing
ls: cannot access '/home/ossau/practice/testing': No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ ls -d ~/practice/testing
ls: cannot access '/home/ossau/practice/testing': No such file or directory
ossau@LAPTOP-2HK683AM:~$ ~/testing
bash: /home/ossau/testing: Is a directory
ossau@LAPTOP-2HK683AM:~$ ls -d ~/testing
/home/ossau/testing
ossau@LAPTOP-2HK683AM:~$ mv ~/practice/testing ~/
mv: cannot stat '/home/ossau/practice/testing': No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd ~
ossau@LAPTOP-2HK683AM:~$ find / -type d name testing 2>/dev/null
ossau@LAPTOP-2HK683AM:~$ cd testing
ossau@LAPTOP-2HK683AM:~/testing$ cd ~
ossau@LAPTOP-2HK683AM:~$ ls -d ~/testing
/home/ossau/testing
ossau@LAPTOP-2HK683AM:~$ cd ~/testing
ossau@LAPTOP-2HK683AM:~/testing$ cd ~
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd testing
bash: cd: testing: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cd
ossau@LAPTOP-2HK683AM:~$ whoami
ossau
ossau@LAPTOP-2HK683AM:~$ cd
ossau@LAPTOP-2HK683AM:~$ cd ~/testing
ossau@LAPTOP-2HK683AM:~/testing$ cd
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd testing
bash: cd: testing: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cd ~/testing
ossau@LAPTOP-2HK683AM:~/testing$ cd
ossau@LAPTOP-2HK683AM:~$ /etc
bash: /etc: Is a directory
ossau@LAPTOP-2HK683AM:~$ cd ~/testing
ossau@LAPTOP-2HK683AM:~/testing$ pwd
/home/ossau/testing
ossau@LAPTOP-2HK683AM:~/testing$ cd
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ cd /
ossau@LAPTOP-2HK683AM:/$ cd $
bash: cd: $: No such file or directory
ossau@LAPTOP-2HK683AM:/$ cd
ossau@LAPTOP-2HK683AM:~$ ls src/
ls: cannot access 'src/': No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ ls src/
ls: cannot access 'src/': No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cat ../config.yml
cat: ../config.yml: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cd
ossau@LAPTOP-2HK683AM:~$ cat ../config.yml
cat: ../config.yml: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd ~/testing
ossau@LAPTOP-2HK683AM:~/testing$ pwd
/home/ossau/testing
ossau@LAPTOP-2HK683AM:~/testing$ ls ~
practice  testing
ossau@LAPTOP-2HK683AM:~/testing$ cd ~
ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ eco $USER
Command 'eco' not found, did you mean:
  command 'peco' from snap peco (v0.5.3)
  command 'ego' from snap ego-dev (1.11.0)
  command 'ecj' from deb ecj (3.35.0+eclipse4.29-2build1)
  command 'co' from deb rcs (5.10.1-3)
  command 'tco' from deb flang (1:21.1.6-71)
  command 'ecl' from deb ecl (24.5.10.20250914.git294da20+dfsg-3)
  command 'ico' from deb x11-apps (7.7+11build4)
  command 'echo' from deb coreutils-from-gnu (0.0.0~ubuntu25)
  command 'echo' from deb coreutils-from-uutils (0.0.0~ubuntu25)
  command 'echo' from deb coreutils-from-busybox (0.0.0~ubuntu25)
  command 'echo' from deb coreutils-from-toybox (0.0.0~ubuntu25)
  command 'ecm' from deb gmp-ecm (7.0.6+ds-2)
  command 'peco' from deb peco (0.5.10-1build2)
See 'snap info <snapname>' for additional versions.
ossau@LAPTOP-2HK683AM:~$ echo $USER
ossau
ossau@LAPTOP-2HK683AM:~$ pwd
/home/ossau
ossau@LAPTOP-2HK683AM:~$ cd testing
ossau@LAPTOP-2HK683AM:~/testing$ pwd
/home/ossau/testing
ossau@LAPTOP-2HK683AM:~/testing$ cd practice
bash: cd: practice: No such file or directory
ossau@LAPTOP-2HK683AM:~/testing$ cd..
cd..: command not found
ossau@LAPTOP-2HK683AM:~/testing$ cd ..
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd testing
bash: cd: testing: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cd notes
bash: cd: notes: No such file or directory
ossau@LAPTOP-2HK683AM:~/practice$ cd ..
ossau@LAPTOP-2HK683AM:~$ cd testing
ossau@LAPTOP-2HK683AM:~/testing$ cd practice
bash: cd: practice: No such file or directory
ossau@LAPTOP-2HK683AM:~/testing$ mkdir test1
ossau@LAPTOP-2HK683AM:~/testing$ cd test1
ossau@LAPTOP-2HK683AM:~/testing/test1$ cd ..
ossau@LAPTOP-2HK683AM:~/testing$ cd ..
ossau@LAPTOP-2HK683AM:~$ cd testing
ossau@LAPTOP-2HK683AM:~/testing$ cd test1
ossau@LAPTOP-2HK683AM:~/testing/test1$ cd~
Command 'cd~' not found, did you mean:
  command 'cdb' from deb tinycdb (0.81-2build1)
  command 'cd5' from deb cd5 (0.1-4build1)
  command 'cdp' from deb irpas (0.10-10build1)
  command 'cde' from deb cde (0.1+git9-g551e54d-3)
  command 'cdw' from deb cdw (0.8.1-3build4)
  command 'cdo' from deb cdo (2.5.4-1)
  command 'cdi' from deb cdo (2.5.4-1)
  command 'cdv' from deb erlang-observer (1:27.3.4.6+dfsg-1)
Try: sudo apt install <deb name>
ossau@LAPTOP-2HK683AM:~/testing/test1$ cd \~
bash: cd: ~: No such file or directory
ossau@LAPTOP-2HK683AM:~/testing/test1$ cd ~
ossau@LAPTOP-2HK683AM:~$ ls
practice  testing
ossau@LAPTOP-2HK683AM:~$  ls -l
total 8
drwxr-xr-x 2 ossau ossau 4096 Nov 20 14:35 practice
drwxr-xr-x 3 ossau ossau 4096 Nov 21 21:03 testing
ossau@LAPTOP-2HK683AM:~$ ls -l
total 8
drwxr-xr-x 2 ossau ossau 4096 Nov 20 14:35 practice
drwxr-xr-x 3 ossau ossau 4096 Nov 21 21:03 testing
ossau@LAPTOP-2HK683AM:~$ la -t
testing  practice  .local  .bash_history  .motd_shown  .lesshst  .cache  .config  .profile  .bashrc  .bash_logout
ossau@LAPTOP-2HK683AM:~$ ls -lt
total 8
drwxr-xr-x 3 ossau ossau 4096 Nov 21 21:03 testing
drwxr-xr-x 2 ossau ossau 4096 Nov 20 14:35 practice
ossau@LAPTOP-2HK683AM:~$ cd practice
ossau@LAPTOP-2HK683AM:~/practice$ cd ..
ossau@LAPTOP-2HK683AM:~$ ls -S
practice  testing
ossau@LAPTOP-2HK683AM:~$ ls -l -S
total 8
drwxr-xr-x 2 ossau ossau 4096 Nov 20 14:35 practice
drwxr-xr-x 3 ossau ossau 4096 Nov 21 21:03 testing
ossau@LAPTOP-2HK683AM:~$ ls -r
testing  practice
ossau@LAPTOP-2HK683AM:~$ ls -lSr
total 8
drwxr-xr-x 3 ossau ossau 4096 Nov 21 21:03 testing
drwxr-xr-x 2 ossau ossau 4096 Nov 20 14:35 practice
ossau@LAPTOP-2HK683AM:~$ -r
-r: command not found
ossau@LAPTOP-2HK683AM:~$ ls -r
testing  practice
ossau@LAPTOP-2HK683AM:~$ su -
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su --login
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ home
Command 'home' not found, did you mean:
  command 'hose' from deb netpipes (4.2-8.1build1)
  command 'jome' from deb jome (1.4.1-1)
  command 'hime' from deb hime (0.9.11+git20231221.g1c15f1f+dfsg-2)
Try: sudo apt install <deb name>
ossau@LAPTOP-2HK683AM:~$ /home
bash: /home: Is a directory
ossau@LAPTOP-2HK683AM:~$ home/
bash: home/: No such file or directory
ossau@LAPTOP-2HK683AM:~$ cd ~
ossau@LAPTOP-2HK683AM:~$ su -
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ su -l
Password:
su: Authentication failure
ossau@LAPTOP-2HK683AM:~$ password
Command 'password' not found, did you mean:
  command '1password' from snap 1password (8.11.14)
  command '5password' from snap 5password (0.3)
See 'snap info <snapname>' for additional versions.
ossau@LAPTOP-2HK683AM:~$ sudo su -
[sudo: authenticate] Password:
Welcome to Ubuntu 26.04.1 LTS (GNU/Linux 6.18.58.1-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://docs.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Sun Nov 22 21:55:10 -05 2026

  System load:  0.0                 Processes:             38
  Usage of /:   0.2% of 1006.85GB   Users logged in:       2
  Memory usage: 10%                 IPv4 address for eth0: 192.168.243.93
  Swap usage:   0%

  => /usr/src/linux-headers-6.18.58.1-microsoft-standard-WSL2 is using 100.0%
     of 96MB

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

This message is shown once a day. To disable it please create the
/root/.hushlogin file.
root@LAPTOP-2HK683AM:~# sl
Command 'sl' not found, but can be installed with:
apt install sl
root@LAPTOP-2HK683AM:~# apt install sl
Installing:
  sl

Installing dependencies:
  libncurses6

Summary:
  Upgrading: 0, Installing: 2, Removing: 0, Not Upgrading: 4
  Download size: 127 kB
  Space needed: 406 kB / 1024 GB available

Continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu resolute/main amd64 libncurses6 amd64 6.6+20251231-1 [114 kB]
Get:2 http://archive.ubuntu.com/ubuntu resolute/universe amd64 sl amd64 5.02-1build1 [12.9 kB]
Fetched 127 kB in 17s (7347 B/s)
Selecting previously unselected package libncurses6:amd64.
(Reading database ... 36466 files and directories currently installed.)
Preparing to unpack .../libncurses6_6.6+20251231-1_amd64.deb ...
Unpacking libncurses6:amd64 (6.6+20251231-1) ...
Selecting previously unselected package sl.
Preparing to unpack .../sl_5.02-1build1_amd64.deb ...
Unpacking sl (5.02-1build1) ...
Setting up libncurses6:amd64 (6.6+20251231-1) ...
Setting up sl (5.02-1build1) ...
Processing triggers for man-db (2.13.1-1build1) ...
Processing triggers for libc-bin (2.43-2ubuntu2.7) ...
root@LAPTOP-2HK683AM:~# sl

root@LAPTOP-2HK683AM:~# la -la
total 20
drwx------  3 root root 4096 Nov 22 21:55 .
drwxr-xr-x 19 root root 4096 Nov 17 09:32 ..
-rw-r--r--  1 root root 3106 Apr 20  2026 .bashrc
-rw-r--r--  1 root root    0 Nov 22 21:55 .motd_shown
-rw-r--r--  1 root root  132 Apr 20  2026 .profile
drwx------  2 root root 4096 Aug 27 09:11 .ssh
root@LAPTOP-2HK683AM:~# ls -la
total 20
drwx------  3 root root 4096 Nov 22 21:55 .
drwxr-xr-x 19 root root 4096 Nov 17 09:32 ..
-rw-r--r--  1 root root 3106 Apr 20  2026 .bashrc
-rw-r--r--  1 root root    0 Nov 22 21:55 .motd_shown
-rw-r--r--  1 root root  132 Apr 20  2026 .profile
drwx------  2 root root 4096 Aug 27 09:11 .ssh
root@LAPTOP-2HK683AM:~# la -ls
total 12
4 -rw-r--r-- 1 root root 3106 Apr 20  2026 .bashrc
0 -rw-r--r-- 1 root root    0 Nov 22 21:55 .motd_shown
4 -rw-r--r-- 1 root root  132 Apr 20  2026 .profile
4 drwx------ 2 root root 4096 Aug 27 09:11 .ssh
root@LAPTOP-2HK683AM:~# exit
logout
ossau@LAPTOP-2HK683AM:~$ lsblk
NAME MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda    8:0    0 722.9M  1 disk
sdb    8:16   0  97.4M  1 disk /usr/src/linux-headers-6.18.58.1-microsoft-standard-WSL2
sdc    8:32   0     2G  0 disk [SWAP]
sdd    8:48   0     1T  0 disk /mnt/wslg/distro
                               /
ossau@LAPTOP-2HK683AM:~$ sudo su -
[sudo: authenticate] Password:
sudo: Authentication failed, try again.
[sudo: authenticate] Password:
Welcome to Ubuntu 26.04.1 LTS (GNU/Linux 6.18.58.1-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://docs.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Mon Nov 23 07:47:10 -05 2026

  System load:  0.01                Processes:             39
  Usage of /:   0.2% of 1006.85GB   Users logged in:       2
  Memory usage: 10%                 IPv4 address for eth0: 192.168.243.93
  Swap usage:   0%

  => /usr/src/linux-headers-6.18.58.1-microsoft-standard-WSL2 is using 100.0%
     of 96MB

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

This message is shown once a day. To disable it please create the
/root/.hushlogin file.
root@LAPTOP-2HK683AM:~# exit
logout
ossau@LAPTOP-2HK683AM:~$ sudo passwd root
[sudo: authenticate] Password:
sudo: Authentication failed, try again.
[sudo: authenticate] Password:
New password:
Retype new password:
passwd: password updated successfully
ossau@LAPTOP-2HK683AM:~$ su
Password:
root@LAPTOP-2HK683AM:/home/ossau# exit
exit
ossau@LAPTOP-2HK683AM:~$


