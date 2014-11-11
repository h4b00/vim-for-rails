# Vim for Ruby on Rails :) 

## Information

This package of vim  in my opinion contains bunch of best plugins for rails environment development.
* To speed up your coding we use [Snipmate Snippets](https://github.com/honza/vim-snippets)
* To avoid bugs we use [rubocop](https://github.com/ngmy/vim-rubocop) with syntastic.
* To protect the eyes we use [railscast](https://github.com/ryanb/dotfiles/blob/master/vim/colors/railscasts.vim) theme.
* To protect nerves, installation is quick and simple.

## Installation

### Requirements

* **Linux**
* **Vim/Gvim**
* **Ruby, Bundler, Rails**
* **Git**

To install requirements run(Ubuntu/Mint/Debian only):
```
sudo apt-get install vim vim-gtk git curl ack-grep clang xclip
```
## Setup

```
# Clone the repository:
cd ~/
git clone https://github.com/h4b00/vim-for-rails .vim-for-rails
cd .vim-for-rails

# Install Vundle
git submodule init
git submodule update
```
Now you have to install gems run `bundle install`

and at the end you have to run Rakefile.

* `rake vim:install` if you it's your first installation of vim 
* `rake vim:install[force]` if you want to overwrite your current config

**In overwrite mode, script automatically makes backups config files before it overwrite them**

## Keyboard

`Leader` = `,`

In insertion mode you can use autocomplete function by pressing `tab`

| Keys          | Action        |
| ------------- |:-------------:|
| **Saving** | |
| `CTRL` + `s`| Save current file (Insertion, normal mode)|
| `CTRL` + `ALT` + `w` | Write and quit. |
| **Split/Copy/Paste/Format** | |
| `Leader` + `v`| Split window vertically and switch to it.|
| `Leader` + `h`| Split window horizontally and switch to it.|
| `Leader` + `t`| Run [ctags](http://en.wikipedia.org/wiki/Ctags) silently. |
| `Leader` + `p`| Paste from clipboard.|
| `Leader` + `y`| Copy to clipboard. |
| `Leader` + `=`| Format whole file. |
| **Navigation** | |
| `F1` | Toggle NERDTreeTabs. |
| `CTRL` + `a`| Move cursor at the beginning of a line.)|
| `CTRL` + `e`| Move cursor at the end of a line.|
| `CTRL` + `t` | Open new tab. |
| `CTRL` + `ALT` + `n`| Open new tab with the content of current text file. |
| `ALT` + `Left`| Previous tab. |
| `ALT` + `Right` | Next tab. |
| `ALT` + *n* | Move to *n*-th tab, where n is from 0..9. |
| **Upper/Lower -case** | |
| `Leader` + `u` | Uppercase all letters of current word. |
| `Leader` + `l` | Lowercase all letters of current word. |
| `Leader` + `w` + `u`| Uppercase first letter of current word.|
| `Leader` + `w` + `l`| Lowercases first letter of current word.|
| `Leader` + `c` + `d`| Change directory to the directory containing the file in the buffer.|
| `Leader` + `g` + `w`| Swap two words. |
| **Search** | |
| `F2` | Start CtrlP search dirs only. |
| `F3` or `Leader` + `f` | Start CtrlP search.|
| `F4` | Start CtrlP search in open buffers. |
| `F5` | Start Ack|
| `Leader` + `g` + `u` | Toggle Gundo undo list. 
| `Leader` + `Space`| Get rid of all search highlights. |
| `Leader` + `s` + `h`| Toggle highlight of search results. |
| `Leader` + `e` + `v` | CtrlP search in app/views. |
| `Leader` + `e` + `c` | CtrlP search in app/controllers.|
| `Leader` + `e` + `m` | CtrlP search in app/models. |
| `Leader` + `r` + `o` | Go straight to config/routes.rb |
| `F10` or `Leader` + `r` + `m` | Choose from app/models. |
| `F11` or `Leader` + `r` + `v` | Choose from app/views. |
| `F12` or `Leader` + `r` + `c` | Choose from app/controllers. |
| **Fugitive**| |
| `Leader` + `g` + `a` | Git add  |
| `Leader` + `g` + `s` | Show git status|
| `Leader` + `g` + `c` | Commit changes of current file|
| `Leader` + `g` + `d` | See diff of current file.|
| `Leader` + `g` + `b` | Git blame current file |
|**GUI**||
| `CTRL` + `o` | Dialog for open file. |
| `CTRL` + `ALT` + `s` | Save as dialog. |
| `CTRL` + `ALT` + `f` | Choose font dialog. |
