# Linux Commands Tasks

## Task 3: Permissions Management

**Create a file with your first name**
    - Command: vim vahant.txt

**Ensure that file can only be modified by you**
    - Command: chmod 700 vahant.txt
    - Command: chmod u=rwx,g=,o= vahant.txt

**Now update the capability where a set of trusted people can read & modify the file but not execute it**\
    - Command: chmod 760 vahant.txt
    - Command: chmod u=rwx,g=rw,o= vahant.txt

**As a last step let any user to read the file**
    - Command: chmod 761 vahant.txt
    - Command: chmod u=rwx,g=rw,o=r vahant.txt



## Task 4: User Management
**Create a new user with first name**
    -Command: sudo useradd Vahant

**Create another user with your lastname representing service**\
    -Command: sudo useradd -r Sharma

**Remove home directory information for lastname user**
    -Command: sudo rm -rf /home/Sharma

**Remove login shell for lastname user**
    -Command: sudo usermod -s /bin/false Sharma

**List both the users**
    -Command: cut -d: -f1 /etc/passwd

**Create user Rahul. By default file1 should be present in home directory of Rahul user.**
    -Command: sudo useradd Rahul
    -Command: sudo touch /home/Rahul/file1
    -Command: sudo chmod 644 /home/Rahul/file1

**Do cleanup**
    -Command: sudo userdel -r Vahant
              sudo userdel -r Rahul
              sudo userdel Sharma