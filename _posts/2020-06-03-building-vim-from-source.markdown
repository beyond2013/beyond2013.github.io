---
layout: default
title:  "Building vim from source"
date:   2020-06-23 11:35 
comments: true
categories: vim building-from-source
---

I have been using vim for almost more than 5 years. As I upgrade from one LTS to another I usually forget how to build vim from source, therefore I am recording the steps here:

1. Removing vim if its already installed
```
sudo apt remove vim vim-runtime gvim
```
2. Installing prerequisite libraries
```
sudo apt install libncurses5-dev libgnome2-dev libgnomeui-dev \
libgtk-3-dev libatk1.0-dev libbonoboui2-dev \
libcairo2-dev libx11-dev libxpm-dev libxt-dev python-dev \
python3-dev ruby-dev lua5.1 liblua5.1-dev libperl-dev 
```
3. Cloning the source from [git repo](https://github.com/vim/vim.git) `git clone https://github.com/vim/vim.git`
4. change to vim directory `cd  vim`
5. configure vim 
```
./configure --with-features=huge \
         --enable-multibyte \
         --enable-rubyinterp=yes \
         --enable-python3interp=dynamic \
         --with-python3-command=/usr/bin/python3.10 \
         --with-python-config-dir=/usr/lib/python3.10/config-3.10-x86_64-linux-gnu \
         --with-x \
         --enable-perlinterp=yes \
         --enable-luainterp=yes \
         --enable-gui=gtk3 \
         --enable-cscope \
         --enable-fail-if-missing \
         --prefix=/usr/local
```
6. Make install
```
make
sudo make install
```
7. set vim as default editor 
```
sudo update-alternatives --install /usr/bin/editor editor /usr/local/bin/vim 1
sudo update-alternatives --set editor /usr/local/bin/vim
sudo update-alternatives --install /usr/bin/vi vi /usr/local/bin/vim 1
sudo update-alternatives --set vi /usr/local/bin/vim
```
One of the problems(at least for now) is that vim does not compile with both python and python3 support. The current build is using python3 support. 

For plugin management I am using [minpac](https://github.com/k-takata/minpac).

