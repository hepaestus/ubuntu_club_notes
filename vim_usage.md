# Vim Usage

Vi/Vim is a powerful text editor that is widely used for programming and general text editing. Below are some basic commands and tips to help you get started with Vim. It is important since it is sometimes the only editor available on remote Linux systems.

Remember the most important key in vim is **ESC** key to exit from any mode to normal mode.

## Starting Vim

- `vim [file]`: Opens the specified file in Vim. If the file does not exist, it will create a new file.
- `vim`: Opens Vim without any file. It will show your the current directory where you can use the up and down keys to select a file to edit, or even navigate deeper into the directory structure.

## Basic Modes

- **Normal Mode**: The default mode for navigation and command execution. Press `Esc` to enter Normal mode.
- **Insert Mode**: Used for inserting text. Press `i` to enter Insert mode from Normal mode.
- **Visual Mode**: Used for selecting text. Press `v` to enter Visual mode from Normal mode.
- **Command-Line Mode**: Used for executing commands. Press `:` to enter Command-Line mode from Normal mode.

## Basic Command-Line Mode Commands

- `i`: Enter Insert mode before the cursor.
- `a`: Enter Insert mode after the cursor.
- `o`: Open a new line below the current line and enter Insert mode.
- `Esc`: Return to Normal mode from Insert or Visual mode.
- `:w`: Save the current file.
- `:q`: Quit Vim.
- `:wq` or `:x`: Save and quit Vim.
- `:q!`: Quit without saving changes.
- `dd`: Delete the current line.
- `yy`: Yank (copy) the current line.
- `p`: Paste the yanked or deleted text after the cursor.
- `u`: Undo the last action.
- `Ctrl + r`: Redo the last undone action.
- `/[pattern]`: Search for a pattern in the file.
- `n`: Repeat the last search in the same direction.
- `N`: Repeat the last search in the opposite direction.
- `gg`: Go to the beginning of the file.
- `G`: Go to the end of the file.
- `:set number`: Show line numbers.
- `:set nonumber`: Hide line numbers.
- `:help [command]`: Display help for a specific command.

## Exiting Vim

This is discussed first since it the most important thing you need to do. How to I save and finish?!

To exit Vim, you can use one of the following commands in Command-Line mode:
- `:wq`: Save changes and quit.
- `:q!`: Quit without saving changes.
- `:x`: Save changes and quit (same as `:wq`).

## Saving your Work

To save in Vim, use the `w` command in **normal** mode.

Here we will open a file with vim, enter **insert** mode, then save the file. 

For Example:

Open the file in vim.
```bash
$ vim file.txt
```

If `file.txt` is empty your screen will be empty. If not you will see the files contents. 
1. Enter **insert** mode by hitting hitting the `i` key.
2. Now you can enter some text. Use the arrow keys to move your cursor around if necessary.
3. Exit insert mode to **normal** mode by hitting the escape key.
4. Enter command mode by hitting the `:` key. You will see the colon character at the bottom of the screen.
5. Enter `w` and hit enter. You have "written" the file to disk.
6. Now hit the escape key and enter **normal** mode again.
7. Now exit by entering the command mode and quiting all in one go. Type `:q`.   

You are done! 

## Just a scratch on the surface

This is the most basic of vi/vim's capabilities.

For eample,with Vi/Vim:
* You can search for text in files using strings or [regular expressions](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_04_01.html).
* You can Search and Replace all of the matching strings or expressions.
* You can record custom macros.
* You can re-run the previous command by using the `.` command in the **normal** mode.

Vi/Vim is as powerfull as just about any text editor available and it runs in any linux terminal.







