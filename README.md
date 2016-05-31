# My .vim files

My personal `.vim` files. This repository includes my `~/.vimrc`, `~/.vim`
dir, and the plugins I use as git submodules. This repository basically
includes my entire vim setup so that I can easily load it onto other systems
and have history of it. The idea was adapted heavily (OK, stolen) from @cyphactor's dotvim
project <https://github.com/cyphactor>. I merged my .vimrc with his and have
built a powerful set of editing tools. 

It seems like it's out here to share with the world. That's great if you glean
something from it, but my real reason is to make sure I can move this around
from machine to machine. Altruism is really just a side effect of convenience
in this case. Feel free to steal what you'd like, though.

## Installation:

    git clone git://github.com/bikeonastick/dotvim.git 

    cd dotvim
    git submodule init
    git submodule update
    ln -s `pwd` ~/.vim
    ln -s `pwd`/vim-plug/plug.vim `pwd`/autoload/plug.vim
    ln -s `pwd`/vimrc ~/.vimrc
    ln -s `pwd`/gvimrc ~/.gvimrc

## Upgrade

    cd ~/.vim

    git pull
    git submodule init
    git submodule update

## Color Scheme

My `.vimrc` is setup to use the Solarized Color Scheme which can be found at
[http://ethanschoonover.com/solarized](http://ethanschoonover.com/solarized).
My `.vim` directory includes this color scheme as Git submodule just like all
the plugins. The reason I mention this is because I have it configured to use
the non 256 degraded Vim color version. This requires that you are using the
Solarized Color Scheme for your terminal application as well. I for example am
using [iTerm 2](http://www.iterm2.com/) with the Solarized iTerm 2 color scheme
presets.

## Quick Guide

### Functionality Provided by my vimrc

The `<leader>` key in my `.vimrc` is set to the `,` key.

#### Tab Completion

In insert mode when you start typing and hit tab it will bring up the tab completion interface.

* `<leader>n` - rename the current file
* `<leader>.` - switch between test & implementation code (assumes RSpec, Cucumber, and Ruby)

#### Running Tests

* `<leader>t` - run all tests defined in the current file and store as last test run if in test file, run last stored test run if in implementation file.
* `<leader>T` - run test nearest cursor in current file and store as last test run if in test file, run last stored test run if in implementation file.
* Cuke - run cuke on current file
* CukeL - run cuke on this line of the current file
* Spec - run rspec on this file
* SpecL - run rspec on this line of the current file
* Zcuke - run local cukes through Zeus
* ZcukeL - run cuke test at current cursor line through Zeus
* Zspec - run local cukes through Zeus
* ZspecL - run test at current line local rspec through Zeus
* Vcuke - run current cuke file on your vagrant box
* VcukeL - run current cuke test line on your vagrant box
* Vspec - run current rspec file on your vagrant box
* VspecL - run current rspec test line on your vagrant box

#### Search Commands

* Ackw does an ack search on the project for the word under the cursor
* Srchv - search project by file extension and grep for selected text
* Ackv - search all project files via ack for selected text
* Ackx - calls ack with whatever is passed as an argument (be sure to quote strings with spaces"
* SrchR - recursive find by file type (ruby) for specific word
* SrchG - recursive find by file type (groovy) for specific word
* SrchJava - recursive find by file type (java) for specific word
* SrchJs - recursive find by file type (javascript) for specific word
* SrchGsp - recursive find by file type (gsp) for specific word

#### Execute commands

* Rb - current file in ruby
* Puplint - puppet-lint on current file

### Plugin Provided Functionality

The following are plugins that my .vim directory includes as Git submodules for
easy upgrading. Below I also provide the commands that I find I use most often
from each of the plugins.

#### vim-surround

Provides functionality to easily manage surroundings parens, quotes, etc.
[http://github.com/tpope/vim-surround](http://github.com/tpope/vim-surround)

* `cst'` - change surrounding html tag to single quotes 
* `cs'<p>` - change surrounding single quotes to `<p>` html tag
* `cs'"` - change surronuding single quotes to double quotes
* `ds"` - delete surrounding double quotes
* `ysiw'` - add surrounding of single quote inside word (iw) where iw is a text object

#### tcomment_vim

Provides easy to use file-type sensible comments.
[http://github.com/tomtom/tcomment_vim](http://github.com/tomtom/tcomment_vim)

* `gc{motion}` - toggle comments
* `gC{motion}` - comment region
* `gcc` - toggle comment current line
* `gCc` - comment current line
* `gc` (visual mode) - toggle comments
* `gC` (visual mode) - comment selected text

#### gist-vim

Provides easy creation of GitHub Gists.
[http://github.com/mattn/gist-vim](http://github.com/mattn/gist-vim)

* `:Gist` - post current buffer to gist
* `:'<,'>Gist` - post current selection to gist
* `:Gist -p` - create private gist
* `:Gist -P` - create public gist
* `:Gist -l` - list your public gists

#### ack.vim

Provides interface to Ack from within vim.
[http://github.com/mileszs/ack.vim](http://github.com/mileszs/ack.vim)

* `:Ack [options] {pattern}` - search for specified pattern showing results in vim quick fix window.

#### vim-rails

Provides bunch of Ruby on Rails specific functionality.
[http://github.com/tpope/vim-rails](http://github.com/tpope/vim-rails)

* `gf` - gives the standard `gf` command knowledge about partials, fixtures, and much more.

#### vim-markdown

Provides syntax highlighting for Markdown files.
[http://github.com/tpope/vim-markdown](http://github.com/tpope/vim-markdown)

#### vim-cucumber

Provides syntax highlighting for Cucumber features and step definitions
[http://github.com/tpope/vim-cucumber](http://github.com/tpope/vim-cucumber)

#### vim-fugitive

Provides full blown Git interface inside of Vim. This is very valuble in my
opinion and is worth spending some time learning as it will make your life much
easier.
[http://github.com/tpope/vim-fugitive](http://github.com/tpope/vim-fugitive)

#### vim-ctrlp

[https://github.com/kien/ctrlp.vim](https://github.com/kien/ctrlp.vim)

#### vim-matchit

[http://www.vim.org/scripts/script.php?script_id=39](http://www.vim.org/scripts/script.php?script_id=39)

#### ruby-matchit

[https://github.com/vim-scripts/ruby-matchit](https://github.com/vim-scripts/ruby-matchit)

#### vim-elixir

[https://github.com/elixir-lang/vim-elixir.git](https://github.com/elixir-lang/vim-elixir.git)
