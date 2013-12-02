#Ubuntu Installation Notes

##Gnome

    $ sudo add-apt-repository ppa:gnome3-team/gnome3
    $ sudo apt-get update
    $ sudo apt-get install gnome-shell
    
[Install Gnome on Ubuntu 12.04](http://www.filiwiese.com/installing-gnome-on-ubuntu-12-04-precise-pangolin/)

> *Note:* On Ubuntu 13.10, installing Gnome 3.10 will **break** some of the existing futures, even the display manager.
>
> *Note:* Ubuntu 13.10 ships with the Gnome 3.8 repositories by default, so you can skip **_add-apt-repository_**

##Bottom Taskbar (GNOME 3)

    $ sudo apt-get install tint2
    $ tint2 &
    
    alt + f2
	
	  gnome-session-properties

	  add
	  Name: tint2 task bar
	  Command: tint2

##Guard
###cURL

    $ sudo apt-get update
    $ sudo apt-get install curl
    $ curl -L https://get.rvm.io | bash -s stable
    $ source ~/.rvm/scripts/rvm
    $ rvm requirements
		
###Ruby

    $ rvm install ruby
    $ rvm use ruby --default
		
###Ruby Gems

    $ rvm rubygems current
 
###Guard

    $ gem install guard
    // $ gem install rb-fsevent
    // $ gem install guard-sass
    // $ gem install guard-coffeescript
    // $ gem install guard-livereload
    // $ gem install guard-concat
    // $ gem install guard-uglify
    
In some cases you will encounter an error while installing the gem. Install the following packages and gems, and return to the previous one

	$ sudo apt-get --yes --force-yes install libxslt1-dev libxml2-dev ruby-dev
	$ gem install rdoc
		
###LiveReload (plugin for chrome)

##xDebug

    sudo apt-get install php5-dev php-pear
    sudo pecl install xdebug
    sudo nano /etc/php5/conf.d/xdebug.ini
    
in xdebug.ini

    ; xdebug debugger
    zend_extension="/usr/lib/php5/20060613/xdebug.so"
    xdebug.remote_enable=1
    xdebug.remote_handler=dbgp
    xdebug.remote_mode=req
    xdebug.remote_host=127.0.0.1
    xdebug.remote_port=9000
    xdebug.var_display_max_depth = 8

    sudo /etc/init.d/apache2 restart
    
##Apache2 - php.ini

    sudo nano /etc/php5/apache2/php.ini
    
    display_errors = On 	
    error_reporting = On
    html_errors = On
    // care for overrides
    
##Composer (PHP Package Manager)

    curl -sS https://getcomposer.org/installer | php
    sudo mv composer.phar /usr/local/bin/composer

##Create a Laravel project using Composer

    composer create-project laravel/laravel --prefer-dist

##Color the command prompt

http://www.cyberciti.biz/faq/bash-shell-change-the-color-of-my-shell-prompt-under-linux-or-unix/
http://www.thegeekstuff.com/2008/09/bash-shell-ps1-10-examples-to-make-your-linux-prompt-like-angelina-jolie/

    nano ~/.bashrc
    alias PSlong='PS1="\[\033[01;32m\]\u\[\033[m\]@\h:\\w\\$ "'
    alias PSshort='PS1="\[\033[01;32m\]\W\[\033[m\]:$ "'






