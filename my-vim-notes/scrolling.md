SCROLLING : 

How to scroll up and down through a page gracefully?

M/H/L : Move cursor to middle/top/bottom of screen

:N : Go to line N
N% : Go to the line N percent through the file
N| : Go to column N

The main scrolling commands in Vim are:
    Ctrl-B and Ctrl-F, as well as PageUp and PageDown scroll by full page
    Ctrl-U and Ctrl-D scroll half a page by default
    Ctrl-Y and Ctrl-E scroll one line
I lose visual context every time for the former two, so I have developed the bad habit of hitting the latter (Ctrl-Y and Ctrl-E) repetitively. 

Vim page up and page down keystrokes:
The Vim page up keystroke is [Control][b]. You can remember the 'b' by thinking "back".
The Vim page down keystroke is [Control][f]. You can remember the 'f' by thinking "forward".

You can use other keystrokes in Vim to move up and down, as shown here:
[Control][b] - Move back one full screen
[Control][f] - Move forward one full screen
[Control][d] - Move forward 1/2 screen
[Control][u] - Move back (up) 1/2 screen

    zt - move current line to the top of the screen
    zz - move current line to the middle of the screen (Careful with zz, if you happen to have Caps Lock on accidentally, you will save and exit vim!)
    zb - move current line to the bottom of the screen

Additionally:

    Ctrl-y Moves screen up one line
    Ctrl-e Moves screen down one line
    Ctrl-u Moves cursor & screen up ½ page
    Ctrl-d Moves cursor & screen down ½ page
    Ctrl-b Moves screen up one page, cursor to last line
    Ctrl-f Moves screen down one page, cursor to first line

Ctrl-y and Ctrl-e only change the cursor position if it would be moved off screen.

To leave the cursor in the same column when you use Ctrl+D, Ctrl+F, Ctrl+B, Ctrl+U, G, H, M, L, gg

you should define the following option:

:set nostartofline

-----------------------------------------------------------
