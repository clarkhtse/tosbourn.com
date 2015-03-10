---
layout: post
status: publish
published: true
title: Setting up Redmine from a blank Ubuntu install
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1120
wordpress_url: http://tosbourn.com/?p=1120
date: '2012-09-20 13:45:17 +0100'
date_gmt: '2012-09-20 12:45:17 +0100'
categories:
- Development Help
tags:
- Ubuntu
- Linux
- Redmine
- Ruby
comments: []
---
<p>Here is a dump of all the commands I typed in to install Redmine onto a blank Ubuntu install.</p>
<p>I am not saying this is the best way to do it (there are definitely better ways to install the dependencies ahead of time) but it worked for me.</p>
<pre><code>sudo apt-get update
sudo apt-get install build-essential
curl -L https://get.rvm.io | bash -s stable --rails
source /usr/local/rvm/scripts/rvm
rvm pkg install zlib
rvm remove 1.9.2
rvm install 1.9.2
rvm use 1.9.2 --default
gem install rails
sudo apt-get install mysql-server mysql-server-5.5 libmysql-ruby libmysqlclient-dev mysql-client-5.5 mysql-common
#Enter MySQL root password twice
gem install mysql2
gem install bundler
mkdir /home/redmine
cd /home/redmine
wget http://rubyforge.org/frs/download.php/76448/redmine-2.1.0.tar.gz
tar xzvf redmine-2.1.0.tar.gz
rm redmine-2.1.0.tar.gz 
mv redmine-2.1.0/* ./
rm -r redmine-2.1.0/
bundle install --without development test postgresql sqlite rmagick
mysql -uroot -proot_password
create database redmine character set utf8;
create user 'redmine'@'localhost' identified by 'redmine_password';
grant all privileges on redmine.* to 'redmine'@'localhost';
exit
cp config/database.yml.example config/database.yml
vi config/database.yml
#Edit databases to suit your needs
rake generate_secret_token
rvm pkg install openssl
rvm reinstall 1.9.2 --with-openssl-dir=$rvm_path/usr
RAILS_ENV=production rake db:migrate
RAILS_ENV=production rake redmine:load_default_data
#select your language
ruby script/rails server webrick -e production 
</code></pre>
