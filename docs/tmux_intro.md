# Tmux

## Why
1. Ability to open multiple terminals in a single window without having to `ssh` multiple times.  
2. Ability to detach without stopping a running process.  

## Installation

`sudo apt install tmux`

## Basic Usage

`tmux` in a terminal  

At the bottom, you can see your session name (e.g., `[0]`), and your window name  (e.g., `3: bash`).  

There are sessions, windows, and panes.  

1. Sessions are browser windows 
2. Windows are like browser tabs
3. Panes split windows

## Useful Commands 

All commands will be `Ctrl+B` and another key.  

You can tell what pane you are in by the borders being not white.  


### Pane commands 

`Ctrl+b %`: Split window horizontally   
`Ctrl+b "`: Split window vertically  
`Ctrl+b <direction>`: Move between panes in the specific direction using arrow keys  
`Ctrl+b z`: Zoom in/out of a pane  
`Ctrl+b [`: Start scrollback in pane  
`Ctrl+b x`: Remove current pane, will ask for Y/N in the bottom status bar  

### Window commands  

`Ctrl+b c`: Create a new window  
`Ctrl+b p`: Go to the previous window  
`Ctrl+b n`: Go to the next window  
`Ctrl+b N`: Go to the `N`th window  

### Session commands  

#### In Tmux  

`Ctrl+b d`: Detach from current session  

#### Outside Tmux  

`tmux ls`: List sessions with session names  
`tmux a -t <session-name>`: Attach to session with session-name  

## Links and Resources

- [Quick Guide by Ham Vocke](https://hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)  
- [Missing Semester Tmux](https://youtu.be/e8BO_dYxk5c?si=acg68b5aL4hfT78k&t=846)  
