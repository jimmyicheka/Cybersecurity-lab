 📂 Viewing and Filtering File Contents in Linux

In Linux, there are several essential commands for inspecting, analyzing, and filtering the contents of files. These tools are incredibly useful when working with configuration files, system logs, and outputs from various processes.

This section provides a hands-on guide with examples and output to help you understand how each command works and what the results mean.

---

## 📄 1. Viewing File Contents

### 🔹 `cat` – View entire file contents
```bash
cat /etc/passwd
Output:

ruby

root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
...
Shows the full contents of the file. Often used to quickly read small files.

🔹 more – View file one page at a time
bash
cat /etc/passwd | more
Output:

ruby

root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
--More--
Pauses after each page. Use Enter/Space to scroll and q to quit.

🔹 less – Scrollable file viewer
bash

less /etc/passwd
Interactive file viewer. Use ↑ ↓ or PgUp/PgDn to navigate, and press q to quit.

🔝🔚 2. Display Start or End of a File
🔹 head – Show beginning lines
bash
head /etc/passwd
Output:

ruby
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
...
Displays the first 10 lines by default. Use -n to set a custom number.

🔹 tail – Show end lines

tail /etc/passwd
Output:

ruby
systemd-resolve:x:102:103:systemd Resolver:/run/systemd/resolve:/usr/sbin/nologin
user:x:1000:1000:user:/home/user:/bin/bash
Useful for checking recent log entries or the last few users.

🔍 3. Filtering and Searching
🔹 grep – Search for matching lines

grep "/bin/bash" /etc/passwd
Output:

ruby

root:x:0:0:root:/root:/bin/bash
user:x:1000:1000:user:/home/user:/bin/bash
Finds lines that contain /bin/bash.

🔹 grep -v – Exclude matching lines

grep -v "nologin" /etc/passwd
Output:


root:x:0:0:root:/root:/bin/bash
user:x:1000:1000:user:/home/user:/bin/bash
Returns lines that do not contain nologin.

✂️ 4. Extracting Fields
🔹 cut – Extract specific fields

cut -d ":" -f1 /etc/passwd
Output:

python-repl
Copy
Edit
root
daemon
bin
sys
...
-d ":" tells it to use : as a delimiter, and -f1 selects the first field — the username.

🔁 5. Replace Characters
🔹 tr – Translate or delete characters

cat /etc/passwd | tr ":" " "
Output:


root x 0 0 root /root /bin/bash
daemon x 1 1 daemon /usr/sbin /usr/sbin/nologin
...
Replaces : with a space. Useful for formatting.

📊 6. Formatting Output
🔹 column – Align into neat columns

cat /etc/passwd | tr ":" " " | column -t
Output:


root    x  0  0  root    /root             /bin/bash
daemon  x  1  1  daemon  /usr/sbin         /usr/sbin/nologin
...
Helps improve readability of structured text.

🧠 7. Smart Field Extraction
🔹 awk – Scan and extract by pattern

cat /etc/passwd | awk -F ":" '{print $1, $7}'
Output:


root /bin/bash
daemon /usr/sbin/nologin
...
-F ":" sets the field delimiter.

$1 is the first field (username), $7 is the seventh (shell path).

🧪 8. Text Substitution
🔹 sed – Search and replace

cat /etc/passwd | sed 's/bash/HTBshell/g'
Output:


root:x:0:0:root:/root:/bin/HTBshell
...
Replaces bash with HTBshell globally in each line.

🔢 9. Counting Results
🔹 wc – Word, line, character count

grep "/bin/bash" /etc/passwd | wc -l
Output:


2
Tells you how many lines (users) match /bin/bash.

📋 Summary Table
Command	Purpose	Example
cat	View full file	cat /etc/passwd
more	Paginate output	`cat file
less	Scroll file interactively	less file
head	View top lines	head -n 10 file
tail	View last lines	tail -n 10 file
grep	Search for patterns	grep 'bash' /etc/passwd
cut	Extract columns by delimiter	cut -d ':' -f1 file
tr	Replace characters	tr ':' ' ' file
column	Align fields into columns	`...
awk	Extract & format fields	awk -F ':' '{print $1, $7}' file
sed	Replace content on the fly	sed 's/bash/zsh/g' file
wc	Count lines, words, chars	wc -l file



