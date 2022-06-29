# 0x02. Shell, I/O Redirections and filters Week 3 at ALX School 
## Tasks
| Task Name | Description | Script |
| --------- | ----------- | ------ |
| 0. Hello World | Write a script that prints “Hello, World”, followed by a new line to the standard output. | `echo "Hello, World"` |
| 1. Confused smiley | Write a script that displays a confused smiley `"(Ôo)'`. | `echo "\"(Ôo)'"` 
| 2. Let's display a file | Display the content of the `/etc/passwd` file. | `cat /etc/passwd`
| 3. What about 2? | Display the content of `/etc/passwd` and `/etc/hosts` file. | `cat /etc/passwd /etc/hosts`
| 4. Last lines of a file | Display the last 10 lines of `/etc/passwd` | `tail -n 10 /etc/passwd`
| 5. I'd prefer the first ones actually | Display the last 10 lines of `/etc/passwd` | `head -n 10 /etc/passwd`
| 6. Line #2 | Write a script that displays the third line of the file `iacta`. | `head -3 iacta | tail -1`
| 7. It is a good file that cuts iron without making a noise | Write a shell script that creates a file named exactly `\*\'Best School\'\*$\?\*\*\*\*\*:)` containing the text `Best School` ending by a new line. | `echo 'Best School' > \\\*\\\\"'\"Best School\"\\'"\\\\\*\$\\\?\\\*\\\*\\\*\\\*\\\*\:\)`
| 8. Save current state of directory | Write a script that writes into the file `ls_cwd_content` the result of the command `ls -la`. If the file `ls_cwd_content` already exists, it should be overwritten. If the file `ls_cwd_content` does not exist, create it. | `ls -la > ls_cwd_content`
| 9. Duplicate last line | Write a script that duplicates the last line of the file `iacta` | `tail -n 1 iacta >> iacta`
| 10. No more javascript | Write a script that deletes all the regular files (not the directories) with a `.js` extension that are present in the current directory and all its subfolders. | `find . -type f -name "*.js" -delete`
| 11. Don't just count your directories, make your directories count | Write a script that counts the number of directories and sub-directories in the current directory. | `find . -type d -not -name '.' | wc -l`
| 12. What’s new | Create a script that displays the 10 newest files in the current directory. | `ls -1t | head -n 10`
| 13. Being unique is better than being perfect | Create a script that takes a list of words as input and prints only words that appear exactly once. | `sort | uniq -u`
| 14. It must be in that file | Display lines containing the pattern “root” from the file `/etc/passwd` | `grep -i root /etc/passwd`
| 15. Count that word | Display the number of lines that contain the pattern “bin” in the file  `/etc/passwd` | `grep -c bin /etc/passwd`
| 16. What's next? | Display lines containing the pattern “root” and 3 lines after them in the file `/etc/passwd` | `grep -A 3 -i root /etc/passwd`
| 17. I hate bins | Display all the lines in the file `/etc/passwd` that do not contain the pattern “bin”. | `grep -v -i bin /etc/passwd`
| 18. Letters only please | Display all lines of the file `/etc/ssh/sshd_config` starting with a letter. | `grep -i '^[[:alpha:]]' /etc/ssh/sshd_config`
| 19. A to Z | Replace all characters `A` and `c` from input to `Z` and `e` respectively. | `tr "A" "Z" | tr "c" "e"`
| 20. Without C, you would live in hiago | Create a script that removes all letters `c` and `C` from input. | `tr -d "cC"`
| 21. esreveR | Write a script that reverse its input. | `rev`
| 22. DJ Cut Killer | Write a script that displays all users and their home directories, sorted by users. | `cut -d : -f 1,6 /etc/passwd | sort`
| 23. Empty casks make the most noise | Write a command that finds all empty files and directories in the current directory and all sub-directories. | `find . -empty | rev | cut -d '/' -f 1 | rev`
| 24. A gif is worth ten thousand words | Write a script that lists all the files with a `.gif` extension in the current directory and all its sub-directories. | `find -type f -name "*.gif" | rev | cut -d "/" -f 1 | cut -d '.' -f 2- | rev | LC_ALL=C sort -f`
| 25. Acrostic | Create a script that decodes acrostics that use the first letter of each line. | `cut -c1 | paste -s | tr -d "[:blank:]" `
| 26. The biggest fan | Write a script that parses web servers logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests. | `tail -n +2 | cut -f1 | sort | uniq -c | sort -nr | head -11 | tr -s ' ' | cut -d' ' -f3`
