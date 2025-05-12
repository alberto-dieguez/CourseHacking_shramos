El anonimato en Internet
Buenas a todos,

Me gustaría dedicar este artículo a hablar sobre el tema del anonimato en Internet y algunas de las técnicas que existen en la actualidad para tratar de garantizarlo. También me gustaría compartir con vosotros algunas reflexiones al respecto.

Antes de comenzar a hablar sobre anonimato en Internet, es importante que tengamos claros algunos conceptos básicos relativos a redes de ordenadores y riesgos de seguridad a los que estamos expuestos por el simple hecho de estar conectados a Internet.

La dirección ip y dirección Mac de los dispositivos que tenemos conectados a nuestra red doméstica/privada (incluidas las máquinas virtuales) no están directamente expuestas a Internet.

Para conectarnos a Internet necesitamos un dispositivo denominado router, que, de manera genérica, conecta nuestra red doméstica/privada con otras redes de las que se compone Internet. Todos los dispositivos que tenemos conectados a nuestra red doméstica/privada tienen una dirección ip privada que solo es accesible por otros dispositivos conectados a esta misma red. Por lo tanto, para poder conectarse a internet, tienen que hacerlo a través del router, que tiene una dirección ip pública concreta que utilizarán todos los sistemas informáticos que tengamos conectados a nuestra red privada.

Esto es algo sencillo de comprobar entrando en páginas que te muestran tu dirección ip pública desde diferentes dispositivos conectados a tu red doméstica (por ejemplo móvil y pc), y podrás observar que la dirección ip pública es la misma para ambos.

Dicho esto, ¿dónde entra el concepto de anonimato?

Utilizando algún método para garantizar el anonimato como puede ser una VPN, un proxy, red tor... de manera genérica lo que estamos haciendo es tunelizar nuestro tráfico de red aplicando algún tipo de cifrado desde una máquina en nuestra red doméstica/local hasta un servidor en Internet que se encargará de descifrar el tráfico y realizar la petición a donde nosotros queramos dirigirla. Es importante entender, que aunque el contenido del tráfico de red vaya cifrado, ese tráfico de red sigue pasando por nuestro router para poder llegar al servidor que lo descifra y, por lo tanto, nuestro router sigue estando expuesto a Internet.

El riesgo de seguridad al que estamos expuestos todos, independientemente de utilizar mecanismos para garantizar el anonimato o no, es a la explotación de un posible fallo de seguridad en nuestro router de manera que permita ganar acceso a los sistemas que se encuentren conectados a nuestra red local. Este riesgo no puede mitigarse por completo debido a que el router tiene que estar expuesto a Internet para poder habilitar la conexión de los dispositivos que se encuentran en nuestra red privada.

Por lo tanto, ¿qué es lo que tratamos de conseguir con las técnicas que intentar garantizar el anonimato en Internet?

Con este tipo de técnicas y herramientas tratamos de garantizar la privacidad y confidencialidad de nuestras conexiones. De esta manera, cuando nos conectamos a una máquina en Internet, por ejemplo un servidor de aplicación que proporciona una página web, lo hacemos a través de una o varias máquinas intermedias con las que establecemos una comunicación cifrada.

Aquí hay varias cosas que se deben tener en cuenta. Las máquinas que se utilizan para salir a internet cuando utilizas mecanismos de anonimato como una VPN, tienen que descifrar tu tráfico de red y, por lo tanto, pueden monitorizarlo y registrarlo. Conocen lo que estás haciendo y también el origen de la conexión. Si utilizas un servicio gratuito de proxy, VPN... que te encuentres por Internet, es posible que incluso te estén monitorizando y puedan llegar a robarte información. Si realizas cualquier tipo de actividad ilegal utilizando estos mecanismos, nada te garantiza que no vayas a ser identificado, sobre todo si estás utilizando un servicio gratuito.

