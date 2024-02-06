# Vim

## Why
1. Fast and useful command line editor. 
2. Lightweight compared to VSCode. 
3. Everything is on keyboard. No need for a mouse.
4. So you can stop using `Nano` and trap your friends in Vim :)

## Installation

`sudo apt install vim`

## Basic Usage

`vim <file-name>` in a terminal

Main editing modes:
1. Normal mode  
2. Insert mode  
3. Visual mode  
4. Visual line mode  
5. Visual block  

### Normal Mode

Where you can move around, navigate, and quickly edit things. You will be in this mode mostly.  

### Insert Mode

When you need to type.

### Visual mode

When you need to select a part of a line.

### Visual line mode

When you need to select multiple lines

### Visual block mode

When you need to select things as a block

## Moving between modes

`ESC` to go back to normal mode from the different modes.  
`i` from normal to insert mode.  
`v` from normal to visual mode.  
`shift+v` from normal to visual line mode.  
`crtl+v` from normal to visual block mode.   


# Normal Mode

## File Navigation

`h`: move cursor left  
`j`: move cursor down  
`k`: move cursor up  
`l`: move cursor right  
`b`: move the cursor back a word  
`w`: move cursor to next word  
`e`: move the cursor to the end of the word  

### More advanced navigation

`0`: move to beginning of line  
`^`: move to the first non-whitespace character of a line  
`$`: move to last character in line  
`gg`: move to beginning of file  
`G`: move to end of file  
`f<char>`: move cursor to next occurrence of <char> (Remember f is find <char>)  
`t<char>`: move cursor to before next occurrence of <char> (Remember t is goto <char>)  
`F<char>`: move cursor to previous occurrence of <char>  
`T<char>`: move cursor to after previous occurrence of <char>  

Can be used with numbers before to repeat that navigation, e.g., `4j` moves down 4 lines.  

## Action Keys

Action keys are normally mixed with Navigation keys to specify where to apply the action.  
Numbers can be used here as well.  
Ex. `d4w` will delete the next 4 words 

`d`: delete  
`c`: change (delete + insert mode)  
`y`: copy (yank)  
`p`: paste the last thing copied or deleted with `d`, `c`, or `x` and more.  
`x`: delete current character   
`r`: replace current character with the next character input. Doesn't go to insert mode.  

### Useful Shortcuts  

`dd`: delete entire line  
`cc`: same as `dd` but put into insert mode after  
`yy`: copy entire line (yank)  
`u`: Undo  
`Crtl+r`: Redo  

## Insert Mode

`i`: insert before cursor  
`I`: insert at the beginning of line  
`a`: insert after cursor (Remember with append)  
`A`: insert at end of line  

## Searching

`/<characters-to-search>`: Hit enter to perform search. `n` to find next occurrence, `N` to find previous occurrence.  
`:s/<characters-to-find-and-replace>/<characters-that-will-replace>`: will only do it once for current line.   
Use `:s/.../.../g` to replace all occurrences in a line.   
Use `:%s/.../...` to replace first occurrence in each line of file.   
Use `:%s/.../.../g` to replace all occurrences.  

## Save and Quit (HELP HOW DO I GET OUT OF VIM)

More traditionally you will do the following:  
`:w`: will write and save the file   
`:q`: will quit the file  
`:wq`: will write and quit  
Less traditionally:  
`ZZ`: will write and quit  

### Additional Notes

Additionally, practice installing the Vim extension in VSCode.  
Vim is much more powerful than just a basic text editor. There are other commands in Neovim.   
You can make macros and other commands to make your workflow faster.  

## Links and Resources

A non-exhaustive list of Vim learning resources:

- [Vim practice](https://www.openvim.com/)  
- [Vim game](https://vim-adventures.com/)  
- [Vim cheatsheet](https://vimsheet.com/)  
- [Missing Semester Vim](https://missing.csail.mit.edu/2020/editors/)  
- `vimtutor` in terminal has tutorial   
