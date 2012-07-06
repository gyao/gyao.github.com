---
layout: post
title: "Bootstrap Mac"
date: 2012-07-06 15:06
comments: true
categories: mac, note
---

This post is an instruction of how to setup development environment on a Mac, including:

1. Basic development environment setup
2. Ruby / Rails environment setup

Also provides a easy way to bootstrap (NOTE: need network connection to run the script):


```bash
bash < <(curl -s https://raw.github.com/gyao/bootstrap-mac/master/mac)
bash < <(curl -s https://raw.github.com/gyao/bootstrap-mac/master/ruby)
```

<!-- more -->

## Basic Development Environment Setup

### 1. Install Xcode and install [Command Line Tools for XCode][1]

[1]:https://developer.apple.com/downloads/index.action


### 2. Generate SSH key pairs 

```bash
cd
mkdir .ssh
cd .ssh
ssh-keygen -t rsa
```

### 3. Install [homebrew][2]

[2]:http://mxcl.github.com/homebrew/

```bash
/usr/bin/ruby -e "$(/usr/bin/curl -fsSL https://raw.github.com/mxcl/homebrew/master/Library/Contributions/install_homebrew.rb)"
brew update
```

### 4. Install [zsh][3] and [oh-my-zsh][4]

[3]:www.zsh.org
[4]:https://github.com/robbyrussell/oh-my-zsh/

```bash
brew install zsh
wget --no-check-certificate https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```

### 5. Install [ack][5]

[5]:http://betterthangrep.com/

```bash
brew install ack
```

### 6. MacVim

```bash
brew install macvim
curl https://raw.github.com/carlhuda/janus/master/bootstrap.sh -o - | sh
```

### 7. [tmux][6]

[6]:tmux.sourceforge.net

```bash
brew install tmux
```

Or use following script to bootstrap

```bash
bash < <(curl -s https://raw.github.com/gyao/bootstrap-mac/master/mac)
```

## Ruby / Rails Environment Setup

Please refer to [another post of mine](/blog/2012/06/28/setup-rails-environment-on-mac-lion)

Also you could use following script to bootstrap ruby and rails development environment, after you installed MySQL.

```bash
bash < <(curl -s https://raw.github.com/gyao/bootstrap-mac/master/ruby)
```




