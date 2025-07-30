# 📁 File & Directory Operations

This section contains essential commands and examples for working with files and directories, based on my learning from the Hack The Box Academy *Linux Fundamentals* module.

---

## 🛠 Basic File & Directory Commands

- `touch filename.txt`  
  → Create a new file.

- `mkdir FolderName`  
  → Create a new directory.

- `mkdir -p path/to/folder`  
  → Create nested directories.

- `mv oldname.txt newname.txt`  
  → Rename a file or move it to another location.

- `mv file.txt Folder/`  
  → Move a file into a directory.

- `cp file.txt Folder/`  
  → Copy a file to another location.

- `tree .`  
  → Display the directory structure of the current folder.

- `rm file.txt`  
  → Delete a file.

- `rmdir FolderName`  
  → Remove an empty directory.

- `rm -r FolderName`  
  → Remove a directory and its contents.

---

## 🧪 Practice Task: Create File and Directory Structure

```bash
touch info.txt
mkdir Storage
mkdir -p Storage/local/user/documents
tree .
