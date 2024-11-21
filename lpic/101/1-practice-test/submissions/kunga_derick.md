1. B

2. Bios has its drivers stored in the ROM therefore updating bios firmware is difficult while the uefi has support for drivers
The BIOS has can have a maximum of 4 primary partions while the UEFI can suport up to 128
UEFI provides faster boot time compared to the BIOS

3. To determin the loaded kernel modules, use the command `lsmod`
To load a new module called dummy, use the command `modprobe dummy`

4. The `/proc` directory was used to store kernel info about processes, but this was quite disorganised and difficult for the user to fetch info about a particular process. The `/sys` dir is the modern way of storing system processes in an organised way. However, the /proc is maintained today for the purpose of backward compatibilty

5. c

6. apt is a widely used, highlevel package manager with automatic dependency resolution while dpkg is a low-level package manager with manual dependency resolution

7. To find and remove orpaned packages in ubuntu, use `sudo apt autoremove`

8. Create a new file in the /etc/yum.repos.d/ directory with a .repo extension, for example, example.repo
Open the file in a text editor and add the following configuration:
[example]
```sh
name=Example Repository
baseurl=http://repo.example.com
enabled=1
gpgcheck=0  # optional, set to 1 if you want to enable GPG signature checking

```

9. B

10. `grep -c "error" /var/log/syslog`

11. To create a hard link, use the command `ln <linkname> <targetanme>`
To create a symlink `ln -s <linkname> <targetanme>`
 The main difference between a symlink and a hardlink is that a symlink can point to files accross different file systems and directories whilst a hard link can't, it can only point to files in thesame fs.

 12. `find /etc -type f -name "*.conf" -mtime -7`

 13. The cron daemon is a process which runs in the background without the intercession of the user. It manages cron tab and job
 example of a cron job which runs everyday at modnigh `0 0 * * * /path/to/backup.sh`

 14. B

 15. `lsblk -f -o UUID`

 16.  ext4 can store larger files compared to ext3
  ext4 can reduce file fragmentation compared to ext3

17. create a new partion using fdisk command `sudo fdisk /dev/sdb`
select n to create a new partion
follow the instructions to enter a starting and ending sector and finally use the `w` to write to the disk
To make the partition an ext4 filesystem `sudo mkfs.ext4 /dev/sdb1`
Make the data directory using `mkdir /data`
To mount the filesystem on /data `sudo mount /dev/sdb1 /data`
To add permanet mount entry to fstab `sudo nano /etc/fstab` `UUID=<partition_UUID> /data ext4 defaults 0 2`

18. The /etc/fstab manages the mounting of file systems in linux
an example entry is `UUID=a67f1 /mnt/example ext4 defaults 0 2`

###bonus question

When a computer is powered on, current flows through the mother board. The POST confirms the flow of current. The BIOS firmware which is stored in the non volatile RAM contains the boot configuration in it's configuration file. The BIOS loads the bootloader(GRUB) from the first partion of the the hard disk and passes cotrol to the bootloader. The bootloader then loads the kernel and passes control to it. The kernel then loads the system libraties and system utilities to a functional operation system. The modules required by the kernel to load the OS is provides by the initranfs; a temporary file system used by the sytem to load and acces the root filesystem. When control is passed to the OS, it runs the first program, the first process with PID of 1, the parent of all processes, known as the init.
The booting process is logged to the kernel ring buffer can can be access using the dmesg command.
