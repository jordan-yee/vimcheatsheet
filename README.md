# Vim Cheat Sheet
#### A quick reference for how to do useful things in Vim.

| **[Vim Core](#vim-core)** | **[General Plugins](#general-plugins)** | **[Clojure Plugins](#clojure-plugins)** |
|---------------------------|-----------------------------------------|-----------------------------------------|
| [Files](#files)           | [table-mode](#table-mode)               | [fireplace](#fireplace)                 |
| [Windows](#windows)       | [ctrlp](#ctrlp)                         | [sexp](#sexp)                           |
| [Tabs](#tabs)             | [fugitive](#fugitive)                   |                                         |
| [Diff Mode](#diff-mode)   | [surround](#surround)                   |                                         |
| [Misc](#misc)             |                                         |                                         |

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
| :cw                | Open quickfix window.            |

### Tabs

| **Command or Key**        | **Description**                       |
|:--------------------------|:--------------------------------------|
| :tabe file.c              | Open a new tab.                       |
| :tab sp                   | Open the current buffer in a new tab. |
| :tabc                     | Close the current tab page.           |
| :tabo                     | Close all but the current tab page.   |
| CTRL-PageUp/Down or :gt/T | Switch between tab pages.             |
| :(+/-[N])tabm             | Move tab.                             |

### Diff Mode

| **Command or Key** | **Description**                                   |
|:-------------------|:--------------------------------------------------|
| :diffs {file}      | Compare current window with {file}.               |
| \[c and \]c        | Jump to next/previous diffs.                      |
| do                 | Set diff in cuffent buffer to match other buffer. |
| dp                 | Set other buffer to match diff in current buffer. |

### Misc

| **Command or Key**   | **Description**                                            |
|:---------------------|:-----------------------------------------------------------|
| gx                   | Open URL under cursor in a browser.                        |
| CTRL-O (insert mode) | Execute a normal mode command without leaving insert mode. |
| :ret                 | Convert tabs to spaces.                                    |

# General Plugins
### [table-mode](https://github.com/dhruvasagar/vim-table-mode)

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
| :Gw                | Write to file and stage results.                            |
| :Gcommit           | Commit changes.                                             |
| :Gpush             | Execute git push, loading results into quickfix list (:cw). |
| :Gpull             | Execute git pull, loading errors into quickfix list (:cw).  |
| :Gdiff             | Diff staged version of file with working tree version.      |
| :Gmove             | Executes git mv and renames buffer.                         |
| :Gdelete           | Executes git rm and deletes buffer.                         |
| :Glog              | Load all revisions of file into quickfix list (:cw).        |
| :Git               | Run a git command.                                          |
| :Git!              | Open output of a command in a temp file.                    |

### [surround](https://github.com/tpope/vim-surround)

| **Command or Key**                  | **Description**                                                              |
|-------------------------------------|------------------------------------------------------------------------------|
| ds{surrounding}                     | Delete surrounding instances of {surrounding}. ex: ds"                       |
| cs{current}{new}                    | Change surrounding instances of {current} with {new}. ex: cs"'               |
| ys{motion/text object}{surrounding} | Surround region selected by {motion/text object} with {surrounding}          |
| yss{surrounding}                    | Surround current line with {surrounding}, ignoring leading whitespace.       |
| yS / YSS                            | Same as ys/yss, but places surrounded text on its own line.                  |
| S{surrounding} (visual mode)        | Surround selection with {surrounding} (visual mode).                         |
| {surrounding} (brackets)            | (, ), {, }, [, ], <, and >. Opening adds inner whitespace, closing doesn't.  |
| {surrounding} (quotes)              | ', ", and `. These are only searched for on current line.                    |
| {surrounding} (tags)                | t or <tagname. ex: typing yswtdiv<enter> will surround a word with div tags. |

# Clojure Plugins
### [fireplace](https://github.com/tpope/vim-fireplace)
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

### [sexp](https://github.com/guns/vim-sexp)

| **Command or Key**      | **Description**                                       |
|:------------------------|:------------------------------------------------------|
| ( or )                  | Move to nearest paired structural bracket.            |
| [[ or ]]                | Move cursor to adjacent top-level element.            |
| [e or ]e                | Select adjacent element.                              |
| ==                      | Indent compound form without moving cursor.           |
| =-                      | Indent top-level compound form without moving cursor. |
| \<localleader\>i or I   | Wrap compound form with () and enter insert mode.     |
| \<localleader\>[ or ]   | Wrap compound form with [] and enter insert mode.     |
| \<localleader\>w or W   | Wrap element with () and enter insert mode.           |
| \<localleader\>e[ or e] | Wrap element with [] and enter insert mode.           |
| \<localleader\>e{ or e} | Wrap element with {} and enter insert mode.           |
| \<localleader\>@        | Splice compound form into parent.                     |
| \<localleader\>o        | Raise compound form, replacing parent.                |
| \<localleader\>O        | Raise element, replacing compound form.               |
| ALT-j or k              | Swap compound form with sibling element.              |
| ALT-h or l              | Swap element with sibling element.                    |
| \<localleader\>h        | Insert cursor at head of compound form.               |
| \<localleader\>l        | Insert cursor at tail of compound form.               |
| af/if (Text Object)     | Select outer/inner list.                              |
| aF/iF (Text Object)     | Select outer/inner top-level list.                    |
| as/if (Text Object)     | Select outer/inner string.                            |
| ae/ie (Text Object)     | Select outer/inner element.                           |

| **Custom Binds**      | **Description**                    |
|:----------------------|:-----------------------------------|
| \<localleader\>b or B | Emit terminal elements (barf).     |
| \<localleader\>s or S | Capture adjacent elements (slurp). |

| [**vim-sexp-mappings-for-normal-people**](https://github.com/tpope/vim-sexp-mappings-for-regular-people) | **Description**                             |
|:---------------------------------------------------------------------------------------------------------|:--------------------------------------------|
| W/B                                                                                                      | Move to beginning of next/previous element. |
| E/gE                                                                                                     | Move to tail of next/previous element.      |
| \>f/\<f                                                                                                  | Move a form right/left.                     |
| \>e/\<e                                                                                                  | Move an element right/left.                 |
