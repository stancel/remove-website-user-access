remove_website_user_access
=========

Ansible role that removes one or more Linux users and removes sftp access to a path where a website was stored on a shared hosting server.

Requirements
------------

While this can be used on any Linux server, it's original and primary purpose is to be used as a specialized role in a shared webserver Ansible playbook, removing chrooted user sftp access to a specific website.

Role Variables
--------------

Sites to setup and host on the webserver
```
	remove_website_user_access_list:
	  - {
		  name: 'mysite'
        }
```

(Default) The document root/absolute path that is the parent of the new user's home directory. The default is "/var/www"
```
	remove_website_user_access_web_root: "/var/www"
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

	- hosts: your_server
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.remove_website_user_access 

or just pass the variables in the playbook

	- hosts: your_server 
	  vars:
        setup_website_user_access_list:
          - {
              name: 'mysite'
            }
	  roles:
	    - stancel.remove_website_user_access


License
-------

GPLv3

Author Information
------------------

[Brad Stancel](https://github.com/stancel) 

