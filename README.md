Source code for my personal website, 2021 edition

[http://bigatti.it](http://bigatti.it)

# Terraforming

```(sh)
yum install -y httpd
cp etc.httpd.conf.d/deflate.conf /etc/httpd/conf.d
cp etc.httpd.conf.d/expires.conf /etc/httpd/conf.d
systemctl start httpd

bash <(curl -Ss https://my-netdata.io/kickstart.sh)
```