# vultr搭建shadowsocks翻墙

## 安装shadowsocks

``` shell
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
```

## 开启tcp加速

* vim /etc/rc.local
* echo 3 > /proc/sys/net/ipv4/tcp_fastopen

* vim /etc/sysctl.conf
* net.ipv4.tcp_fastopen = 3


## 更换内核

### centos7更换内核

* 查看当前内核
``` shell
uname -r
```
* 更换内核
``` shell
rpm -ivh http://xz.wn789.com/CentOSkernel/kernel-3.10.0-229.1.2.el7.x86_64.rpm --force
```

* 查看是否更换成功
``` shell
rpm -qa | grep kernel
```


### centos6更换内核

* 查看当前内核
``` shell
uname -r
```

* 更换内核
``` shell
rpm -ivh http://xz.wn789.com/CentOSkernel/kernel-firmware-2.6.32-504.3.3.el6.noarch.rpm
rpm -ivh http://xz.wn789.com/CentOSkernel/kernel-2.6.32-504.3.3.el6.x86_64.rpm --force
```

* 查看是否更换成功
``` shell
rpm -qa | grep kernel
```

## 重启并查看内核

``` shell
reboot
uname -r
```

## 安装锐捷加速器

``` shell
wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/serverspeeder/master/serverspeeder-all.sh && bash serverspeeder-all.sh
```
