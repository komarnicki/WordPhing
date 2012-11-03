WordPhing
=========

WordPress build using Phing.

- Automated Installing WordPress from the command line (install script).
- Currently builds WordPress in about 30 seconds depending on your Internet connection and how many plugins/themes you include.
- Simple config file and command to run

If you want something that has a lot more features please check out WP-CLI.
https://github.com/wp-cli/wp-cli

Video: http://www.youtube.com/watch?feature=player_embedded&v=Y5eFQwgkgh4

*Phing has no dependencies other than PHP, so it will run anywhere PHP does (unlike Apache Ant/Cappicino/Rails, etc). It should work right out of the box.

## What does it do?

- Creates a new database (optional)
- Downloads and installs WordPress (latest stable)
- Download and installs plugins and themes
- Appends needed info to your wp-config
- Runs the WP install script

Some minor changes are made during install, they are;

- Removes Hello Dolly plugin (sry Matt).
- Removes default "Hello World" post, Sample Page, Links.
- Removes default Mr.Wordpress comment.
- Deletes readme.html and wp-sample-config.php


##Basic Instructions

- Open build.properties and fill it out. All the detials are found it build.properties and must be filled out.

2 Command options
- Type `"phing wp-install"`      Creates a database and WordPress
- Type `"phing wp-install-only"` Creates just WordPress (will not create the database)
- Type `"phing wp-zip"`          Creates a zip
- Type `"phing wp-gzip"`         Creates a gzip
- Type `"phing wp-doc"`          Runs PHP Documentor 2
- Type `"phing help"`            Command line options

The build will not overwrite existing directories or existing databases.
The file/dir permissions (chown)  are commented out by default to prevent issues on windows

##Requires

PHP 5.2 + & Phing.

Phing is already included in most default PHP installs. If you need to install it separately see "Install" below.

PHP Documentor 2 requires the latest Phing and XSL PHP extension. You can follow the instructions here if your install doesn not have it: http://www.phpdoc.org/

##Notes

If there are problems during install you can run WordPhing in debug and verbose modes or both.

For example: `"phing install -verbose -debug"`


##Todo

- Add git & svn support
- Add FTP support
- Theme minify (yui-compress and google closure)
- Moving, staging and backups (phing even has an amazon task)
- Run some tests (phpunit, phpmess)

##Install 

It is recommend you run `"pear upgrade phing/phing"` for the latest release.( required for PHP Documentor 2).

This script will eventually REQUIRES some optional libraries (http, git, svn, etc), so you can run `"pear install --alldeps phing/phing"` to get them.

- Seperate install if pear/phing is not included in your stack.

http://www.phing.info/docs/guide/stable/chapters/Setup.html#SystemRequirements

- PEAR package
http://pear.phing.info/

Thanks to: https://github.com/etivite/phing-wordpress-installer/ 

Why Phing? Because it's built with PHP.
https://github.com/phingofficial/phing





