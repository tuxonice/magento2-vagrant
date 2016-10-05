Vagrant Magento 2 Box
====================

## Installation

Virtualbox and Vagrant (min. Version 1.8) have to be installed on your local machine:

 - [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
 - [Vagrant](https://www.vagrantup.com/downloads)

### Vagrant installation for Debian / Ubuntu
 
    $ wget https://releases.hashicorp.com/vagrant/1.8.5/vagrant_1.8.5_x86_64.deb
    $ sudo dpkg -i vagrant_1.8.5_x86_64.deb
    
## Usage

Clone the repository to your local machine.

    $ git clone https://github.com/tuxonice/magento2-vagrant
    $ cd magento2-vagrant

Boot up your vagrant virtual machine:

    $ vagrant up

The first boot may take a while, so feel free to get a cup of coffee.

Your machine will be available at [http://192.168.33.10/](http://192.168.33.10/)
All required tools like the LAMP stack are already installed.

- Adminer (DB-Administration): [http://192.168.33.10/adminer.php](http://192.168.33.10/adminer.php)
- MySQL 5.6 user: `root`, password: `root`

To SSH into the created VM:

    $ vagrant ssh

If you use Putty the ssh configuration can be obtained via:

    $ vagrant ssh-config

To reprovision your machine:

    $ vagrant provision

### Troubleshooting

- Error message "The 'ansible_local' provisioner could not be found.":

Make sure vagrant is at least at version 1.8:

    $ vagrant -v

## Change PHP Version

The following PHP Versions are installed by default:

 - PHP 5.6
 - PHP 7.0
 - PHP 7.1 (RC)

Call one of the following commands to change the PHP Version:
 
    $ changephp_5.6
    $ changephp_7.0
    $ changephp_7.1

This will change the PHP Version used by the Apache webserver as well as the Version of the `php` command.

You can also call the PHP versions directly using their full path

    $ /usr/bin/php5.6 -V
    $ /usr/bin/php7.0 -v
    $ /usr/bin/php7.1 -v

## Installing Magento 2

SSH first into your VM:

    $ vagrant ssh

    //@todo: finish configuration scripts


## Notes for Arch Linux users

    $ sudo pacman -S virtualbox ansible net-tools nfs-utils
    $ sudo modprobe -a vboxdrv vboxnetadp vboxnetflt
    $ sudo systemctl start nfs-server

## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.

## Notes

This project is based from https://github.com/shopwareLabs/shopware-vagrant clone
