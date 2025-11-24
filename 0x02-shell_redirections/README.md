# 0x02. Shell, I/O Redirections and Filters

## Description
This project introduces learners to input and output redirections and essential text-processing commands in Linux. Through hands-on tasks, students will gain practical experience in redirecting command output, reading from files, and using common filters like `cat`, `head`, `tail`, `sort`, and `uniq`. By the end of this project, learners will be able to control where output goes, manage errors, and combine commands with pipes for efficient data processing.

## Learning Objectives
By the end of this project, you should be able to explain:

### Shell I/O Redirections
- What do the commands `head`, `tail`, `find`, `wc`, `sort`, `uniq`, `grep`, `tr` do
- How to redirect standard output to a file
- How to get standard input from a file instead of the keyboard
- How to send the output from one program to the input of another program
- How to combine commands and filters with redirections

### Special Characters
- What are special characters
- Understand what do the white spaces, single quotes, double quotes, backslash, comment, pipe, command separator, tilde and how and when to use them

### Other Man Pages
- How to display a line of text
- How to concatenate files and print on the standard output
- How to reverse a string
- How to remove sections from each line of files
- What is the `/etc/passwd` file and what is its format
- What is the `/etc/shadow` file and what is its format

## Project Information
- **Weight:** 1280
- **Project Duration:** Nov 17, 2025 1:00 AM - Dec 1, 2025 1:00 AM
- **Grade Contribution:** 12.5% of overall grade
- **Auto-checker:** Runs at the end of the submission deadline

## Requirements
- Allowed editors: `vi`, `vim`, `emacs`
- All scripts will be tested on Ubuntu 20.04 LTS
- All scripts should be exactly two lines long (`$ wc -l file` should print 2)
- All files should end with a new line
- The first line of all files should be exactly `#!/bin/bash`
- A README.md file at the root of the project folder is mandatory
- You are not allowed to use backticks, `&&`, `||` or `;`
- All files must be executable
- You are not allowed to use `sed` or `awk`

## Repository Structure
```
system_engineering-devops/
└── 0x02-shell_redirections/
    ├── README.md
    ├── 0-hello_world
    ├── 1-confused_smiley
    ├── 2-hellofile
    ├── 3-twofiles
    ├── 4-lastlines
    ├── 5-firstlines
    ├── 6-third_line
    ├── 7-file
    ├── 8-cwd_state
    ├── 9-duplicate_last_line
    └── 10-no_more_js
```

## Tasks

### 0. Hello World
**File:** `0-hello_world`  
Write a script that prints "Hello, World", followed by a new line to the standard output.

### 1. Confused Smiley
**File:** `1-confused_smiley`  
Write a script that displays a confused smiley `"(Ôo)'`.

### 2. Let's Display a File
**File:** `2-hellofile`  
Display the content of the `/etc/passwd` file.

### 3. What About 2?
**File:** `3-twofiles`  
Display the content of `/etc/passwd` and `/etc/hosts`.

### 4. Last Lines of a File
**File:** `4-lastlines`  
Display the last 10 lines of `/etc/passwd`.

### 5. I'd Prefer the First Ones, Actually
**File:** `5-firstlines`  
Display the first 10 lines of `/etc/passwd`.

### 6. Line #2
**File:** `6-third_line`  
Write a script that displays the third line of the file `iacta`.
- The file `iacta` will be in the working directory
- You're not allowed to use `sed`

### 7. It's a Good File That Cuts Iron Without Making a Noise
**File:** `7-file`  
Write a shell script that creates a file named exactly `\*\\'"Best School"\'\\*$\?\*\*\*\*\*:)` containing the text `Best School` ending by a new line.

### 8. Save Current State of Directory
**File:** `8-cwd_state`  
Write a script that writes into the file `ls_cwd_content` the result of the command `ls -la`. If the file `ls_cwd_content` already exists, it should be overwritten. If the file `ls_cwd_content` does not exist, create it.

### 9. Duplicate the Last Line
**File:** `9-duplicate_last_line`  
Write a script that duplicates the last line of the file `iacta`.
- The file `iacta` will be in the working directory

### 10. No More Javascript
**File:** `10-no_more_js`  
Write a script that deletes all the regular files (not the directories) with a `.js` extension that are present in the current directory and all its subfolders.

## Key Concepts

### I/O Redirection
Input/Output redirection allows you to control where command input comes from and where output goes.

**Standard Streams:**
- `stdin` (0) - Standard input (keyboard)
- `stdout` (1) - Standard output (screen)
- `stderr` (2) - Standard error (screen)

