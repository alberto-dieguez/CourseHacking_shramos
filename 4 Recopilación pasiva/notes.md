# URLs

 - https://www.shodan.io/

 - https://search.censys.io/

 - https://archive.org/

# Linux Application

 - Whois

## The Harvester

 - https://github.com/laramies/theHarvester
  - Default in kali linux, explore with: `theharvester -h`
  - Examples:
    - theHarvester -d microsoft.com -b baidu -l 100 -f resultados
theHarvester → Es una herramienta de recopilación de información (OSINT) utilizada para obtener correos electrónicos, subdominios, nombres y más sobre un dominio específico.

-d microsoft.com → Indica el dominio objetivo sobre el que queremos recopilar información. En este caso, microsoft.com.

-b baidu → Especifica el motor de búsqueda que se usará para obtener la información. En este caso, baidu. Otros motores disponibles incluyen Google, Bing, Yahoo, DuckDuckGo, etc.

-l 100 → Define el número de resultados que se quieren obtener. En este caso, 100.

# Tools
## Miniconda
 - Miniconda:
 https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

  - Commands:
  
  ```
    bash Miniconda3-latest-Linux-x86_64.sh
    conda config --set auto_activate_base false
    conda create -n "old_harvester" python=3.8.0
    conda activate old_harvester
    mkdir old_harvester
    cd old_harvester
    wget https://github.com/laramies/theHarvester/archive/refs/tags/3.2.2.zip
    unzip 3.2.2.zip
    rm 3.2.2.zip
    cd theHarvester-3.2.2
    pip install -r requirements/base.txt
    python theHarvester.py -h
    python theHarvester.py -d microsoft.com -b baidu -l 100 -f resultados
    firefox resultados.html

  ```

    echo 'export PATH="$HOME/miniconda3/bin:$PATH"' >> ~/.zshrc
    source miniconda3/bin/activate

  Bloqueo temporal de dirección IP pública
Después de realizar algunas peticiones con TheHarvester es posible que os aparezca un error similar al siguiente:


Este error nos indica que Google ha bloqueado nuestra dirección IP pública. Lo que quiere decir que no nos deja realizar peticiones a su servicio desde ningún dispositivo que se encuentre dentro de nuestra red local.

Este comportamiento es muy frecuente y también debe tenerse en cuenta para las siguientes herramientas que se presentan en esta sección. Si realizas muchas peticiones automatizadas en poco tiempo a servicio como Google, Bing, Shodan... utilizando herramientas como theHarvester, estos servicios suelen bloquear temporalmente tu dirección IP pública para que no los satures.

Para resolver este problema tienes varias alternativas:

1. La más sencilla es esperar un tiempo hasta que el servicio correspondiente (ej. Google) desbloquee tu dirección IP pública. Esto suele tardar unos minutos o, como mucho, unas pocas horas. Probablemente si repites el mismo ejercicio dentro de unos minutos, comprobarás que ya te ha desbloqueado la IP

2. La segunda más sencilla es reiniciar tu router. En muchas ocasiones tu proveedor de Internet te asigna una dirección IP pública de manera dinámica, por lo tanto, apagando y encendiendo el router fuerzas a que se te asigne una dirección IP pública nueva que no estará bloqueada. Ten en cuenta que esto depende de tu proveedor de Internet y que no siempre funciona (puedes comprobar cuál es tu dirección IP pública aquí: https://www.whatsmyip.org/)

3. Puedes utilizar algún mecanismo de anonimización que te permita conectarte a internet a través de otra región y, por lo tanto, con otra dirección IP pública. El mecanismo más común es utilizar una VPN. Existen muchos servicios de VPN gratuitos, por mi experiencia personal, te recomiendo ProtonVPN. Este servicio tiene una versión gratuita que puedes utilizar. (Para más información sobre privacidad y anonimato te recomiendo mi curso de Udemy: Curso de Ciberseguridad y Privacidad Online: VPN, Proxy, TOR)

4. Por último, puedes cambiar la fuente en la que realizar la búsqueda y utilizar otras diferentes. Por ejemplo, si te bloquea Google, puedes realizar las peticiones a bing o duckduckgo, para ello utiliza la opción -b de theHarvester

Estas serían las opciones más sencillas para resolver el problema. También existirían otras alternativas interesantes un poco más complejas, como, por ejemplo, utilizar un proxy público para la salida a internet o conectarte mediante la red TOR.



¡Espero que este artículo os haya resultado interesante y nos vemos en la siguiente sección!

Santiago.

# Maltego

 Install: `sudp apt install maltego`
 Create free maltego account.

# Recon-ng

  Default in kali.
 - https://github.com/lanmaster53/recon-ng



