# Security Checklist

## [SSH](./practices.md#ssh-keys)

## Firewalls

Perimeter security technique that either allow or block requests in or out depending on their origin, port and protocol.

## Updates

Zero day is unpatched, undocumented vulnerability. Worth ton of money.

### unattented-upgrades

```sh
sudo apt install unattented-upgrades

less /etc/apt/apt.conf.d/50unattended-upgrades
```

## 2FA

Two layers of authentications. Usually phone.

## VPN

Virtual Private Network - a wall between Internet and Intranet.
