# FileManager.sh

`FileManager.sh` is a Bash utility script designed to manage directories. It allows users to perform various tasks related to directory management.

## Tasks the Utility Can Perform

- **Create a Directory**
- **Delete a Directory**
- **List Files in a Directory**
- **List Content of a Directory**
- **List Directories in a Directory**
- **List All Files and Directories**

## Script

```bash
#!/bin/bash

echo "Enter the command you want to execute:"
echo -e "1. Create a Directory---create\n2. Delete a Directory---delete\n3. List Content of a Directory---dirList\n4. Only list files in a Directory---onlyFiles\n5. Only list Directories in a Directory---onlyDir"
read choice

create() {
    read -p "Enter the name of the directory you want to create: " dirName
    if [ -d "/home/vahant/$dirName" ]; then
        echo "Directory already exists. Please choose a different name."
    else
        mkdir "/home/vahant/$dirName"
        if [ -d "/home/vahant/$dirName" ]; then
            echo "New Directory '$dirName' created successfully!"
        else
            echo "Failed to create the directory!"
        fi
    fi
}

delete() {
    read -p "Enter the name of the directory you want to delete: " dirName
    if [ -d "/home/vahant/$dirName" ]; then
        rm -r "/home/vahant/$dirName"
        if [ -d "/home/vahant/$dirName" ]; then
            echo "Failed to delete the directory!"
        else
            echo "Directory successfully deleted!"
        fi
    else
        echo "Directory does not exist."
        create
    fi
}

dirList() {
    read -p "Enter the name of the directory: " dirName
    if [ -d "/home/vahant/$dirName" ]; then
        echo "Showing the contents of the directory:"
        ls "/home/vahant/$dirName"
    else
        echo "Directory does not exist."
    fi
}

onlyFiles() {
    read -p "Enter the name of the directory: " dirName
    if [ -d "/home/vahant/$dirName" ]; then
        echo "Showing the files of the directory:"
        find "/home/vahant/$dirName" -maxdepth 1 -type f
    else
        echo "Directory does not exist."
    fi
}

onlyDir() {
    read -p "Enter the name of the directory: " dirName
    if [ -d "/home/vahant/$dirName" ]; then
        echo "Showing the directories within the directory:"
        find "/home/vahant/$dirName" -maxdepth 1 -type d
    else
        echo "Directory does not exist."
    fi
}

case $choice in
    create) create ;;
    delete) delete ;;
    dirList) dirList ;;
    onlyFiles) onlyFiles ;;
    onlyDir) onlyDir ;;
    *) echo "Wrong choice entered." ;;
esac
