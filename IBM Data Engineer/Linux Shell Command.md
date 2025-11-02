- **Definition of Shell**:
    - A shell is a powerful user interface for Unix-like ([[Unix & Linux]]) operating systems that interprets commands and runs programs. ([[Language for Data Engineering]])
    - It serves as both an interactive language and a scripting language.
- **Default Shell**:
    
    - The default shell on Linux systems is usually Bash (Bourne Again Shell).
    - You can check your default shell with the command:
        ```bash
        printenv SHELL
        ```
    - If needed, you can switch to Bash by entering `bash` in the command line.
- **Common Applications of Shell Commands**:
    
    - Getting information
    - Navigating and working with files and directories
    - Printing file and string contents
    - File compression and archiving
    - Performing network operations
    - Monitoring system performance
    - Running batch jobs
- **Common Shell Commands**:
    - **Information Commands**:
        - `whoami`, `id`, `uname`, `ps`, `top`, `df`, `man`, `date`
    - **File Commands**:
        - `cp`, `mv`, `rm`, `touch`, `chmod`, `wc`, `grep`
    - **Directory Commands**:
        - `ls`, `find`, `pwd`, `mkdir`, `cd`, `rmdir`
    - **Printing Commands**:
        - `cat`, `more`, `head`, `tail`, `echo`
    - **Compression Commands**:
        - `tar`, `zip`, `unzip`
    - **Networking Commands**:
        - `hostname`, `ping`, `ifconfig`, `curl`, `wget`
---
## Informational command
- **User Information Commands**:
    - `whoami`: Displays the current user's username.
    - `id`: Returns the user or group ID; options like `-u` for user ID and `-n` for name.
- **Operating System Information**:
    
    - `uname`: Provides OS information, including kernel name and version. Options like `-s` and `-r` can be used for specific details.
- **Disk Usage**:
    
    - `df`: Shows disk usage; `-h` makes the output human-readable. Can specify directories or view all filesystems.
- **Process Monitoring**:
    
    - `ps`: Displays currently running processes; `-e` lists all processes.
    - `top`: Acts as a task manager, showing running processes and their resource usage.
- **Printing Strings and Variables**:
    
    - `echo`: Displays text or variable values in the terminal.
    - Example: `echo "Learning Linux is fun!"`.
- **Date and Time**:
    
    - `date`: Displays the current date and time. Can format output using control characters.
- **Manual Pages**:
    - `man`: Displays the manual for any command, providing a summary and options.
---
## Direction folder navigation command
- **Listing Directory Contents**:
    
    - The `ls` command lists files and directories in the current directory.
    - You can specify a directory (e.g., `ls Downloads`) to list its contents.
    - The `-l` option provides detailed information about files (permissions, last-modified date, owner).
- **Current Working Directory**:
    
    - Use the `pwd` command to display your current working directory.
- **Changing Directories**:
    
    - The `cd` command changes your current directory.
    - You can use relative paths (e.g., `cd Documents`) or absolute paths (e.g., `cd /Users/me/Documents`).
    - The `..` symbol moves you to the parent directory.
    - The tilde symbol (`~`) takes you to your home directory.
- **Finding Files**:
    - The `find` command searches for files matching specified criteria.
    - Example: `find . -name 'a.txt'` searches for `a.txt` in the current directory.
    - The `-iname` option allows for case-insensitive searches.
---
## File and directory management command
- **Creating and Deleting Directories:**
    
    - Use `mkdir` to create a directory (e.g., `mkdir test`).
    - Use `rm` to remove files (e.g., `rm file1`).
    - To remove a directory and its contents, use `rm -r` (be cautious with this command).
    - For removing empty directories, use `rmdir`.
- **Creating and Modifying Files:**
    
    - Use `touch` to create empty files (e.g., `touch a.txt b.txt`).
    - `touch` can also update the last-modified date of existing files.
- **Copying and Moving Files:**
    
    - Use `cp` to copy files (e.g., `cp notes.txt Documents`).
    - To copy directories, use `cp -r` (e.g., `cp -r Documents Docs_copy`).
    - Use `mv` to move files or directories (e.g., `mv my_script.sh Scripts`).
