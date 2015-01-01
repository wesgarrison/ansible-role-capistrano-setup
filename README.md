Ansible Capistrano setup Role
=============================

An ansible role for creating the default project structure when using Capistrano as your application deployment tool.
This role will create a new system user / group for your deployment as well as set the default application structure for
Capistrano and put a placeholder page in an initial release.

For more information on Capistrano, [visit the Capistrano website](http://www.capistranorb.org)

Role Variables
--------------
Available variables are listed below, along with default values (see `defaults/main.yml`):

    capistrano_setup_users
    
list holding a dictionary that has all the information for your project creation. The dictionary holds the following fields:

    name: 
    
name of the project or some extra information you want to put in the users comment field

    username: 

project username

    password

password for the project user

    update_password
    
update the user password

    uid

user id of the user

    groups

list of groups the user belongs to

    home
    
path of the users home directory

    createhomedir
    
indicate if you want to create the home directory

    shell

user shell

    pub_key

public key to use when deploying through capistrano

    upload_key

indicate if you want to upload the public key

    project_directory
    
possible subdirectory inside the users home directory for your project structure

    placeholder
    
placeholder file so you can have a dummy deployment when your project is not deployed yet

    capistrano_setup_users_deleted

list holding a dictionary of projects you wish to remove. The dictionary has the following fields:

    name

name of the user you want to remove

    remove

indicate if you want to remove the users home directory


Example Playbook
-------------------------

    - hosts: servers
      roles:
         - { role: MichaelRigart.capistrano-setup }

License
-------

GPLv3

Author Information
------------------

Michaël Rigart <michael@netronix.be>
