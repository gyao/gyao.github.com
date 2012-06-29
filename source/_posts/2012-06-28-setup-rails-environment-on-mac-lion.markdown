---
layout: post
title: "Setup rails environment on Mac Lion"
date: 2012-06-28 16:25
comments: true
categories: 
---

This post logs the "best practice" of setup rails development environment.

<!--more-->

Prepare 
----
* Install [XCode](http://itunes.apple.com/us/app/xcode/id448457090?mt=12)
* Install [osx-gcc-installer](https://github.com/kennethreitz/osx-gcc-installer)
* Install [homebrew](http://github.com/mxcl/homebrew)
```bash
ruby -e "$(curl -fsSL https://gist.github.com/raw/323731/install_homebrew.rb)"
```

Install MySQL
----
* Download [MySQL](http://www.mysql.com/downloads/mysql/)
* Install 
	* mysql-5.5.20-osx10.6-x86_64.pkg for MySQL installation
	* MySQL.prefPane to install MySQL panel on System Preference
	* MySQLStartupItem.pkg to start up MySQL when system boot
* Start / stop MySQL service through MySQL panel on System Preference
* Install [Sequel Pro](http://www.sequelpro.com/) as MySQL GUI

Install imagemagick
----
```bash
brew install imagemagick 
```

Install rvm
----
rvm is a ruby version management tool to allow install and switch multiple versions of ruby interpreter.
```bash
bash <<( curl http://rvm.beginrescueend.com/releases/rvm-install-head )
```

Edit profile, add following line at the bottom of ~/.zshrc
```bash ~/.zshrc
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
```

Activate profile
```bash
source ~/.zshrc
```

Install ree
----
```bash
rvm install ree --force
```

Switch ruby interpreter to ree
```bash
rvm ree --default
```

Install Essential gems
----
```bash
gem install rails
gem install rails -v=3.0.7 
gem install mysql2
gem install passenger
gem install nokogiri
gem install capistrano
gem install capistrano-ext 
gem install delayed_job
gem install hoptoad_notifier
gem install facebooker2
gem install factory_girl
gem install sphinx
```

Install Pow as HTTP Server
----
Pow is a zero configure http server.

Installation
```bash
curl get.pow.cx | sh
```

Setup, well, I'm lying before…
```bash
cd ~/.pow/
ln -s ~/dir/to/your/rails/project
```

Project settings for pow
```bash
cd /dir/to/your/rails/project
echo "rvm your_ruby_interpreter" > .rvmrc
```

Resolve mysql2 Adapter Issue Under rvm
----
```bash
sudo install_name_tool -change libmysqlclient.18.dylib /usr/local/mysql/lib/libmysqlclient.18.dylib ~/.rvm/rubies/ruby-1.9.2-p290/lib/ruby/gems/1.9.1/gems/mysql2-0.3.11/lib/mysql2/mysql2.bundle 
```
