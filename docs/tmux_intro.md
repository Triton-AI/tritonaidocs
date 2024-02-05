# Tmux

## Why
1. Ability to open multiple terminals in a single window without having to ssh multiple times.  
2. Ability to deattach without stopping a running process.  

## Instalation

`sudo apt install tmux`

## Basic Usage

`tmux` in a terminal  

In the bottom, you can see your session name ex. `[0]`, your window name ex.`3: bash`.  

There are sessions, windows, and panes.  

1. Sessions are browser windows 
2. Windows are like browser tabs
3. Panes split windows

## Useful Commands 

All commands will be `Crtl+B` and another key.  

You can tell what pane you are in by the boarders being not white.  

Pane commands  
`Crtl+b %`: Split window horizontally   
`Crtl+b "`: Split window vertically  
`Crtl+b <direction>`: Move between panes in the specific direction using arrow keys  
`Crtl+b z`: Zoom in/out of a pane  
`Crtl+b [`: Start scrollback in pane  
`Crtl+b x`: Remove current pane, will ask for Y/N in bottom status bar  

Window commands  
`Crtl+b c`: Create new window  
`Crtl+b p`: Go to previous window  
`Crtl+b n`: Go to next window  
`Crtl+b N`: Go to the `N`th window  

Session commands  
In Tmux  
`Crtl+b d`: Detach from current session  
Outside Tmux  
`tmux ls`: List sessions with session names  
`tmux a -t <session-name>`: Attach to session with session-name  

## Links and Resources

[Quick Guide by Ham Vocke](https://hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)  
[Missing Semester Tmux](https://youtu.be/e8BO_dYxk5c?si=acg68b5aL4hfT78k&t=846)  
