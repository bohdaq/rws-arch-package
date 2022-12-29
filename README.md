## Arch Linux Pacman package for Rust Web Server

### To install rws as Pacman package:

- Make sure you have Rust installed.

> pacman -S rust

- Clone repository

> cd rws-arch-package
> 
> makepkg

- You may need to run commands listed below as an administrator

Replace _VERSION_ with version you've built.

> pacman -U rust-web-server-_VERSION_.pkg.tar.zst


### Test installation:
> rws

Press Ctrl + C (or CMD + C) to stop server.

### To remove rws:
> pacman -Rs rust-web-server
