# puppet_vagrant_environment_repo

Puppet Repository to demonstrate using puppet environments with kitchen-puppet and Vagrant.
The tests are stored in the repository rather than separately in /test/integration (as is the chef format)

This demonstrates using test-kitchen, puppet and kitchen-verifier-serverspec to build and verify a server.


## Workstation Software Installation

The first thing you need to do is install the test-kitchen environment on your workstation.
A useful link is: http://misheska.com/blog/2013/12/26/set-up-a-sane-ruby-cookbook-authoring-environment-for-chef/

The follow instructions are for Windows PC (it will be similar for Mac):

1. Download and install virtualbox from https://www.virtualbox.org/wiki/Downloads.
2. Download and install Vagrant from https://www.vagrantup.com/downloads.html
3. Download and install the Windows RubyInstaller for 64 bit Ruby 2.4 from http://rubyinstaller.org/downloads.
   * Check the option to add ruby to your path.
4. install the development kit as part of the ruby install
5. Then install the following gems
  * gem install librarian-puppet
  * gem install puppet
  * gem install test-kitchen
  * gem install kitchen-puppet
  * gem install kitchen-vagrant
  * gem install kitchen-verifier-serverspec
6. git clone the repository https://github.com/neillturner/puppet_vagrant_environment_repo

## Check everything installed
In a command window in the puppet_vagrant_environment_repo directory run command
```
kitchen list
```
This will return a list if everyting is correctly installed.

## Create Servers in Virtual Box on your Workstation.
```
kitchen create base-nocm-centos-65 -l debug
```

## Build the server.
```
kitchen converge base-nocm-centos-65 -l debug
```

## Verify the server.
```
kitchen verify base-nocm-centos-65 -l debug
```

## Shutdown the server.
```
kitchen destroy base-nocm-centos-65 -l debug
```

##




