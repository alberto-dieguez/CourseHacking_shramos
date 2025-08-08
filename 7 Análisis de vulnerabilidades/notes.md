# Análisis de vulnerabilidades

## CVE, CVSS, CPE Common Vulnerabilities and exposures

 - [CVE](https://www.cve.org/)
 - [CVSS](https://nvd.nist.gov/)
 - [CVE details](https://www.cvedetails.com/)

## Análisis de vulnerabilidades con Nmap

 - [Examples](https://nmap.org/book/nse-usage.html)

sudo namp -v -sS --script=vuln <IP>

sudo nmap -v -sS -oX vulverabilidades.xml --stylesheet="https://svn.nmap.org/nmap/docs/nmap.xsl" --script=vuln <IP>

## Nessus: Introducción e instalación

 - [Nessus essential](https://es-la.tenable.com/products/nessus/nessus-essentials)

sudo apt install ./Nessus*.deb

/bin/systemctl start nessusd.service

Go to the URL.

## Nessus: Análisis de vulnerabilidades

 - Host Discovery
 - Check plugins
 - Advanced Dynamic Scan