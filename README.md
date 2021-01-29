# centos8-docker-installation
Install Docker CE &amp; docker-compose on CentOS 8

### Docker CE
```bash
sudo su
dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
dnf list docker-ce
dnf install docker-ce --nobest -y
systemctl start docker
systemctl enable docker
systemctl is-active docker
systemctl is-enabled docker
```

### docker-compose
```bash
sudo su
curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o docker-compose
mv docker-compose /usr/local/bin && sudo chmod +x /usr/local/bin/docker-compose
/usr/local/bin/docker-compose
```


### Run Docker commands without sudo

```bash
groupadd docker
gpasswd -a <USER> docker
service docker restart

#logout or reboot
```
