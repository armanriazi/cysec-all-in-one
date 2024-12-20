# PAM (Pluggable Authentication Modules)

### User Management

PAM manages user authentication for various services in Linux. Passwords are stored in `/etc/shadow`, which contains hashed passwords.

### Security Patching on Linux

Always ensure your system is up-to-date with the latest security patches.

```bash
# Update source list to include Debian security updates
sudo nano /etc/apt/sources.list
deb http://security.debian.org/ jessie/updates main contrib non-free

# Update package list and upgrade installed packages
sudo aptitude update && sudo aptitude upgrade

# Check the status of a specific package (e.g., libgnutls-openssl27)
apt-cache policy libgnutls-openssl27
```

##### Basic PAM Configuration

To configure a specific service (e.g., `git-shell`):

```bash
sudo nano /etc/pam.d/git-shell
# Add these lines:
auth required pam_unix.so  
account required pam_unix.so
```

##### Common PAM Configurations

The `common-auth`, `common-account`, and `common-password` files include configurations for all services.

```bash
# View the common-auth configuration
grep -v "^#" /etc/pam.d/common-auth

# Ensure the following line is included in your SSHD config
sudo nano /etc/pam.d/sshd
@include common-auth

# Common password handling configuration
sudo nano /etc/pam.d/common-password
@include common-password
```

#### Password Management

##### Restrict User from Using Old Password

To prevent users from reusing past passwords:

```bash
sudo nano /etc/pam.d/common-password
# Add this line to ensure passwords are remembered
password sufficient pam_unix.so use_authok md5 shadow remember=10
```

##### Set Password Expiration Policies

Use the `chage` command to enforce password expiry rules:

```bash
chage -l arman # Check current expiration settings
sudo chage -M 60 -m 7 -W 3 arman # Set max 60 days, min 7 days, warn 3 days
```

##### Enforce Strong Password Policies

Install the `libpam-pwquality` package for stronger password enforcement:

```bash
# Search for the package
aptitude search libpam-pwquality

# Configure password quality requirements
sudo nano /etc/security/pwquality.conf
minlen=9
minclass=2
maxrepeat=3
maxclassrepeat=4

# Ensure pam_pwquality is in common-password
sudo nano /etc/pam.d/common-password
# Ensure retry=3 is configured
```

### Sudo Access Management

Use the `sudo` command to provide users with elevated privileges.

#### Configure Sudoers File

Always use `visudo` to edit the sudoers file to prevent syntax errors:

```bash
# Check current sudoers file
ls -l /etc/sudoers
sudo visudo
# Ensure to change the editor if necessary
update-alternatives --config editor
```

#### Granting Access to Groups

```bash
# Add users to the sudoers file
# Example for granting specific permissions
## User privilege specification
root ALL=(ALL:ALL) ALL 
arman ALL=(ALL:ALL) ALL 
jessie ALL=(ALL)NOPASSWD: /etc/init.d/apache2 reload 

# Create a new group and manage user permissions
sudo groupadd group1
sudo adduser jessie group1

# Allow group 1 to execute updates without a password
sudo nano /etc/sudoers.d/group1
%group1 ALL=NOPASSWD: /usr/bin/apt-get update

# Define user aliases and command aliases for cleaner management
User_Alias GROUPONE = arman,jessie
Cmnd_Alias POWER = /sbin/reboot, /sbin/shutdown
GROUPONE ALL=POWER
```

#### Secure Root Login and Define Secure TTY

To prevent root from logging in directly via SSH:

```bash
# Change the shell for root to disable direct login
sudo nano /etc/passwd
# Change to:
root:x:0:0:root:/root:/sbin/nologin

# Configure securetty to restrict root login sources
sudo nano /etc/securetty
# Add only the TTY devices from which root should be allowed to log in
```

### Implementing Two-Factor Authentication (2FA)

Consider implementing 2FA for additional security layer:

```bash
# Install necessary packages
sudo apt-get install libpam-google-authenticator

# Configure for the user
google-authenticator
```

### Regular Audits and Compliance Checks

Schedule regular audits of PAM configurations, user privileges, and installed packages. Consider tools like Lynis or OpenSCAP for compliance checking.

### Checking which service using PAM

```bash
ldd /bin/login | grep libpam
whereis apache2
ldd /usr/sbin/apache2 | grep libpam
whereis git
ldd /usr/bin/git | grep libpam
```

This revised version organizes the content into clear sections with appropriate headings, corrects minor errors, and maintains all the original information while improving readability and structure.

Citations:
[1] <https://ubuntu.com/landscape/docs/pam-authentication>
[2] <https://www.tecmint.com/configure-pam-in-centos-ubuntu-linux/>
[3] <https://manpages.ubuntu.com/manpages/jammy/en/man5/pam.conf.5.html>
[4] <https://askubuntu.com/questions/513081/how-do-i-change-options-in-pam-configuration>
[5] <https://www.miniorange.com/pam/pam-ubuntu-installation-guide>
[6] <https://manpages.ubuntu.com/manpages/lunar/man7/PAM.7.html>
[7] <https://www.geeksforgeeks.org/what-is-linux-pam-module-and-how-to-configure-it/>
[8] <http://docs.pingidentity.com/pingid/pingid_integrations/pid_configuration_example_pam_ubuntu_debian.html>
[9] <https://www.digitalocean.com/community/tutorials/how-to-use-pam-to-configure-authentication-on-an-ubuntu-12-04-vps>
[10] <https://learn.microsoft.com/en-us/azure/defender-for-iot/device-builders/configure-pam-to-audit-sign-in-events>
