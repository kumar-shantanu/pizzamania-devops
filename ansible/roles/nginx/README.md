Nginx
=========

This role installs and configures the nginx web server. The user can specify any http configuration parameters they wish to apply their site. Any number of sites can be added with configurations of your choice.

Requirements
------------

This role requires Ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------
None

Example Playbook
----------------
1) Install nginx with HTTP directives of choices, but with no sites
configured and no additionnal configuration:

```yaml
- hosts: all
  roles:
  - {role: nginx,
     nginx_http_params: ["sendfile on", "access_log /var/log/nginx/access.log"]
                          }
```

2) Install nginx with different HTTP directives than previous example, but no
sites configured and no additionnal configuration.

```yaml
- hosts: all
  roles:
  - {role: nginx,
     nginx_http_params: ["tcp_nodelay on", "error_log /var/log/nginx/error.log"]}
```

Note: Please make sure the HTTP directives passed are valid, as this role
won't check for the validity of the directives. See the nginx documentation
for details.

3) Install nginx and add a site to the configuration.

```yaml
- hosts: all

  roles:
  - role: nginx
    nginx_http_params:
      - sendfile "on"
      - access_log "/var/log/nginx/access.log"
    nginx_sites:
      pizzamania:
        - listen 8080
        - location / { try_files $uri $uri/ /index.html; }
        - location /images/ { try_files $uri $uri/ /index.html; }
    nginx_configs:
      proxy:
        - proxy_set_header X-Real-IP  $remote_addr
        - proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for
```

License
-------

BSD

Author Information
------------------
Kumar Shantanu
