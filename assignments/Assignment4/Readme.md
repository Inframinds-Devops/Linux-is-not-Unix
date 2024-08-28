# User Management and File Permission Task Documentation

1. Create a User with Your First Name
   Command:
   sudo useradd -m vahant
   This command creates a user named Abdul with a home directory.

2. Create a System User for a Service with Your Last Name
   Command:
   sudo useradd -r -s /usr/sbin/nologin sharma
   This command creates a system user named Vahant for service purposes, with no interactive login shell.

3. Remove Home Directory Information for the Last Name User
   Remove the existing home directory if it exists:
   Command:
   sudo rm -rf /home/sharma
   This command deletes the user's home directory if it exists.
   
   Update the user’s home directory to `/nonexistent`:
   Command:
   sudo usermod -d /nonexistent sharma
   This command sets the user’s home directory to `/nonexistent`.

4. Remove Login Shell for the Last Name User
   Command:
   sudo usermod -s /usr/sbin/nologin sharma
   This command removes the login shell for the user by setting it to `nologin`.

5. Create User Rahul and Ensure a Default File `file1` is in His Home Directory
   Create the user:
   Command:
   sudo useradd -m Rahul
   This command creates the user Rahul with a home directory.
   
   Create the file `file1` in Rahul's home directory:
   Command:
   sudo touch /home/Rahul/file1
   This command creates an empty file named `file1` in Rahul's home directory.
   
   Set the correct ownership for the file:
   Command:
   sudo chown Rahul:Rahul /home/Rahul/file1
   This command sets the ownership of `file1` to the user Rahul.