# Recopilación activa de la información

## metasploitable3

 - [metasploitable3](https://github.com/rapid7/metasploitable3)

 - Descargar la de windos y la de linux.
   - https://portal.cloud.hashicorp.com/vagrant/discover?query=metasploitable%20rapid7

Descargar y descomprir hasta tener las imágenes.

### Configuración
W
 - VM Ubuntu: 
 user vagrant y pass vagrant
 sudo loadkeys es
 sudo dhclient  // para asignar IP
 sudo iptables -S
 sudo iptables -F // para borrar

 - VM Windows:
 user administator pass vagrant
 ipconfig  // para ver la IP
 Control Panel -> Network and Internet -> Network and Sharing Center y poner todo a on.

Hacer ping para comprobar

## DNSrecon y transferencia de zona

Instalar: sudo apt-get install dnsutils

$ nslookup
> set type=ns
> zonetranfer.me

> set type=any
> server nsztm1.digi.ninja
> ls -d zonetransfer.me

 - dnsrecon:
 dnsrecon -d zonetransfer.me -t axfr

# Nmap

## Host Discovery

nmap -sn <IP/24> -> usa TCP

sudo nmap -sn <IP> -> usa ARP

sudo nmap -sn <IP/24> -> usa ARP

nmap -PS21,22,23 <IP/24> -p 80 -> análisis de puertos

## Escaneo de Puertos

sudo nmap -sS <IP> -p 80

sudo nmap -sS <IP/24> -p 80 -> silent scan

sudo nmap -v --reason -sS -oX puertos.xml --stylesheet="https://svn.nmap.org/nmap/docs/nmap.xsl" <IP> -p 80

sudo chmod 777 puertos.xml

firefox puertos.xml

sudo nmap -sT <IP/24> -p 80 -> TCP scan

sudo nmap -sS <IP/24> -p 53 -> UDP PORT

sudo nmap -sU <IP/24> -p 53 -> UDP PORT

## Escaneo de Servicios

sudo nmap -sV <IP> -p 21

# Amap

sudo apt-get install amap

sudo nmap -v --reason -sS -oA servicios.amap --stylesheet="https://svn.nmap.org/nmap/docs/nmap.xsl" <IP> -p 80

amap -i servicios.amap.gnmap -B

## Escaneo de SO

sudo nmap -v -O <IP>

## Nmap SMB enumeration

sudo nmap -v -sS -p 139,445 <IP>

ls /usr/share/nmap/scripts -> mustrea scripts que podemos usar

sudo nmap -v -sS -p 139,445 --script=smb-os-discovery <IP> 

## Nmap SNMP enumeration

sudo nmap -v -sS -p 161 <IP> -> port closed in TCP

sudo nmap -v -sU -p 161 <IP> -> port open in UDP

sudo nmap -v -sU -p 161 --script=snmp-win32-software <IP>

sudo nmap -v -sU -p 161 --script=snmp-win32-processes <IP> 

