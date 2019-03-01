# it490-RabbitMQ

### RabbitMQ User
```
rabbitmqctl add_user auth_client secure_pass
```

* `auth_client` is the username for the user

* `secure_pass` is the password for the user

### RabbitMQ Create Virtual Host
```
rabbitmqctl add_vhost user_auth
```

* `user_auth` is the name of the vhost

### RabbitMQ Set Permissions
```
rabbitmqctl set_permissions -p user_auth auth_client “.*” “.*” “.*”
```

* `user_auth` is passed with the `-p` argument and is the vhost

* `auth_client` is the user to change permissions on

The arguments after the username specify that the user should have
all permissions, in the given vhost, for **configuration**, **writing**, and **reading**
respectively. This is done using a regular expression for each permission
matching resource names within the vhost.
