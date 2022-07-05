---
# can edit: title, date, categories, and tags
layout: post
title: "Installation Process of Jekyll"
date: 2022-05-28 24:00:00 -0500
categories: [Installation]
tags: [Installation, Homelab]
---

### Installation of Ruby and other requirements:
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```
### Configuration of Ruby Gems (do not want to install them as root user)
```bash
echo '\n# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
### Install bundler
```shell
gem install jekyll bundler
```
### Running Jekyll-Based site
 You will want to run the command:
 ```shell
 bundle
 ```
 just to make sure that gems dependencies are installed and checked.

 To execure and serve (locally) a Jekyll site, run:
 ```shell
 bundle exec jekyll serve
 ```

 ### Notes:

 You may have to change the permissions of the directory you hold your repo in.
 If it looks like: `drwxrwxrwx 1 root 197609 0 Jun 18 22:23 {placeholder}.github.io/`, you will need to use `sudo chown -R $USER:$USER <filepath>`

 _Revision 0.1 - 5/28/2022: Initial Upload_