# Vim Usage

Vi/Vim is a powerful text editor that is widely used for programming and general text editing. Below are some basic commands and tips to help you get started with Vim. It is important since it sometimes the only editor available on remote Linux systems.

Remember the most important key in vim is **ESC** key to exit from any mode to normal mode.

## Starting Vim

- `vim [file]`: Opens the specified file in Vim. If the file does not exist, it will create a new file.
- `vim`: Opens Vim without any file.

## Basic Modes

- **Normal Mode**: The default mode for navigation and command execution. Press `Esc` to enter Normal mode.
- **Insert Mode**: Used for inserting text. Press `i` to enter Insert mode from Normal mode.
- **Visual Mode**: Used for selecting text. Press `v` to enter Visual mode from Normal mode.
- **Command-Line Mode**: Used for executing commands. Press `:` to enter Command-Line mode from Normal mode.

## Basic Commands

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

To exit Vim, you can use one of the following commands in Command-Line mode:
- `:wq`: Save changes and quit.
- `:q!`: Quit without saving changes.
- `:x`: Save changes and quit (same as `:wq`).