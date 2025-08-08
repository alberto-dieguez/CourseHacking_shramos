# Explotación y hacking de vulnerabilidades en Hosts

## Explotación manual

Descarga el payload asociado a la vulnerabilidad y ejecutalo.

## Metasploit

msfconsole
msfcli

 - Error en Nessus
   Preferences -> privacidad -> clear data

- Comandos
    search XXXX
    use XXXXX
    set payload XXXX
    show options
    show payloads
    exploit
    show target
    load nessus
    nessus_help
    db_import XXX
    help vulns

## Msfvenom

 - Commandos
     msfvenom -h
     msfvenom - p XXXX lhost=XXX lport=XXXX
     use exploit multi/handler
     msfvenom - p XXXX lhost=XXX lport=XXXX -f exe > prueba.exe

## Armitage

Es un IDE para metasploit

sudo apt-get install armitage
service postgresql start
armitage

