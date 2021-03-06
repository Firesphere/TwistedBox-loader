# Twisted Bytes Vagrant

This is a base installer for the [Twisted Bytes Vagrant box](https://www.twistedbytes.nl/en/blog/php-vagrant-box/) plus [SilverStripe](https://silverstripe.org).

It's a slightly customised version of the default installation.

It will install a base SilverStripe, or go with your existing git repository.

Assumed is a SilverStripe installation. It will set you up with a working system to continue developing.

# Author

[Simon `Firesphere` Erkelens](https://github.com/firesphere)

# Requirements

* Vagrant
* Virtualbox provider (e.g. VirtualBox, VMWare, etc.)
* Git
* PHP 5.6 or higher

# Installation

Download the `vagrantrunner.phar` file from the build directory to your root where you have your sites.

For example, if all your sites are located in `users/sites`, put the vagrantrunner.phar in that directory. Sites will be created in subdirectories of the .phar file's location.

Optionally, install the phar globally by copying it to `/usr/local/bin/vagrantrunner`, so you can kickstart a machine from anywhere.

# Usage

## To start a bare SilverStripe project

`php vagrantrunner.phar init projectname`

## To start a project from existing Git sources

`php vagrantrunner.phar init projectname git@github.com:yourProject.git`

## To destroy a box (to free up space)

```php vagrantrunner.phar destroy projectname```

This will _not_ destroy your project files, only the Vagrant machine.


After running the init, your box is ready to go. The admin username and password are: `admin:password`. Since it's a local isolated machine, this is not a security issue immediately, but you are free to change it.

# Versioning

As of version 1.0, all recent SilverStripe branches are pulled from the remote to give you the choice to install a specific branch.

Version 1.0 is the final release before implementation of box selection.

# Suggested Vagrant plugins

* [vagrant-cachier](http://fgrehm.viewdocs.io/vagrant-cachier/)

# Customisations

For testing purposes, we're not using the ini configuration that's in private. I suggest on live sites, you do.
Running Behat from your host machine, causes issues because it can't read the ini correctly.
Besides that, Behat requires root privileges. Therefore, the environment is hardcoded to root with empty password.

# Todo

* Clean up some code maybe
* Add smoketests
* Make a website for this project
* Make the box not just Twisted Bytes, but give a selection of boxes?
* Fix classmap
* Cleanup the messy strings. They need to be in a separate helper

# Suggestions

Yes, welcome.

# cow?

Ofcourse!

```

               /( ,,,,, )\
              _\,;;;;;;;,/_
           .-"; ;;;;;;;;; ;"-.
           '.__/`_ / \ _`\__.'
              | (')| |(') |
              | .--' '--. |
              |/ o     o \|
              |           |
             / \ _..=.._ / \
            /:. '._____.'   \
           ;::'    / \      .;
           |     _|_ _|_   ::|
         .-|     '==o=='    '|-.
        /  |  . /       \    |  \
        |  | ::|         |   | .|
        |  (  ')         (.  )::|
        |: |   |;  U U  ;|:: | `|
        |' |   | \ U U / |'  |  |
        ##V|   |_/`"""`\_|   |V##
           ##V##         ##V##
```