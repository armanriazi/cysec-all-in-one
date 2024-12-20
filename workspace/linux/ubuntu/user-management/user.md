
# User Managmenet & Permissions

```bash
adduser "username"
userdel "username"
killall -U "username"
sudo usermod  -a -G sudo "username"
```

## Permissions

+---------+-----------+-----------+-----------+  
| Symbol  | Permission| Owner     | Group     | Other users     |  
+---------+-----------+-----------+-----------+  
| d       | Directory | r (read)  | r (read)  | r (read)   |  
| w       | Write     | w (write) | -         | -          |  
| r       | Read      | x (execute)| x (execute) | -          |  
| x       | Execute   | r (read)  | r (read)  | x (execute)|  
| -       | No access | -         | -         | -          |  
| x       | Execute   | -         | -         | x (execute)|  
+---------+-----------+-----------+-----------+  
|         |           |           |           |            |  
|         |           |   User    |   Group   |   Other    |  
+---------+-----------+-----------+-----------+

For example, `dwrx(UserOwner)-xr(Group)-x(Others)`



## User Management

```bash
# Add a new user
adduser armanriazi

# View account status and expiration information
chage -l armanriazi
```

```bash
# Remove SUID permission from a file
chmod u-s file1

# Add Sticky Bit to a file
chmod +t /test

# Add write permission for others to a file
chmod o+w /test

# Remove Sticky Bit from a file
chmod -t /test
```

### Explanation of File Permissions Commands

1. `adduser armanriazi`: Adds a new user to the system. This command prompts for various details such as full name, room number, shell, etc., unless you provide arguments.

2. `chage -l username`: Displays the last change information for a user's account. This includes password expiration details, minimum days, maximum days, warning period, and last password change.

3. `chmod u-s file1`: Removes the SUID (Set User ID) bit from the file. This prevents the file from automatically inheriting the privileges of the owner when executed.

4. `chmod +t /test`: Adds the Sticky Bit to the file. The Sticky Bit prevents users from deleting or renaming files owned by other users, even if they have write permissions.

5. `chmod o+w /test`: Adds write permissions for others to the file.

6. `chmod -t /test`: Removes the Sticky Bit from the file.

### Additional Information on Permissions

- SUID (Set User ID): When set on an executable file, it runs with the privileges of the owner rather than the executing user.
- SGID (Set Group ID): Similar to SUID but applies to group ownership.
- Sticky Bit: Prevents deletion or renaming of files owned by other users, even for those with write permissions.

These commands demonstrate various ways to modify file permissions in Linux systems. The `chmod` command is versatile and can be used with both symbolic notation (`u-s`, `-t`, `o+w`) and numeric notation (e.g., `755`).

Remember that modifying permissions should be done carefully, especially when dealing with system files or directories. Always ensure you have the necessary privileges before making changes to file permissions.

Citations:
[1] https://www.redhat.com/en/blog/suid-sgid-sticky-bit
[2] https://www.cbtnuggets.com/blog/technology/system-admin/linux-file-permissions-understanding-setuid-setgid-and-the-sticky-bit
[3] https://www.redhat.com/en/blog/linux-file-permissions-explained
[4] https://linuxhandbook.com/suid-sgid-sticky-bit/
[5] https://www.howtogeek.com/656646/how-to-use-suid-sgid-and-sticky-bits-on-linux/
[6] https://www.geeksforgeeks.org/setuid-setgid-and-sticky-bits-in-linux-file-permissions/
[7] https://www.linuxfoundation.org/blog/blog/classic-sysadmin-understanding-linux-file-permissions
[8] https://www.liquidweb.com/blog/how-do-i-set-up-setuid-setgid-and-sticky-bits-on-linux/
[9] https://learning.lpi.org/en/learning-materials/010-160/5/5.3/5.3_01/