# Bash Basics

An introduction to Bash scripting and command line usage.

## Topics Covered

- The Pipe `|` Operator
- The `grep` Command

### Coming Soon

- Input and Output Redirection (`>`, `>>`, `<`)
- Variables and Environment Variables
- Conditional Statements (`if`, `then`, `else`, `elif`)
- Loops (`for`, `while`, `until`)

## Pipe Operator

Example: Maybe you have large number of files in a directory and you want to see only the last few files based on modification time. You can use the `ls` command with the `-altr` options combined with `tail` using a pipe. The `-altr` options for `ls` list all files (`a`), in long format (`l`), sorted by modification time (`t`), in reverse order (`r`).

the tail command by default shows the last 10 lines of its input, but you can specify a different number of lines to display by providing a numeric argument. For example, `tail -n 5` will show the last 5 lines.

The pipe operator `|` is used to pass the output of one command as input to another command. For example:

```bash
ls -altr | tail -n 5
```
This command lists all files in long format, sorted by modification time, and then pipes the output to `tail`, which displays the last few lines only.

The output will look something like this:

```bash
$ ls -altr | tail -5
-rwxrwxrwx 1 pete pete    0 Nov 19 16:22 foo.txt
-rwxrwxrwx 1 pete pete    0 Nov 19 16:22 bar.txt
-rwxrwxrwx 1 pete pete    0 Nov 19 16:22 flim.txt
-rwxrwxrwx 1 pete pete    0 Nov 19 16:22 flam.txt
drwxrwxrwx 1 pete pete 4096 Nov 19 16:22 .
```

## Grep Command

The `grep` command is used to search for specific patterns within files or input streams. It stands for "global regular expression print." You can use `grep` to filter output based on matching text.

Example: To search for the word "error" in a log file, you can use the following command:

```bash
grep "error" /var/log/syslog
```

This command will display all lines in the `/var/log/syslog` file that contain the word "error".



### More to come soon

