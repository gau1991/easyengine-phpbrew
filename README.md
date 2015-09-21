[EasyEngine] (https://github.com/rtCamp/easyengine)-[PHPBrew](https://github.com/phpbrew/phpbrew/)
==================

This is a simple Vagrant file to run multiple PHP Version with EasyEngine. Right now this setup is using custom vagrant box [ee-phpbrew](https://atlas.hashicorp.com/gau1991/boxes/ee-phpbrew), created for this project.

Note: If you are using other that Ubuntu/Debian system, then installation steps will differ, but setup steps are same.

## Vagrant box preinstalled 
1. EasyEngine with Nginx and MySQL
2. PHP 5.3, 5.4, 5.5 and 5.6

## Installation
1. First we will install Virtual Box and Vagrant on our system.

  ```bash
  sudo apt-get install virtualbox
  ```
1.  After that download the latest version of Vagrant from http://www.vagrantup.com/downloads
2.  Install vagrant

  ```bash
   sudo dpkg -i vagrant_*.deb
  ```
2.  You will also need to install [vagrant-hostsupdater](https://vagrantup.com/) plugin for Vagrant

  ```bash
    sudo vagrant plugin install vagrant-hostsupdater
  ```

## Let's setup Vagrant
1. You can use any distribution from [VagrantCloud](http://vagrantcloud.com/) that supports EasyEngine. By default EasyEngine-Vagrant uses ubuntu/trusty64. 
  To change the distribution open the Vagrantfile and replace ubutnu/trusty64 with box name

  ```bash
  git clone https://github.com/gau1991/easyengine-phpbrew.git

  cd easyengine-phpbrew
 ```
2. Edit `ee-hosts` file and enter domain names that should be pointed to this vagrant box

  ```
      $ cat ee-hosts
      example.com
  ```

3. Now start Vagrant

  ```bash
  vagrant up
  ```
4. It will setup EasyEngine on Vagrant Box. 

  ```
    ee site create example.com --wp
  ```

5. To check installation log, open another terminal and use

  ```bash
  tail -f easyengine-vagrant/logs/*
  ```
6. To switch PHP version use command
  
  ```
  sudo ee-switch <PHP-VERSION>
  ```
  