Una vez dicho todo esto, me gustaría recalcar, que, en mi opinión, este tipo de herramientas son de mucha utilidad y en algunas ocasiones pueden ayudarnos a garantizar nuestra confidencialidad y privacidad para ciertas acciones, sin embargo, y tal y como reitero en varias ocasiones a lo largo del curso, no debería utilizarse ninguna técnica de hacking que sea ilegal sobre un sistema o una organización con la que no tienes un contrato establecido para la realización de un hacking ético. En caso contrario, utilices o no técnicas que garanticen el anonimato, te estás exponiendo a que ser identificado.

En las primeras secciones de este curso no se presentan herramientas para garantizar el anonimato porque las técnicas de recopilación pasiva de información no son ilegales y no necesitas ocultar tu dirección ip pública. Son técnicas que se basan en búsqueda de información en fuentes abiertas y no van dirigidas a ningún objetivo en particular. A partir de la sección 6, donde empezamos a ver técnicas de recopilación activa de información, en las que se dirigen a objetivos específicos, establecemos un laboratorio virtual donde realizamos todas las pruebas sobre servidores y máquinas en nuestro entorno controlado, nunca hacia Internet. No os recomiendo bajo ningún concepto que utilicéis técnicas activas de hacking sobre objetivos que se encuentren en Internet y para los que no disponéis de un contrato previo para realización de un Hacking Ético, ni siquiera utilizando herramientas para garantizar el anonimato.

Una vez presentada esta reflexión sobre las técnicas para garantizar el anonimato en Internet, me gustaría hablar sobre la importancia que tienen para ciertas tareas. Uno de los ejemplos más claros en los que pueden servir técnicas como una VPN es cuando estamos conectados a una red local no confiable, como puede ser la red wifi de una cafetería o de un aeropuerto. En estos casos no sabemos que dispositivos hay conectados a nuestra misma red local o si pueden estar monitorizando nuestra comunicación (como se presenta en la sección 10 del curso), por lo tanto, el uso de una VPN, que cifra el tráfico de red desde nuestro equipo a un servidor en Internet, nos garantiza que alguien interceptando nuestra comunicación no pueda ver nada.

Para terminar con el artículo, me gustaría indicaros algunas de las soluciones y herramientas más populares para garantizar el anonimato en Internet:

La opción más sencilla es utilizar un proxy. Si utilizas un proxy gratuito y público ten en cuenta que en esa máquina de destino por la que estas saliendo a Internet pueden estar monitorizando tu navegación.

Otro de los mecanismos más comunes es utilizar una VPN. Existen muchos servicios de VPN gratuitos, por mi experiencia personal, os recomiendo ProtonVPN. Este servicio tiene una versión gratuita que podéis utilizar de manera segura.

Aunque es menos popular, podéis conectaros a Internet a través de la Red Tor, esto garantiza que los nodos de salida a Internet pertenezcan a esta red y, por lo tanto, su dirección ip pública sea diferente a la tuya. En este caso también debes tener en cuenta que mucha gente utiliza este mecanismos y sus direcciones ip públicas están bloqueadas frecuentemente por los buscadores más populares como Google.

Podéis establecer vuestra propia máquina de salto en la nube. Puedes crear una cuenta gratuita de AWS (Amazon Web Services) y crear una máquina (instancia) en la nube que puedes utilizar de máquina de salto para conectarte a Internet y hacer las peticiones a través de ella, sería muy similar a tener tu proxy personal.

Estas son algunas de las alternativas que existen, si queréis profundizar más sobre este tema, os recomiendo el curso que tengo publicado en Udemy Curso de Ciberseguridad y Privacidad Online: VPN, Proxy, TOR, en el que se tratan en detalle todas estas tecnologías y muchas más.

Como reflexión final de este artículo me gustaría que entendieseis que este tipo de herramientas no siempre garantizan el anonimato en Internet y, en ciertas ocasiones, pueden llegar exponernos a nuevos riesgos de seguridad. Es importante que seáis conscientes de las limitaciones que tienen estas técnicas y las utilicéis de manera inteligente en las situaciones que realmente aportan un beneficio desde el punto de vista de la seguridad.

¡Muchas gracias a todos por haber seleccionado este curso y nos vemos en la siguiente sección!

Santiago.