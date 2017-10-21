# Vim Cheat Sheet
#### A quick reference for how to do useful things in Vim.

| **[Vim Core](#vim-core)** | **[General Plugins](#vim-plugins)** | **[Clojure Plugins](#vim-plugins)** |
|---------------------------|-------------------------------------|-------------------------------------|
| [Files](#files)           | [vim-table-mode](#vim-table-mode)   | [vim-fireplace](#vim-fireplace)     |
| [Windows](#windows)       | [ctrlp](#ctrlp)                     | [vim-sexp](#vim-sexp)               |
| [Tabs](#tabs)             | [fugitive](#fugitive)               |                                     |

# Vim Core
### Files

| **Command or Key** | **Description**                                                |
|:-------------------|:---------------------------------------------------------------|
| :e                 | Edit a file.                                                   |
| :e $MYVIMRC        | Edit your vimrc file.                                          |
| :e .\dir           | Open directory with netrw.                                     |
| :hid e             | Edit a different file while retaining changes in current file. |
| :sav filename.c    | Save current buffer as filename.c.                             |
| :f filename.c      | Change filename of buffer without saving the file.             |

### Windows

| **Command or Key** | **Description**                  |
|:-------------------|:---------------------------------|
| CTRL-W s           | Split window horizontally.       |
| CTRL-W v           | Split window vertically.         |
| CTRL-W c           | Close window.                    |
| CTRL-W h/j/k/l/t/b | Move between windows.            |
| CTRL-W H/J/K/L     | Move window to edge.             |
| CTRL-W _           | Maximize window height.          |
| CTRL-W \<pipe\>    | Maximize window width.           |
| CTRL-W =           | Equalize window sizes.           |
| CTRL-W o           | Close all but current window.    |
| CTRL-W\_CTRL-N     | Open a new empty file in a split |
| :sp/:vsp file.c    | Open a file in a split.          |

### Tabs

| **Command or Key**        | **Description**                       |
|:--------------------------|:--------------------------------------|
| :tabe file.c              | Open a new tab.                       |
| :tab sp                   | Open the current buffer in a new tab. |
| :tabc                     | Close the current tab page.           |
| :tabo                     | Close all but the current tab page.   |
| CTRL-PageUp/Down or :gt/T | Switch between tab pages.             |
| :(+/-[N])tabm             | Move tab.                             |

# General Plugins
### [vim-table-mode](https://github.com/dhruvasagar/vim-table-mode)

| **Command or Key** | **Description**                                   |
|:-------------------|:--------------------------------------------------|
| \<leader\>tm       | Toggle table-mode.                                |
| \<leader\>tdd      | Delete row.                                       |
| \<leader\>tdc      | Delete column.                                    |
| i/a\<pipe\>        | Inner/outer cell text object. Use with d, v, etc. |

### [ctrlp](https://github.com/ctrlpvim/ctrlp.vim)

| **Command or Key** | **Description**                                     |
|:-------------------|:----------------------------------------------------|
| CTRL-P             | Open ctrlp find file menu.                          |
| F5                 | Refresh file list.                                  |
| CTRL-F/B           | Cycle search modes (file, buffer, mru).             |
| CTRL-D             | Switch between path and filename only search modes. |
| CTRL-J/K           | Navigate results.                                   |
| CTRL-T/V/X         | Open selected entry in new tab or split.            |
| CTRL-N/P           | Navigate prompt history.                            |
| CTRL-Y             | Create a new file, including parent directories.    |
| CTRL-Z             | Mark files.                                         |
| CTRL-O             | Open marked files.                                  |

### [fugitive](https://github.com/tpope/vim-fugitive)

| **Command or Key** | **Description**                                             |
|:-------------------|:------------------------------------------------------------|
| :Gstatus           | Open git status.                                            |
| cc (in status)     | Execute git commit.                                         |
| - (in status)      | Add/reset a files changes.                                  |
| p (in status)      | Add/reset a files changes with --patch.                     |
| :Gcommit           | Commit changes.                                             |
| :Gpush             | Execute git push, loading results into quickfix list (:cw). |
| :Gdiff             | Diff staged version of file with working tree version.      |
| :Gblame            | Open git blame.                                             |
| ENTER (in blame)   | Edit commit.                                                |
| o (in blame)       | Edit commit in a split.                                     |
| :Gedit (in blame)  | Return to working tree version.                             |
| :Gmove             | Executes git mv and renames buffer.                         |
| :Gdelete           | Executes git rm and deletes buffer.                         |
| :Ggrep             | Search working tree or commit with git grep.                |
| :Glog              | Load all revisions of file into quickfix list (:cw).        |
| :Gread             | git checkout on buffer.                                     |
| :Gwrite            | Writes to both working tree and index versions of file.     |
| :Git               | Run a git command.                                          |
| :Git!              | Open output of a command in a temp file.                    |

# Clojure Plugins
### [vim-fireplace](https://github.com/tpope/vim-fireplace)
*Note: You need to start a REPL for most fireplace commands to work.*  

| **Command or Key** | **Description**                                             |
|:-------------------|:------------------------------------------------------------|
| K                  | Lookup symbol with doc.                                     |
| [d                 | Lookup symbol with source.                                  |
| [<C-D>             | Jump to symbol definition.                                  |
| gf                 | Vim go to file command--works on namespaces.                |
| cpp                | Evaluate innermost form.                                    |
| cp{motion}         | Evaluate the code indicated by {motion}.                    |
| cqc                | Open command line window.                                   |
| cqq                | Open command line window, prepopulated with innermost form. |

### [vim-sexp](https://github.com/guns/vim-sexp)

| **Command or Key**          | **Description**                                       |
|:----------------------------|:------------------------------------------------------|
| ( and )                     | Move to nearest paired structural bracket.            |
| [[ and ]]                   | Move cursor to adjacent top-level element.            |
| [e and ]e                   | Select adjacent element.                              |
| ==                          | Indent compound form without moving cursor.           |
| =-                          | Indent top-level compound form without moving cursor. |
| \<localleader\>i/I          | Wrap compound form with () and enter insert mode.     |
| \<localleader\>[/]          | Wrap compound form with [] and enter insert mode.     |
| \<localleader\>w/W          | Wrap element with () and enter insert mode.           |
| \<localleader\>e[/e]        | Wrap element with [] and enter insert mode.           |
| \<localleader\>e{/e}        | Wrap element with {} and enter insert mode.           |
| \<localleader\>@            | Splice compound form into parent.                     |
| \<localleader\>o            | Raise compound form, replacing parent.                |
| \<localleader\>O            | Raise element, replacing compound form.               |
| ALT-j/k                     | Swap compound form with sibling element.              |
| ALT-h/l                     | Swap element with sibling element.                    |
| \<localleader\>b/B (custom) | Emit terminal elements (barf).                        |
| \<localleader\>s/S (custom) | Capture adjacent elements (slurp).                    |
| \<localleader\>h            | Insert cursor at head of compound form.               |
| \<localleader\>l            | Insert cursor at tail of compound form.               |

