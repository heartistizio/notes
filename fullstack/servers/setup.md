# Setup

## Server setup

### Update & upgrade software

```sh
apt update
apt upgrade
```

### Create a new user

```sh
adduser $USERNAME
```

### Make them a super user

```sh
usermod -aG sudo $USERNAME
```

### Switch user and verify

```sh
su $USERNAME
sudo less /var/log/auth.log
```

### Enable ssh login for the user

```sh
cd ~
mkdir -p ~/.ssh
vi ~/.ssh/authorized_keys // paste public key
```

### _Optionally_

Change authorized_keys permission have access only by high permission users

```sh
chmod 644 ~/.ssh/authorized_keys
```

### Disable root login

```sh
sudo vi /etc/ssh/sshd_config
```

### Restart sshd service

```sh
sudo service sshd restart
```
