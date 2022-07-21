# VIM Setup

## VIM folder directory structure

```bash
.vim/
 |--- autoload/
 |--- backup/
 |--- colors/
 |--- plugged/
```

```bash
mkdir -p ~/.vim ~/.vim/autoload ~/.vim/backup ~/.vim/colors ~/.vim/plugged
```

## Installing Plugins

Install your preferred vim plugin manager. In this case, we recommend vim-plug plugin manager.

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Now installing plugins is as easy as adding the Plug 'username/plugin-name' string you find
on GitHub in between the function calls.

Finally open vim and type :PlugInstall to download and install the plugins.

## Adding ColorSchemes

Installing a colorscheme is as simple as adding a <colorscheme>.vim file to the ~/.vim/colors/ directory.

We will add the popular color scheme molokai:

```bash
cd ~/.vim/colors
curl -o molokai.vim https://raw.githubusercontent.com/tomasr/molokai/master/colors/molokai.vim
```

To load the colorscheme by default when opening vim, add the below section to
the Vimscript section of the .vimrc with the full path to the colorscheme

```vim
if filereadable(expand("$HOME/.vim/colors/<colorscheme>.vim"))
    " Set the colorscheme
    colorscheme <colorscheme>.vim
endif
```

## Creating .vimrc

Copy the .vimrc.sample file that you received with this repository

```bash
cp .vimrc.sample ~/.vimrc
```
