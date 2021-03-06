# Project 3 - Ultracatalogue on Linux 

## Overview
This deploys a basic database-driven website for cataloguing ultramarathons.  

## Server
The application is coded in Python and runs on Ubuntu on an AWS Lightsail server.

## Public IP and SSH Port
The application can be accessed at http://18.208.146.24 SSH port is 2200.

### Software Installed
The following software is installed

```
asn1crypto==0.24.0
certifi==2019.3.9
chardet==3.0.4
Click==7.0
cryptography==2.1.4
enum34==1.1.6
Flask==1.0.2
Flask-SQLAlchemy==2.3.2
httplib2==0.12.1
idna==2.8
ipaddress==1.0.17
itsdangerous==1.1.0
Jinja2==2.10
keyring==10.6.0
keyrings.alt==3.0
MarkupSafe==1.1.1
oauth2client==4.1.3
psycopg2==2.7.7
pyasn1==0.4.5
pyasn1-modules==0.2.4
pycrypto==2.6.1
pygobject==3.26.1
pyxdg==0.25
requests==2.21.0
rsa==4.0
SecretStorage==2.3.1
six==1.12.0
SQLAlchemy==1.3.1
urllib3==1.24.1
virtualenv==15.1.0
Werkzeug==0.15.0
```

## Configuration Changes

### Disable Root SSH Access
Root SSH access was disabled by changing the PermitRootLogin line  in /etc/ssh/sshd_config to:

```
PermitRootLogin no
```

### Enforce Key-based Authentication
Key-based authentication is enforced by changing the PasswordAuthentication line in /etc/ssh/sshd_config to:

```
PasswordAuthentication no
```

### Changed SSH Port to 2200
SSH port was changed to 2200 by changing the Port line in /etc/ssh/sshd_config to:

```
Port 2200
```

### Updated Firewall Settings
Firewalls were updated to only allow access on ports 2200, 80, and 123.

```
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw allow 2200
sudo ufw allow 80
sudo ufw allow 123
sudo ufw enable
```

## Third-Party Code 
The code for the application itself can be found in this repo: 

```
https://github.com/StephenGnoza/ultramarathoncatalogue
```

## Author
Stephen Gnoza
stephen.gnoza@gmail.com
