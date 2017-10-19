# [Vim Cheat Sheet](https://jyee117.github.io/vimcheatsheet)
#### A quick reference for how to do useful things in Vim.

| **[Vim Core](#vim-core)** | **[Vim Plugins](#vim-plugins)** |
|---------------------------|---------------------------------|
| [Files](#files) | [Foo](#foo) |
| [Windows](#windows) | |
| [Tabs](#tabs) | |

# Vim Core
### Files

| **Command or Key** | **Description** |
|:-------------------|:----------------|
| :e | Edit a file. |
| :e $MYVIMRC | Edit your vimrc file. |
| :e .\dir | Open directory with netrw. |
| :hid e | Edit a different file while retaining changes in current file. |
| :sav filename.c | Save current buffer as filename.c. |
| :f filename.c | Change filename of buffer without saving the file. |

### Windows

| **Command or Key** | **Description** |
|:-------------------|:----------------|
| CTRL-W s | Split window horizontally. |
| CTRL-W v | Split window vertically. |
| CTRL-W c | Close window. |
| CTRL-W h/j/k/l/t/b | Move between windows. |
| CTRL-W H/J/K/L | Move window to edge. |
| CTRL-W _ | Maximize window height. |
| CTRL-W | | Maximize window width. |
| CTRL-W = | Equalize window sizes. |
| CTRL-W o | Close all but current window. |
| CTRL-W\_CTRL-N | Open a new empty file in a split |
| :sp/:vsp file.c | Open a file in a split. |

### Tabs

| **Command or Key** | **Description** |
|:-------------------|:----------------|
| :tabe file.c | Open a new tab. |
| :tab sp | Open the current buffer in a new tab. |
| :tabc | Close the current tab page. |
| :tabo | Close all but the current tab page. |
| CTRL-PageUp/Down or :gt/T | Switch between tab pages. |
| :(+/-[N])tabm | Move tab. |

# Vim Plugins
### [Foo](https://github.com/jyee117/vimcheatsheet)

