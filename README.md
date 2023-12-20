# Jarkom-Modul-5-E16-2023

## Anggota

| NRP        | Name               |
| ---        | ---                |
| 5025211058 | Nadya Zuhria Amana |
| 5025211127 | Nadif Mustafa      |

## Daftar Isi
- [Jarkom-Modul-5-E16-2023](#jarkom-modul-5-e16-2023)
  - [Anggota](#anggota)
  - [Daftar Isi](#daftar-isi)
  - [Persiapan](#persiapan)
    - [Topologi GNS3](#topologi-gns3)
    - [Pembagian Rute Subnet](#pembagian-rute-subnet)
    - [Tree VLSM](#tree-vlsm)
    - [Pembagian IP Subnet](#pembagian-ip-subnet)
    - [Network Configuration](#network-configuration)
    - [Routing](#routing)
  - [Konfigurasi](#konfigurasi)
    - [DNS Server](#dns-server)
    - [DHCP Server](#dhcp-server)
    - [DHCP Relay](#dhcp-relay)
    - [Web Server](#web-server)
    - [Client](#client)
  - [Penyelesaian Soal](#penyelesaian-soal)
    - [Soal 1](#soal-1)
    - [Soal 2](#soal-2)
    - [Soal 3](#soal-3)
    - [Soal 4](#soal-4)
    - [Soal 5](#soal-5)
    - [Soal 6](#soal-6)
    - [Soal 7](#soal-7)
    - [Soal 8](#soal-8)
    - [Soal 9](#soal-9)
    - [Soal 10](#soal-10)

## Persiapan

### Topologi GNS3

![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/bc5a3663-699d-45aa-95c0-4040d62cba28)

### Pembagian Rute Subnet

![Topologi_Subnet](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/340c4c82-32c7-40bc-8931-9a85520d48ef)

![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/9a9a892f-e00a-47bb-bba4-d7dcd9be15e4)

### Tree VLSM

![Modul 5_VLSM Tree](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/1b709816-5f97-41a0-85dd-62e27936cd97)

### Pembagian IP Subnet

![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/8d862792-91b5-4cd9-b9e6-df681cfeb8b4)

### Network Configuration

**Aura**

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

#A1
auto eth1
iface eth1 inet static
address 192.214.0.1
netmask 255.255.255.252

#A8
auto eth2
iface eth2 inet static
address 192.214.0.21
netmask 255.255.255.252
```

**Frieren**

```
auto lo
iface lo inet loopback

#A1
auto eth0
iface eth0 inet static
address 192.214.0.2
netmask 255.255.255.252
gateway 192.214.0.1

#A2
auto eth1
iface eth1 inet static
address 192.214.0.5
netmask 255.255.255.252

#A7
auto eth2
iface eth2 inet static
address 192.214.0.17
netmask 255.255.255.252
```

**Himmel**

```
auto lo
iface lo inet loopback

#A2
auto eth0
iface eth0 inet static
address 192.214.0.6
netmask 255.255.255.252
gateway 192.214.0.5

#A3
auto eth1
iface eth1 inet static
address 192.214.2.1
netmask 255.255.254.0

#A4
auto eth2
iface eth2 inet static
address 192.214.0.129
netmask 255.255.255.128
```

**Fern**

```
auto lo
iface lo inet loopback

#A4
auto eth0
iface eth0 inet static
address 192.214.0.130
netmask 255.255.255.128
gateway 192.214.0.129

#A5
auto eth1
iface eth1 inet static
address 192.214.0.9
netmask 255.255.255.252

#A6
auto eth2
iface eth2 inet static
address 192.214.0.13
netmask 255.255.255.252
```

**Heiter**

```
auto lo
iface lo inet loopback

#A8
auto eth0
iface eth0 inet static
address 192.214.0.22
netmask 255.255.255.252
gateway 192.214.0.21

#A9
auto eth1
iface eth1 inet static
address 192.214.8.1
netmask 255.255.248.0

#A10
auto eth2
iface eth2 inet static
address 192.214.4.1
netmask 255.255.252.0
```

**Revolte**

```
#A6
auto eth0
iface eth0 inet static
address 192.214.0.14
netmask 255.255.255.252
gateway 192.214.0.13
```

**Richter**

```
#A5
auto eth0
iface eth0 inet static
address 192.214.0.10
netmask 255.255.255.252
gateway 192.214.0.9
```

**Stark**

```
#A7
auto eth0
iface eth0 inet static
address 192.214.0.18
netmask 255.255.255.252
gateway 192.214.0.17
```

**Sein**

```
#A10
auto eth0
iface eth0 inet static
address 192.214.4.2
netmask 255.255.252.0
gateway 192.214.4.1
```

**Client (LaubHills, SchwerMountain, TurkRegion, GrobeForest)**

```
auto eth0
iface eth0 inet dhcp
```

### Routing

**Aura**

```
#Frieren
##A2
route add -net 192.214.0.4 netmask 255.255.255.252 gw 192.214.0.2
##A3
route add -net 192.214.2.0 netmask 255.255.254.0 gw 192.214.0.2
##A4
route add -net 192.214.0.128 netmask 255.255.255.128 gw 192.214.0.2
##A5
route add -net 192.214.0.8 netmask 255.255.255.252 gw 192.214.0.2
##A6
route add -net 192.214.0.12 netmask 255.255.255.252 gw 192.214.0.2
##A7
route add -net 192.214.0.16 netmask 255.255.255.252 gw 192.214.0.2

#Heiter
##A9
route add -net 192.214.8.0 netmask 255.255.248.0 gw 192.214.0.22
##A10
route add -net 192.214.4.0 netmask 255.255.252.0 gw 192.214.0.22
```

**Frieren**

```
#default
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.214.0.1

#Himmel
##A3
route add -net 192.214.2.0 netmask 255.255.254.0 gw 192.214.0.6
##A4
route add -net 192.214.0.128 netmask 255.255.255.128 gw 192.214.0.6
##A5
route add -net 192.214.0.8 netmask 255.255.255.252 gw 192.214.0.6
##A6
route add -net 192.214.0.12 netmask 255.255.255.252 gw 192.214.0.6
```

**Himmel**

```
#default
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.214.0.5

#Fern
##A5
route add -net 192.214.0.8 netmask 255.255.255.252 gw 192.214.0.130
##A6
route add -net 192.214.0.12 netmask 255.255.255.252 gw 192.214.0.130
```

**Fern**

```
#default
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.214.0.129
```

**Heiter**

```
#default
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.214.0.21
```

## Konfigurasi

### DNS Server

**init.sh**

```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install bind9 -y

cp /root/named.conf.options /etc/bind/named.conf.options

service bind9 start
service bind9 restart
```

**named.conf.options**

```
options {
    directory "/var/cache/bind";

    forwarders {
        192.168.122.1;
    };

    allow-query{any;};
    listen-on-v6 { any; };
};
```

### DHCP Server

**init.sh**

```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install isc-dhcp-server -y
apt-get install netcat -y

cp /root/isc-dhcp-server /etc/default/isc-dhcp-server
cp /root/dhcpd.conf /etc/dhcp/dhcpd.conf
rm /var/run/dhcpd.pid

service isc-dhcp-server start
service isc-dhcp-server restart
```

**isc-dhcp-server**

```
INTERFACESv4="eth0"
INTERFACESv6=""
```

**dhcpd.conf**

```
option domain-name "example.org";
option domain-name-servers ns1.example.org, ns2.example.org;

default-lease-time 600;
max-lease-time 7200;

ddns-update-style none;
authoritative;

subnet 192.214.0.8 netmask 255.255.255.252 {

}

subnet 192.214.0.12 netmask 255.255.255.252 {

}

#LaubHills
subnet 192.214.2.0 netmask 255.255.254.0 {
    range 192.214.2.2 192.214.3.254;
    option routers 192.214.2.1;
    option broadcast-address 192.214.3.255;
    option domain-name-servers 192.214.0.10;
    default-lease-time 600;
    max-lease-time 7200;
}

#SchwerMountain
subnet 192.214.0.128 netmask 255.255.255.128 {
    range 192.214.0.131 192.214.0.254;
    option routers 192.214.0.129;
    option broadcast-address 192.214.0.255;
    option domain-name-servers 192.214.0.10;
    default-lease-time 600;
    max-lease-time 7200;
}

#TurkRegion
subnet 192.214.8.0 netmask 255.255.248.0 {
    range 192.214.8.2 192.214.15.254;
    option routers 192.214.8.1;
    option broadcast-address 192.214.15.255;
    option domain-name-servers 192.214.0.10;
    default-lease-time 600;
    max-lease-time 7200;
}

#GrobeForest
subnet 192.214.4.0 netmask 255.255.252.0 {
    range 192.214.4.3 192.214.7.254;
    option routers 192.214.4.1;
    option broadcast-address 192.214.7.255;
    option domain-name-servers 192.214.0.10;
    default-lease-time 600;
    max-lease-time 7200;
}
```

### DHCP Relay

**init.sh**

```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install isc-dhcp-relay -y
apt-get install netcat -y

cp /root/isc-dhcp-relay /etc/default/isc-dhcp-relay
cp /root/sysctl.conf /etc/sysctl.conf

service isc-dhcp-relay start
service isc-dhcp-relay restart
```

**isc-dhcp-relay**

```
SERVERS="192.214.0.14"
INTERFACES="eth0 eth1 eth2"
OPTIONS=""
```

**sysctl.conf**

```
net.ipv4.ip_forward=1
```

### Web Server

Contoh di bawah ini adalah untuk node `Stark`. Lakukan hal yang sama pada `Sein`, tetapi dengan mengganti setiap kata `Stark` menjadi `Sein`.

**init.sh**

```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install apache2 -y
apt-get install netcat -y

cp /root/ports.conf /etc/apache2/ports.conf
cp /root/index.html /var/www/html/index.html

cp /root/stark.conf /etc/apache2/sites-available/stark.conf
a2ensite stark.conf
service apache2 restart
```

**ports.conf**

```
Listen 80
Listen 443

<IfModule ssl_module>
    Listen 443
</IfModule>

<IfModule mod_gnutls.c>
    Listen 443
</IfModule>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
```

**000-default.conf**

```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
```

**stark.conf**

```
<VirtualHost *:80>
    ServerName 192.214.0.18
    DocumentRoot /var/www/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

<VirtualHost *:443>
    ServerName 192.214.0.18
    DocumentRoot /var/www/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

**index.html**

```
Stark
```

### Client

**init.sh**

```
apt-get update
apt-get install lynx -y
apt-get install netcat -y
```

## Penyelesaian Soal

### Soal 1

### Soal 2

### Soal 3

### Soal 4

### Soal 5

### Soal 6

### Soal 7

### Soal 8

### Soal 9

### Soal 10
