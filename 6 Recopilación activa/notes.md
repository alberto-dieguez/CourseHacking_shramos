# Recopilación activa de la información

## metasploitable3

 - [metasploitable3](https://github.com/rapid7/metasploitable3)

 - Descargar la de windos y la de linux.
   - https://portal.cloud.hashicorp.com/vagrant/discover?query=metasploitable%20rapid7

Descargar y descomprir hasta tener las imágenes.

### Configuración

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