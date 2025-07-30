📂  Viewing & Filtering File Contents
Linux offers several command-line tools that help you inspect files, extract useful data, and transform the output for better understanding. These tools are especially useful for sysadmins, developers, and hackers.

📄 1. Viewing File Contents
🔹 more
What it does: Displays file content one page at a time (when file is long).

bash
Copy
Edit
cat /etc/passwd | more
cat: Outputs the entire file.

| more: Pauses every screenful so you can read line-by-line.

Example Output:

ruby
Copy
Edit
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
--More--
🔹 less
What it does: Similar to more, but more powerful. Lets you scroll up/down freely.

bash
Copy
Edit
less /etc/passwd
Opens file in a scrollable view.

Press q to quit.

Example Output: Same as more, but scrollable interactively.

🔝🔚 2. Show Start or End of a File
🔹 head
What it does: Shows the first 10 lines of a file.

bash
Copy
Edit
head /etc/passwd
Output:

ruby
Copy
Edit
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
...
🔹 tail
What it does: Shows the last 10 lines of a file.

bash
Copy
Edit
tail /etc/passwd
Output:

ruby
Copy
Edit
systemd-resolve:x:102:103:systemd Resolver:/run/systemd/resolve:/usr/sbin/nologin
user:x:1000:1000:user:/home/user:/bin/bash
🔍 3. Filtering & Searching Content
🔹 grep
What it does: Searches for lines that match a pattern.

bash
Copy
Edit
cat /etc/passwd | grep "/bin/bash"
Finds users whose login shell is /bin/bash.

Output:

ruby
Copy
Edit
root:x:0:0:root:/root:/bin/bash
user:x:1000:1000:user:/home/user:/bin/bash
🔹 grep -v
What it does: Shows lines that do NOT match the pattern.

bash
Copy
Edit
cat /etc/passwd | grep -v "nologin"
Excludes system accounts without real login access.

Output:

ruby
Copy
Edit
root:x:0:0:root:/root:/bin/bash
user:x:1000:1000:user:/home/user:/bin/bash
✂️ 4. Extracting Specific Fields
🔹 cut
What it does: Splits each line and shows specific fields.

bash
Copy
Edit
cat /etc/passwd | cut -d ":" -f1
-d ":": Use : as a separator.

-f1: Show first field (username).

Output:

python
Copy
Edit
root
daemon
bin
🔁 5. Replacing Characters
🔹 tr
What it does: Translates or replaces characters.

bash
Copy
Edit
cat /etc/passwd | tr ":" " "
Replaces colons (:) with spaces.

Output:

bash
Copy
Edit
root x 0 0 root /root /bin/bash
📊 6. Formatting as a Table
🔹 column
What it does: Aligns text into neat columns.

bash
Copy
Edit
cat /etc/passwd | tr ":" " " | column -t
Output:

bash
Copy
Edit
root   x  0    0    root   /root           /bin/bash
daemon x  1    1    daemon /usr/sbin       /usr/sbin/nologin
🧠 7. Smart Field Extraction
🔹 awk
What it does: Prints selected columns from input.

bash
Copy
Edit
cat /etc/passwd | tr ":" " " | awk '{print $1, $NF}'
$1: First field (username)

$NF: Last field (login shell)

Output:

bash
Copy
Edit
root /bin/bash
daemon /usr/sbin/nologin
🧪 8. Search and Replace Text
🔹 sed
What it does: Finds and replaces text in each line.

bash
Copy
Edit
cat /etc/passwd | tr ":" " " | sed 's/bash/HTBshell/g'
Replaces bash with HTBshell.

Output:

bash
Copy
Edit
root x 0 0 root /root /bin/HTBshell
🔢 9. Counting Output
🔹 wc
What it does: Counts lines, words, or characters.

bash
Copy
Edit
cat /etc/passwd | grep "/bin/bash" | wc -l
wc -l: Counts the number of lines.

Useful for counting users with /bin/bash login shell.

Output:

Copy
Edit
2
✅ Summary Table
Tool	Use Case	Example Use
cat	Show full file	cat /etc/passwd
more	Paginate long files	`cat file.txt
less	Advanced paging	less file.txt
head	Show first N lines	head /var/log/syslog
tail	Show last N lines	tail -n 20 /var/log/syslog
grep	Find matching lines	grep 'error' file.txt
cut	Extract columns	cut -d ":" -f1 file.txt
tr	Replace characters	tr ':' ' '
column	Format output into table	`...
awk	Print specific fields	awk '{print $1, $NF}'
sed	Search and replace	sed 's/old/new/g'
wc	Count lines, words, characters	wc -l

