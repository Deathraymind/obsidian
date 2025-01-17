- export TERM=xterm
- nano /etc/apt/sources.list
  comment out this code
- ```
  # deb cdrom://[Debian GNU/Linux 12.9.0 _Bookworm_ - Official amd64 DVD Binary-1 with firmware 20250111-10:55] bookworm main
  # add these lines 
  deb http://deb.debian.org/debian/ bookworm main
  deb-src http://deb.debian.org/debian/ bookworm main
  ```
- apt update
- apt install sudo passwd
- ```
  $ su -l
  # adduser <your_username_here> sudo
  # logout
  ```
-