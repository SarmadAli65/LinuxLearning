🐧 Linux Commands & Concepts Cheat Sheet
This document captures Linux commands I've learned so far, along with explanations and examples.

📁 File & Directory Navigation
 * ls
    - Lists contents of the current directory

    - .-R: Recursively lists nested directories

    - .ls nonexistent 2> error.txt: Redirects error output to a file

    - .ls 'name' 2> /dev/null: Suppresses error messages

 * pwd
    - Prints the current working directory

 * cd 'directory'
    - Changes directory

    - cd ..: Move up one level

    - cd ~: Go to the home directory

    - cd "My Project": Use quotes for directories with spaces

📂 Creating & Deleting Files/Directories
 * mkdir 'folder'
    - Creates a new directory

    - mkdir .folder: Creates a hidden directory

    - mkdir -p project/src/components: Creates nested directories

    - mkdir "My Project": Handles spaces with quotes

rmdir 'folder'
Removes an empty directory

rm 'file'
Deletes a file

rm -r 'folder': Deletes a non-empty directory

touch 'file.txt'
Creates a new file

📥 File Content & Redirection
echo "message" > file
Writes a message to a file (overwrites existing)

>>: Appends instead of overwriting

cat 'file'
Views file contents

cat file1 file2 > newfile: Combine files

cat < -: Handles dash-named files

grep "text" file
Searches for text in a file

head 'file'
Shows first 10 lines

head -n 5 file: Show first 5 lines

tail 'file'
Shows last 10 lines

tail -n 5 file: Show last 5 lines

Combine with head using | for advanced control

strings data.txt | grep =
Extracts printable strings from a binary file and finds lines containing =

🧭 Copying & Moving
cp file1 file2
Copies content from file1 to file2

cp -r dir1 dir2: Copies entire directories

mv old new
Renames or moves files

mv file dir/: Moves file to a directory

🔐 Permissions & Ownership
sudo
Runs commands with elevated privileges

sudo !!: Re-runs the last command with sudo

sudo su: Switch to root user

chmod
Changes file/directory permissions

Symbolic: chmod u+x,g+r,o-w file.txt

Octal: chmod 750 file.txt

Grouped: chmod ug=rw,o=r file.txt

chown
Changes file owner

sudo chown user file.txt

sudo chown user:group file.txt: Changes both

sudo chown -R user:group dir/: Recursive

chgrp
Changes group ownership

sudo chgrp group file.txt

👥 Users & Groups
User Management
sudo useradd user: Adds a user

sudo passwd user: Sets user password

sudo usermod -aG sudo user: Grants sudo

sudo deluser user sudo: Removes sudo

su - user: Switches to user

Group Management
sudo groupadd group: Creates group

sudo groupdel group: Deletes group

sudo usermod -aG group user: Adds user to group

sudo gpasswd -d user group: Removes user from group

sudo usermod -aG group1,group2 user: Adds user to multiple groups
