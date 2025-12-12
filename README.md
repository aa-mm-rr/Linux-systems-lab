# Linux Systems & Network Services Lab
Mariia Tufar

## Overview
This project demonstrates practical knowledge in Linux system administration, networking, virtualization, and service deployment. The work was carried out using multiple virtual machines to simulate real-world scenarios of system setup, secure communication, file sharing, and service hosting.

## Skills Demonstrated
- Linux system installation, updates, and package management
- Secure remote access with SSH and key-based authentication
- Hostname and IP configuration for multi-VM environments
- Directory sharing with NFS and Samba, including SELinux and firewall adjustments
- Archive creation, compression, transfer, and extraction across VMs
- Web server deployment with Apache, user directories, and access control
- Cron-based automation and scripting for system monitoring
- SELinux context management and troubleshooting service access
- Documentation of reproducible workflows and error resolution

## Tools Used
- Fedora Linux VMs, SSH, SCP, NFS, Samba, Apache, Cockpit
- SELinux, firewall-cmd, cron, shell scripting, tar/gzip/bzip2

## Environment Setup
- Two Linux VMs created: `mariiaat.mariia.lab` and `friend.mariia.lab`
- Hostnames configured with `hostnamectl`
- IP addresses assigned and mapped in `/etc/hosts`
- Verified connectivity with `ping`

## Secure Access
- Installed and enabled SSH server
- Configured firewall for SSH
- Generated and deployed SSH keys for passwordless login
- Tested access with PuTTY and Cockpit web interface

## File Sharing
### NFS
- Installed `nfs-utils`
- Created `/nfs/share` directory on `mariiaat`
- Configured `/etc/exports` for `friend.mariia.lab`
- Enabled and tested NFS server
- Mounted share on `friend` VM and verified file creation
- Made mount permanent via `/etc/fstab`

### Samba
- Installed Samba packages
- Configured `/mnt/share` with proper permissions
- Edited `smb.conf` to define `[myshare]`
- Adjusted firewall and SELinux contexts
- Created Samba user and tested access with `smbclient`

## Archiving & Transfer
- Created and extracted archives using `tar`, `gzip`, and `bzip2`
- Transferred archives between VMs using `scp`
- Deployed web content from archives to Apache server
- Configured permissions and SELinux contexts for web access

## Web Services
- Installed and configured Apache HTTP Server
- Enabled user directories (`~public_html`)
- Applied SELinux policies for home directories
- Created `.htaccess` with `htpasswd` for protected content
- Changed DocumentRoot to `/var/newroot` and applied SELinux contexts
- Verified service availability via `curl`

## Automation
- Installed Python and created shell scripts
- Configured cron jobs to log timestamps every minute
- Verified execution via `cron_test.log` and system logs

## Security & Troubleshooting
- Applied SELinux contexts with `semanage` and `restorecon`
- Configured firewall services for SSH, HTTP, NFS, Samba
- Used Fail2ban and access controls to secure services
- Documented troubleshooting steps (e.g., localhost access issue)