**Redirection Operators:**
| Operator | Description | Example |
|----------|-------------|---------|
| `>` | Redirect stdout to file (overwrite) | `echo "text" > file.txt` |
| `>>` | Redirect stdout to file (append) | `echo "text" >> file.txt` |
| `<` | Redirect stdin from file | `sort < file.txt` |
| `2>` | Redirect stderr to file | `command 2> error.log` |
| `&>` | Redirect both stdout and stderr | `command &> output.log` |
| `\|` | Pipe: stdout of cmd1 to stdin of cmd2 | `cat file \| grep pattern` |

### Filters
Filters are commands that process text from stdin and output to stdout.

**Common Filters:**
- `cat` - Concatenate and display files
- `head` - Display first lines of a file
- `tail` - Display last lines of a file
- `grep` - Search for patterns in text
- `sort` - Sort lines of text
- `uniq` - Remove duplicate consecutive lines
- `wc` - Count lines, words, and characters
- `tr` - Translate or delete characters

### Special Characters

| Character | Name | Purpose |
|-----------|------|---------|
| `\` | Backslash | Escape character |
| `'` | Single quote | Literal string (no expansion) |
| `"` | Double quote | String with variable expansion |
| `*` | Asterisk | Wildcard (any characters) |
| `?` | Question mark | Wildcard (single character) |
| `$` | Dollar | Variable prefix |
| `#` | Hash | Comment |
| `\|` | Pipe | Connect commands |
| `;` | Semicolon | Command separator |
| `~` | Tilde | Home directory |

## Important Files

### /etc/passwd
Contains user account information. Format:
```
username:password:UID:GID:comment:home_directory:shell
```

Example:
```
root:x:0:0:root:/root:/bin/bash
```

### /etc/hosts
Maps hostnames to IP addresses for local name resolution.

Example:
```
127.0.0.1   localhost
192.168.1.10   myserver
```

## Usage Examples

### Basic Output Redirection
```bash
# Save command output to file
echo "Hello" > output.txt

# Append to file
echo "World" >> output.txt

# Read from file
cat < input.txt
```

### Piping Commands
```bash
# Count lines in a file
cat file.txt | wc -l

# Search and sort
grep "pattern" file.txt | sort

# Get unique values
cat file.txt | sort | uniq
```

### Head and Tail
```bash
# First 10 lines
head file.txt

# Last 10 lines
tail file.txt

# Specific number of lines
head -n 5 file.txt
tail -n 3 file.txt

# Get specific line (line 3)
head -n 3 file.txt | tail -n 1
```

### Find Command
```bash
# Find all .txt files
find . -name "*.txt"

# Find and delete .js files
find . -type f -name "*.js" -delete

# Find directories only
find . -type d
```

## Common Commands Reference

| Command | Description | Example |
|---------|-------------|---------|
| `echo` | Print text to stdout | `echo "Hello"` |
| `cat` | Display file contents | `cat file.txt` |
| `head` | Show first lines | `head -n 10 file.txt` |
| `tail` | Show last lines | `tail -n 5 file.txt` |
| `find` | Search for files | `find . -name "*.txt"` |
| `grep` | Search text patterns | `grep "error" log.txt` |
| `sort` | Sort lines | `sort file.txt` |
| `uniq` | Remove duplicates | `uniq file.txt` |
| `wc` | Count lines/words | `wc -l file.txt` |
| `tr` | Translate characters | `tr 'a-z' 'A-Z'` |

## Tips for Success

1. **Test your scripts locally** if you have access to a Linux environment
2. **Read man pages** for detailed command information: `man command`
3. **Check script length**: `wc -l filename` should output 2
4. **Verify shebang**: First line must be `#!/bin/bash`
5. **Make executable**: `chmod +x filename`
6. **Test with different inputs** to ensure robustness
7. **Pay attention to special characters** and escape them properly
8. **Use pipes effectively** to combine simple commands

## Debugging Tips

```bash
# Check if file exists
ls -la filename

# Verify script permissions
ls -l filename

# Check script syntax (won't execute, just checks)
bash -n filename

# Run with verbose output
bash -x filename

# Check file line count
wc -l filename
```

## Resources

- [Shell I/O Redirection](https://www.gnu.org/software/bash/manual/html_node/Redirections.html)
- [Pipe, Grep and Sort Command](https://www.geeksforgeeks.org/piping-in-unix-or-linux/)
- [Special Characters in Bash](https://www.tldp.org/LDP/abs/html/special-chars.html)

## Author
Created as part of the System Engineering & DevOps curriculum.

## License
This project is part of an educational program and follows the institution's academic policies.
