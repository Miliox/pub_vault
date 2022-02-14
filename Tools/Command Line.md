
# Packages
* [alacritty](https://alacritty.org/)
* [cppman](https://github.com/aitjcize/cppman)
* [cheat](https://github.com/cheat/cheat)
* [cling](https://github.com/root-project/cling)
* [ffmpeg](https://www.ffmpeg.org/)
* [fzf](https://github.com/junegunn/fzf) 
* [ghidra](https://ghidra-sre.org/)
* [image magick](https://imagemagick.org/)
* [most](https://www.cyberciti.biz/faq/unix-linux-color-man-pages-configuration/)
* [neo-vim](https://neovim.io/)
* [procs](https://github.com/dalance/procs)
* [pygments](https://pygments.org/)
* [ripgrep](https://github.com/BurntSushi/ripgrep)
* [rsync](https://rsync.samba.org/)
* [sd](https://github.com/chmln/sd)
* [htop](https://htop.dev/)
* [howdoi](https://github.com/gleitz/howdoi)
* [tealdeer](https://github.com/dbrgn/tealdeer)
* [tmux](https://github.com/tmux/tmux) 
* [todo.txt](http://todotxt.org/)
* [xclip](https://linux.die.net/man/1/xclip)

## Ubuntu
```bash
packages=('cppman'
          'fd-find'
          'ffmpeg'
          'fzf'
          'git'
          'graphviz'
          'hdf5-tools'
          'imagemagick'
          'most'
          'neovim'
          'ripgrep'
          'rsync'
          'pv'
          'tmux'
          'xclip'
          'todotxt-cli')

sudo apt update
sudo apt install ${packages[*]}
```

## Python
```bash
packages=('gdbgui'
          'howdoi'
          'pygments')

pip3 install ${packages[*]}
```

## Rust
```bash
# Install instructions:
# https://www.rust-lang.org/tools/install

packages=('procs'
          'sd'
          'tealdeer')

cargo install ${packages[*]}
```

## macOS / Brew
```bash
# Install instructions:
# https://brew.sh/

packages=('cling'
          'cmake'
          'cppman'
          'erlang'
          'fd'
          'ffmpeg'
          'fzf'
          'gcc'
          'gdb'
          'git'
          'graphviz'
          'htop'
          'imagemagick'
          'lua'
          'most'
          'neofetch'
          'pv'
          'ripgrep'
          'tmux'
          'youtube-dl')

brew update
brew install ${packages[*]}
```