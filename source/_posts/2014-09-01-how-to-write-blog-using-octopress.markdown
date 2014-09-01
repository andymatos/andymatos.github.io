---
layout: post
title: "how to write blog using octopress"
date: 2014-09-01 19:36:56 +0800
comments: true
categories: [octopress,blog]
---

#Get Ready

##what's need

git Ruby DevKit Python Octopress

#Install

##Install Ruby

Remember “Add Ruby executables to your PATH”

Use ruby -version in cmd to test.

##Install DevKit

Directory should with out chinese and space.

cd DevKit

ruby dk.rb init

ruby dk.rb install

##Install Octopress

git clone git://github.com/imathis/octopress.git octopress

cd octopress


gem sources -a http://ruby.taobao.org/

gem sources -r http://rubygems.org/

gem sources -l


gem install bundler

rbenv rehash

bundle install


rake install

#To use chinese

1.In  environment variable set

LANG=zh_CN.UTF-8

LC_ALL=zh_CN.UTF-8

2.save the file as UTF-8 without BOM

3.find file convertible.rb

C:\Ruby193\lib\ruby\gems\1.9.1\gems\jekyll-0.12.0\lib\jekyll\convertible.rb

replace line 27 with：self.content = File.read(File.join(base, name), :encoding => 'utf-8')

#Blog Posts

1.rake new_post["title"]

the markdown file is stored in the source/_posts

2.rake generate

3.rake preview

use localhost:4000 to preview

#Deploying to Github Pages

1.Create a new Github repository and name the repository with the format username.github.io, where username is your GitHub user name or organization name.

2.change to Octopress directory

rake setup_github_pages

git@github.com:username/username.github.io.git

3.rake generate

4.rake deploy

5.commit the source 
git add .
git commit -m 'your message'
git push origin source