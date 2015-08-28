# Install
- `cp bufferhint.vim ~/.vim/plugin/`
- pathogen: `mkdir -p ~/.vim/bundle/bufferhint/plugin/` throw bufferhint.vim in that directory.

Add following two lines in your "~/.vimrc":
    nnoremap - :call bufferhint#Popup()<CR>
    nnoremap \ :call bufferhint#LoadPrevious()<CR>

# Usage
Basic usage:
1. `vim foo.txt bar.txt doe.txt`
1. Type `-` to popup bufferhint window
1. Type `j/k/C-f/C-b/PGUP/PGDN` to navigate
1. Type `ENTER` to load the buffer under cursor

Load buffer by hint:
1. `vim foo.txt bar.txt doe.txt`
1. Type `-` to popup bufferhint window
1. Type `b` to load "bar.txt"
1. Type `\` to load the previous buffer namely "foo.txt"

Switch sort mode:
1. Type `-` to popup bufferhint window
1. Type `SPACE` to switch sort mode

Delete buffers:
1. `vim foo.txt bar.txt doe.txt`
1. Type `-` to popup bufferhint window
1. Type `dd` to delete the buffer under cursor
1. Type `db` to delete a buffer by hint

Notes:
- Yellow hints means the buffers are sorted by path, green hints means the buffers are sorted by LRU.
- You can also type `/` in bufferhint window and search what you want, then type `ENTER` to load it.
- Apparently `j/k/d/n/N` are excluded from the hint chars.

# Functions
- `bufferhint#Popup()`
Toggle bufferhint window.

- `bufferhint#LoadPrevious()`
Load the second item in LRU. It's very useful in the scene where you want to switch back and forth between two files.

- `bufferhint#Save()`
Save current session to an external session file which can be restored by `vim -S` command in the future. The name of the session file is "session.vim" by default, it can be specified by setting `g:bufferhint_SessionFile`.

# Preference
- `g:bufferhint_SortMode`
Default sort mode. 0: sort by path, 1: sort by LRU.

- `g:bufferhint_MaxWidth`
Maxmium window width.

- `g:bufferhint_PageStep`
Page step, for `PGUP/PGDN/C-f/C-b`.

- `g:bufferhint_SessionFile`
Session file name.
