Nginx timer
=========

Configure the web-server nginx so that uptime is sent upon GET /service_data request. 
Requirements
------------

None.

Role Variables
--------------
Example respose for GET /service_data
{
	"title": "Seems working",
	"uptime": 0
}

`title_field` var is title, `time_field` is "uptime".

If you require your own configuration file, you can specify your own  via `nginx_conf_template`


Dependencies
------------

None.

Example Playbook
----------------
---
- hosts: virtual_machines
  tasks:
  - name: Include the role to setup nginx.
    ansible.builtin.include_role:
      name: nginx_timer
    vars:
      title_field: "Your title here"
    

License
-------

BSD


