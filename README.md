# ansible-playbook-web-server

An ansible playbook to setup web servers on Debian 9:
- php 7.3 + composer
- nginx mainline
- mariadb 10.3
- redis 5.0.3
- certbot

## Configuration
Create the Vault password file, with your secret password:
```
➜ vim .vault_pass.txt

<your vault password>
```

Create an encrypted secret variables file:
```
➜ ansible-vault create vars/secret.yml

secret_mysql_root_password: <your mysql root password here>
#secret_mysql_foo_user_name: <your mysql user name for db foo here>
#secret_mysql_foo_user_password: <your mysql user password for db foo here>
secret_certbot_admin_email: <your email here>
```

Edit `inventory/hosts.yml` to setup your inventory, check variable in `vars/*.yml` to customize.

## Usage
Run the entire playbook:
```
➜ ansible-playbook playbook.yml
```

## License
MIT
