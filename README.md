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
##### Penyelesaian Soal
- Topologi yang dibuat harus dapat mengakses internet keluar.
- Konfigurasi NAT dilakukan dengan menggunakan iptables, tetapi tidak menggunakan MASQUERADE.
- Untuk melakukan NAT tanpa MASQUERADE, digunakan perintah SNAT --to-source.
- IP yang digunakan untuk SNAT adalah NID dari router yang berhubungan dengan NAT.

##### Konfigurasi
Pada node Aura, tambahkan konfigurasi sebagai berikut
```
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP -s 192.214.0.0/20
```

#### Screenshoot Hasil
- Router


- Server


- Client



### Soal 2
##### Penyelesaian Soal
- Dilakukan konfigurasi firewall untuk drop semua TCP dan UDP kecuali port 8080 pada TCP.
- Konfigurasi dilakukan pada node Revolte.

##### Konfigurasi
Pada node Revolte, tambahkan konfigurasi sebagai berikut
```
 iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
 iptables -A INPUT -p tcp -j DROP
 iptables -A INPUT -p udp -j DROP

```
##### Penjelasan Konfigurasi
- Aturan pertama, ```iptables -A INPUT -p tcp --dport 8080 -j ACCEPT```, mengizinkan lalu lintas TCP yang menuju ke port 8080.
Aturan kedua, ```iptables -A INPUT -p tcp -j DROP```, menolak semua lalu lintas TCP kecuali yang menuju ke port 8080.
Aturan ketiga, ```iptables -A INPUT -p udp -j DROP```, menolak semua lalu lintas UDP.

#### Screenshoot Hasil
- [SUCCES] TurkRegion (Sender) > Revolte (Receiver) port 8080



- [GAGAL] TurkRegion (Sender) > Revolte (Receiver) port 8000

### Soal 3
##### Penyelesaian Soal
- Dilakukan konfigurasi firewall untuk membatasi jumlah koneksi ICMP ke DHCP dan DNS Server.
- Konfigurasi dilakukan pada chain INPUT.
- Jumlah koneksi ICMP yang diizinkan adalah maksimal 3.
- Koneksi yang melebihi batas akan ditolak.

##### Konfigurasi
Pada node Revolte, tambahkan konfigurasi sebagai berikut
```
iptables -I INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
iptables -I INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```
##### Penjelasan Konfigurasi
- Aturan pertama, ```iptables -I INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP```, membatasi jumlah koneksi ICMP dari satu alamat IP.
- Aturan kedua, ```iptables -I INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT```, mengizinkan paket yang terkait dengan koneksi yang sudah didirikan atau terkait dengan koneksi yang ada untuk masuk ke sistem.

#### Screenshoot Hasil
- Ping ke 4 Client (TurkRegion, LaubHills, GrobeForest, dan SchwerMountain)



### Soal 4
##### Penyelesaian Soal
- Dilakukan konfigurasi firewall untuk membatasi koneksi SSH pada Web Server.
- Konfigurasi dilakukan pada chain INPUT.
- Hanya lalu lintas SSH yang berasal dari alamat IP yang dimulai dengan 192.214.4.3 (IP GrobeForest) yang diizinkan.

##### Konfigurasi
Pada node Stark dan Sein, tambahkan konfigurasi sebagai berikut
```
iptables -A INPUT -p tcp --dport 22 -s 192.214.4.3/22 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
```

##### Penjelasan Konfigurasi
- Aturan pertama, ```iptables -A INPUT -p tcp --dport 22 -s 192.214.4.3/22 -j ACCEPT```, mengizinkan lalu lintas SSH yang berasal dari alamat IP yang dimulai dengan 192.214.4.3
- Aturan kedua, ```iptables -A INPUT -p tcp --dport 22 -j DROP```, menolak semua lalu lintas SSH yang tidak berasal dari alamat IP yang dimulai dengan 192.214.4.3

#### Screenshoot Hasil
- [SUCCES] GrobeForest (Sender) > Stark (Receiver)



- [GAGAL] TurkRegion (Sender) > Stark (Receiver)

### Soal 5
##### Penyelesaian Soal
- Dilakukan konfigurasi firewall untuk membatasi akses ke Web Server.
- Konfigurasi dilakukan pada chain INPUT.
- Akses ke Web Server hanya diperbolehkan pada hari Senin sampai Jumat, pukul 08:00-16:00.


##### Konfigurasi
Pada node Stark dan Sein, tambahkan konfigurasi sebagai berikut
```
iptables -A INPUT -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
iptables -A INPUT -j REJECT
```

##### Penjelasan Konfigurasi
- Aturan pertama, ```iptables -A INPUT -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT```, mengizinkan lalu lintas yang masuk (INPUT) hanya pada rentang waktu antara pukul 08:00 hingga 16:00 pada hari Senin sampai Jumat.
- Aturan kedua, ```iptables -A INPUT -j REJECT```, menolak semua lalu lintas yang tidak sesuai dengan aturan pertama. Ini termasuk lalu lintas di luar rentang waktu atau pada hari yang tidak termasuk dalam Senin sampai Jumat.

#### Screenshoot Hasil
Stark (Sender) > GrobeForest (Receiver)
- [SUCCES] ```date --set="2023-12-19 14:00:00"```



- [GAGAL] ```date --set="2023-12-19 17:00:00" ```


### Soal 6

> Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

**Script**

```
iptables -A INPUT -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j REJECT
iptables -A INPUT -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j REJECT
```

**Testing**

- Berhasil
  ![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/9aa6928f-4103-4b12-ab22-35f1c2a0a79b)

- Gagal (Rabu)
  ![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/cc8e81fd-c213-4943-959b-b536e39e929e)

- Gagal (Jumat)
  ![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/9e5aa13f-b700-44e4-a1ff-226a7a445661)

### Soal 7

### Soal 8

> Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024

**Script**

```
iptables -A INPUT -p tcp --dport 80 -s 192.214.0.12/30 -m time --datestart 2023-12-10 --datestop 2024-02-15 -j DROP
```

**Testing**

- Gagal
  ![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/9f814cd0-296f-4976-a631-2c089f9dda86)

- Berhasil
  ![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/8260419a-b4c3-4aef-956f-854f2df80e06)

### Soal 9

> Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. (clue: test dengan nmap)


**Script**

```
iptables -N portscan

iptables -A INPUT -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP

iptables -A INPUT -m recent --name portscan --set -j ACCEPT
iptables -A FORWARD -m recent --name portscan --set -j ACCEPT
```

**Testing**

![image](https://github.com/Stoam/Jarkom-Modul-5-E16-2023/assets/58579201/99d777f7-00de-4f51-b7b2-30b45348e4fa)

### Soal 10