- **Changing File Permissions:**
    - Use `chmod` to change permissions (e.g., `chmod +x my_script.sh` to make a script executable).
	File permissions can be viewed using the [`ls`](https://linuxize.com/post/how-to-list-files-in-linux-using-the-ls-command/) command:
	```
	ls -l filename.txt
	-> ```rw-r--r-- 12 linuxize users filename.txt
	```

	In the example (`rw-r--r--`) means that the file owner has read and write permissions (`rw-`), the group and others have only read permissions (`r--`).
	Permission table:
	
	| Permission | Character | Meaning              |
	| ---------- | --------- | -------------------- |
	| Read       | r         | The file is readable |
	| Write      | w         | This file can modify |
	| Execute    | x         | This file can run    |
- How to use chmod: **Text**
	The first set of flags (`[ugoa…]`), users flags, defines which users classes the permissions to the file are changed.
	- `u` - The file owner.
	- `g` - The users who are members of the group.
	- `o` - All other users.
	- `a` - All users, identical to `ugo`.
	The second set of flags (`[-+=]`), the operation flags, defines whether the permissions are to be removed, added, or set:
	- `-` Removes the specified permissions.
	- `+` Adds specified permissions.
	- `=` Changes the current permissions to the specified permissions. If no permissions are specified after the `=` symbol, all permissions from the specified user class are removed.
- How to use chmod: Numeric
	 When 3 digits number is used, the first digit represents the permissions of the file’s owner, the second one the file’s group, and the last one all other users.
	Each write, read, and execute permissions have the following number value:
	- `r` (read) = 4
	- `w` (write) = 2
	- `x` (execute) = 1
	- no permissions = 0
	Example : `chmod 754 filename.txt`
---
## View contents command
- **Commands for Viewing File Content**:
    - **cat**: Displays the entire content of a file.
        ```bash
        cat numbers.txt
        ```
    - **more**: Allows viewing a file's content page by page
        ```bash
        more numbers.txt
        ```
        - Use the space bar to go to the next page and 'Q' to quit.
    - **head**: Shows the first 10 lines of a file.
        ```bash
        head numbers.txt
        ```
        - You can specify the number of lines with the `-n` option.
        ```bash
        head -n 3 numbers.txt
        ```
    - **tail**: Displays the last 10 lines of a file.
        ```bash
        tail numbers.txt
        ```
        - You can also specify the number of lines with the `-n` option.
        ```bash
        tail -n 3 numbers.txt
        ```
- **Counting Lines, Words, and Characters**:
    - **wc**: Counts lines, words, and characters in a file.
        ```bash
        wc pets.txt
        ```
        - To count only lines, word or character, use corresponding command:
        ```bash
        wc -l pets.txt
        wc -w pets.txt
        wc -c pets.txt
        ```
---
## Wrangling text files command
- **Sorting Lines**:
    - Use the `sort` command to create a line-by-line sorted view of a file        ```bash
        sort pets.txt
        ```
        
    - To sort in reverse order, use:
        ```bash
        sort -r pets.txt
        ```
- **Removing Duplicates**:
    - The `uniq` command filters out repeated lines, but only if they are consecutive.
        
        ```bash
        uniq pets.txt
        ```
- **Pattern Matching**:
    - The `grep` command returns lines matching a specified pattern.
    - Example:
        ```bash
        grep "ch" people.txt
        ```
    - Use `-i` for case-insensitive matching:
        ```bash
        grep -i "ch" people.txt
        ```
- **Extracting Fields**:
    - The `cut` command extracts specific sections from each line.
        ```bash
        cut -c 2-9 people.txt
        ```
        
    - To extract the last name (second field) using space as a delimiter:
        ```bash
        cut -d " " -f2 people.txt
        ```
        
- **Merging Files**:
    - The `paste` command merges lines from multiple files.
    - Example:
        ```bash
        paste first.txt last.txt yob.txt
        ```
    - To specify a different delimiter (e.g., comma):
        ```bash
        paste -d "," first.txt las
        ```
---
## Networking ccommand

Use for network [[Network]]
- **hostname Command**:
    - Used to get or set the host name of your machine.
    - Running the command without options returns the current host name.
    - Options like `-s` can drop the domain suffix, and `-i` provides the IP address.
- **ifconfig Command**:
    
    - Displays information about all communication devices on your machine.
    - Running `ifconfig` without options shows details like IP address and MAC address.
    - You can specify a device (e.g., `ifconfig eth0`) to get specific information.
- **ping Command**:
    
    - Tests connectivity to a host or IP address.
    - Sends ICMP requests and listens for responses.
    - Example: `ping google.com` shows response times and packet statistics.
    - Use `-c` option to limit the number of pings (e.g., `ping -c 5 google.com`).
- **curl Command**:
    
    - Transfers data to and from URLs using various protocols.
    - Example: `curl www.google.com` retrieves the HTML content of the page.
    - You can save the output to a file using the `-o` option (e.g., `curl -o google.txt www.google.com`).
- **wget Command**:
    - Similar to curl, but more specialized for downloading files from URLs.
    - Can handle recursive downloads.
    - Example: Downloading a file with `wget` shows progress and status messages.
---
## File archiving and compression command
- **Archiving vs. Compression**:
    - **Archiving**: Storing information for future use, creating a single file from multiple files and directories (e.g., using the `tar` command).
    - **Compression**: Reducing file size by eliminating redundancy (e.g., using `gzip`).
- **Creating an Archive**:
    - Use the `tar` command to create an archive:
        ```bash
        tar -cf notes.tar notes
        ```
    - The `-c` option creates a new archive, and `-f` specifies the filename.
- **Compressing an Archive**:
    - To compress the archive, add the `-z` option:
        ```bash
        tar -czf notes.tar.gz notes
        ```
- **Listing Archive Contents**:
    - To view the contents of an archive:
        ```bash
        tar -tf notes.tar
        ```
- **Extracting Files**:
    - To extract files from an archive:
        ```bash
        tar -xf notes.tar
    ```
    - To extract files from an compression
		```bash
		tar -xzf notes.tar.gz notes
		```
- **Using Zip for Compression**:
    - The `zip` command can also be used to compress files:
        ```bash
        zip notes.zip notes
        ```
    - To extract files from a zip archive:
        ```bash
        unzip notes.zip
        ```