# Linux-Firewalld-rules
Nautilus system admins team just deployed a web UI application for their backup utility running on Nautilus backup server in Stratos Datacenter. The application is running on port 6300 . They have firewalld installed on that server. Some requirements have came up as mentioned below.   

#### Open all incoming connection on 8087/tcp port. Zone should be public.

##### Login to backup-server and switch to root user.


      `systemctl status firewalld
       firewall-cmd --zone=public --list-all
       firewall-cmd --zone=public --list-ports
       firewall-cmd --permanent --zone=public --add-port=6300/tcp
       firewall-cmd --reload
       systemctl restart firewalld
       firewall-cmd --zone=public --list-all
       firewall-cmd --zone=public --list-ports`
