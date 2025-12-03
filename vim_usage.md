# Vi/Vim Usage

Nomenclatural note: **Vi** is often the same as Vim. Vi is a text editor found on almost every linux system. **Vim** is the newest iteration of Vi. On most modern linux distros you can use the names interchangably.

## Why Learn this?

Vi/Vim is a powerful text editor that is widely used for programming and general text editing. Below are some basic commands and tips to help you get started with Vim. 

It is **important** to learn  because `vi` is sometimes the **only file editor** available by default on some Linux systems. 

## Before we start

Remember the most important key in vim is the **ESC** or escape key. Use it to exit from any other mode into normal mode, this will become more clear soon. You may have never used this key before and wondered what it is for :). Now you know.

## Starting Vim/Vi

- `vi [file]` or `vim [file]`: Opens the specified file in Vi/Vim. If the file does not exist, it will create a new file.
- The `vim` or `vi` command alone opens Vi/Vim without any file. Instead it will show your the current directory where you can use the up and down keys to select a file to edit, or even navigate deeper into the directory structure.

## The Arrow Keys

On some early computer systems keyboards did not have arrow keys! On these keyboards you use the `h`, `j`, `k`, and `l` keys for moving the cursor around the screen. Modern keyboards almost always have arrow keys but you can still use the `hjkl` keys to move the cursor without moving your fingers off the home keys. Once you learn to open files you can try out these keys for yourself, it can be very nice not to move your hands off the home keys, once you get used to it.

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

This is discussed now since it the most important thing you need to do. How to I save and finish?! People are often stuck here unable to save their work.

To exit Vim, you can use one of the following commands in Command-Line mode:

1. Hit the escape key a few times like a hacker.
2. Enter the command mode with the `:` key.
3. Then hit `x` to save and quit.

Here are some examples:

- `:wq`: Save changes and quit.
- `:q!`: Quit without saving changes.
- `:x`: Save changes and quit (same as `:wq`).

## Saving your Work Regulary

To save in Vim, use the `w` command in **command** mode. The sequence is `ESC`, `:` , `w`, enter.  

### A full exmaple of editing a file.

Here we will open a file with vim, enter **insert** mode, then save the file. 

For Example:

Open the file in vim.
```bash
$ vim file.txt
```

The regular terminal will disapear and be replaced with the following:

```bash
~                                                                      
~                                                                      
~                                                                      
~                                                                      
~                                                                                
~                                                                      
~                                                                      
~                                                                      
                                                     0,0-1         All
```
This is a blank file in normal mode. Those numbers are the Line and Character numbers your cursor is at.

If `file.txt` is empty your screen will be empty. If not you will see the files contents. 

1. Enter **insert** mode by hitting hitting the `i` key. Notice the `-- INSERT --` mode indication in the bottom of the terminal.
2. Now you can enter some text. Use the to move your cursor around if necessary. Delete and Backspace function as you would expect.

```bash
This is some
text in the
test file.

~                                                                                
~                                                                        
~                                                                        
~                                                                        
-- INSERT --                                           4,1           All
```

3. Exit insert mode to **normal** mode by hitting the escape key.
4. Enter command mode by hitting the `:` key. You will see the colon character at the bottom of the screen.
5. Enter `w` and hit enter. You have "written" the file to disk.

```bash
This is some
text in the
test file.

~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
"test_file.txt" 4L, 38B written                        4,0-1         All
```

6. Now hit the escape key a and enter **normal** mode again.
7. Now exit the editor by entering the command mode and quiting all in one go. Type `:q` and then hit enter.   

```bash
This is some
text in the
test file.

~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
~                                                                        
:q
```

You should be back at the command line of the terminal again where you started. You are done! You edited and inserted into a file in vim! Well Done.

## Just a scratch on the surface

This is the most basic of vi/vim's capabilities.

For example, with Vi/Vim:
* You can search for text in files using strings or [regular expressions](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_04_01.html).
* You can Search and Replace all of the matching strings or expressions.
* You can record custom macros.
* You can re-run the previous command by using the `.` command in the **normal** mode.

Vi/Vim is as powerfull as just about any text editor available and it runs in any linux terminal.

