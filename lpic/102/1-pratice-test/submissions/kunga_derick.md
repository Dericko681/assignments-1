1. `journalctl`
2. `/etc/resolv.conf`
3. password aging
4. ServerName:Allow
5. ::1
6. -R
7. LD_LIBRARY_PATH
8. `systemctl stop ssh.service`
9. `route`
10. `/var/spool/cron/crontabs`
11. B
12. c
13. c
14. B
15. c
16. C
17. B
18. A
19. B
20. B
21. 0 2 * * FRI ./backup.sh
22. a soft link can point to files in a different file system whereas a hardlink cannot point to files on a different system. deleting the target doesn't affect the hardlink while deleting the target affetcs the symlink rendering it broken. to create  hard link `ln -T target linkname` `ln -s linkname target`
23.  to configure eth0, use the command `sudo ifconfig eth0 up`
    /etc/network/interfaces  ```sh
   auto eth0
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1
    dns-nameservers 8.8.8.8 8.8.4.4
```
24.   ```sh
    sudo find /home/user -type f -exec chmod 0644 ()
    sudo find /home/user -type d exec chmod 0755 ()
    ```
25.  the /etc/nsswitch.conf is used to set the rules for name resolution. example; `passwd:         files systemd`
26.  ```sh
     groupadd sshusers
     sudo nano /etc/ssh/sshd_config
     AllowGroups sshusers
     sudo systemctl restart ssh
     ```
27.  ufw is used to manage netfilter firewall while iptables is an administration tool for IPv4/IPv6 packet filtering
       and NAT
