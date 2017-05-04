Ansible WordPress
===========
Ansible playbook for setup to WordPress.

## Spec
- CentOS 7
- Ansible 2.3 or newer
- Apache 2.4
- MariaDB 5.5
- PHP 7.1

## Prepared
Edit to the target host
```
[wordpress]
localhost ansible_connection=local
```

Create to credentials on MariaDB.
`vars/private.yml`
```yaml
mariadb_root_password: "your mysql root password"
mariadb_default_user_password: "your wordpress user password"
```

Edit to vhost on Apache.  
`roles/apache24/defaults/main.yml` or `vars/main.yml`
```yaml
apache_vhosts:
  - servername: "yourhostname"
    documentroot: "/var/www/html"
    logdir: "/var/log/httpd/yourehostname"
apache_vhosts_ssl: []
```

## Run
```bash
ansible-playbook setup.yml
```
