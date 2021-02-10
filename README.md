# README

Source code for my personal website, 2021 edition

[https://bigatti.it](https://bigatti.it)

## Terraforming

### Install httpd
```(sh)
yum install -y httpd
cp etc.httpd.conf.d/deflate.conf /etc/httpd/conf.d
cp etc.httpd.conf.d/expires.conf /etc/httpd/conf.d
systemctl start httpd
```

### Install Netdata

```(sh)
bash <(curl -Ss https://my-netdata.io/kickstart.sh)
```

### Install Certbot

```(sh)
yum install -y snapd
systemctl enable --now snapd.socket
ln -s /var/lib/snapd/snap /snap

yum install mod_ssl

snap install core; sudo snap refresh core
snap install --classic certbot
ln -s /snap/bin/certbot /usr/bin/certbot
certbot --apache
certbot renew --dry-run
```