## Arch Linux Pacman package for Rust Web Server

### Install rws as Pacman package

#### 1. Install Rust 

> pacman -S rust
 
#### 2. Install required developer tools

> pacman -S base-devel

#### 3. Build package

> cd ~

> mkdir git 

> cd git

> git clone git@github.com:bohdaq/rws-arch-package.git

> cd rws-arch-package
 
> makepkg

> ls -l


Replace _VERSION_ with version you've built.

> sudo pacman -U rust-web-server-_VERSION_.pkg.tar.zst


### Test installation:
> rws

Press Ctrl + C (or CMD + C) to stop server.

### To remove rws:
> pacman -Rs rust-web-server
