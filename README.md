# tmux cheatsheet
Based on [tmux: Productive Mouse-Free Development](http://pragprog.com/book/bhtmux/tmux)
(The Pragmatic Progammers - Brian P. Hogan).

| Shell command | Description |
| --- | ---- |
| `tmux new-session -s sessionname`<br>`tmux new -s sessionname` | Create a named session called *sessionname* |
| `tmux new -s sessionname -d` | Create detached session |
| `tmux new -s sessionname -n win` | Create session *sessionname* with window *win* |
| `tmux list-sessions` <br> `tmux ls` | |
| `tmux attach` | |
| `tmux attach -t sessionname` | Attach to session with name *sessionname* |
| `tmux kill-session -t sessionname` | |

| PREFIX (`CTRL-b`) + … | Description | Custom mapping |
| --------------------- | ----------- | -------------- |
| `d`|Detach ||
| `c`| Create window ||
| `,`| Rename window ||
| `n`|Go to next window ||
| `p`|Go to previous window ||
| `0`|Go to window no `0` ||
| `1`|Go to window no `1` ||
| `f`|Find window by name ||
| `w`|Select window by menu ||
| `&`|Kill window (after confirmation) ||
| `%`|Split horizontally ||
| `PIPE`|Split horizontally | yes|
| `"`|Split vertically ||
| `-` | Split vertically|yes |
| `o`|Cycle through panes ||
| `UP`, `DOWN`, `LEFT`, `RIGHT`|Move to next pane in direction ||
|`h`, `j`, `k`, `l`|Select next pane in vim-direction|yes|
| `SPACE`|Cycle pane layout (`even-horizontal`, `even-vertical`, `main-horizontal`, `main-vertical`, `tiled`) ||
|`CTRL-h`, `CTRL-l`|Select next/previous window|yes|
|`H`, `J`, `K`, `L`|Resize pane in vim-direction (5 column-wise)|yes|
| `x`|Kill pane (after confirmation) ||
| `:`|Enter command mode ||
| `?`|See all keybindings ||
| `ESCAPE`|Enter copy mode ||
| `p`|Paste from buffer||
| `r`| Reload config file (`.tmux.conf`)| yes |
| `CTRL-c`|Copy buffer to MAC clipboard |

## Command mode

Command|Description
-------|-----------
`new-window -n redis "redis-server"`|Open new window, name it *windowname* and run *redis-server* in it.
`capture-pane`|Copy entire visible contents of pane into the paste buffer
`show-buffer`|Show contents of actual buffer
`save-buffer file.txt`|Save buffer to `file.txt`
`list-buffers`|Show all buffers
`choose-buffer`|Chosse a buffer and paste

## Copy mode
Key|Description
---|-----------
`h`, `j`, `k`, `l`|Move around
`ENTER`|Leave copy mode
`w`|Jump to next word
`b`|Jump to previous word
`fA`|Jump to next `A` in the actual line
`FA`|Jump to previous `A` in the actual line
`CTRL-b`|Down one page
`CTRL-f`|Up one page
`g`|Jump to top of buffer
`G`|Jump to bottom of buffer
`?`|Backward search
`/`|Foreward search
`n`|Go to next occurence
`N`|Go to previous occurence
`SPACE`|Begin selecting text
`v`|Begin selecting text
`y`|Copy selection to buffer

## More
* [`~/.tmux.conf`](https://github.com/der-flo/dotfiles/blob/master/tmux.conf)
* [tmux: Productive Mouse-Free Development](http://pragprog.com/book/bhtmux/tmux).
* [Man page](http://www.openbsd.org/cgi-bin/man.cgi?query=tmux)
