### Principales Protocolos de Internet y sus Puertos

* _Protocolo de internet_: El protocolo internetwork más común es el Protocolo de Internet (IP). IP es responsable de tomar los segmentos formateados del TCP, encapsularlos en paquetes, asignarles las direcciones correctas y seleccionar la mejor ruta hacia el host de destino.

* _Protocolos de acceso a la red_: Estos protocolos describen dos funciones principales: administración de enlace de datos y transmisión física de datos en los medios. Los protocolos de administración de enlace de datos toman los paquetes IP y los formatean para transmitirlos por los medios. Los estándares y protocolos de los medios físicos rigen de qué manera se envían las señales por los medios y cómo las interpretan los clientes que las reciben. Los transceptores de las tarjetas de interfaz de red implementan los estándares apropiados para los medios que se utilizan.

* _Protocolo de aplicación_: Protocolo de transferencia de hipertexto (HTTP) es un protocolo común que regula la forma en que interactúan un servidor Web y un cliente Web. HTTP define el contenido y el formato de las solicitudes y respuestas intercambiadas entre el cliente y el servidor. Tanto el cliente como el software del servidor Web implementan el HTTP como parte de la aplicación. El protocolo HTTP se basa en otros protocolos para regir de qué manera se transportan los mensajes entre el cliente y el servidor.

* _Protocolo de transporte_: Protocolo de control de transmisión (TCP) es el protocolo de transporte que administra las conversaciones individuales entre servidores Web y clientes Web. TCP divide los mensajes HTTP en pequeñas partes, denominadas segmentos, para enviarlas al cliente de destino. También es responsable de controlar el tamaño y los intervalos a los que se intercambian los mensajes entre el servidor y el cliente.

### UDP (User Datagram Protocol)

El grupo de protocolos de Internet también maneja un protocolo de transporte sin conexiones, el UDP (User Data Protocol, protocolo de datos de usuario). El UDP ofrece a las aplicaciones un mecanismo para enviar datagramas IP en bruto encapsulados sin tener que establecer una conexión.
Muchas aplicaciones cliente-servidor que tienen una solicitud y una respuesta usan el UDP en lugar de tomarse la molestia de establecer y luego liberar una conexión. El UDP se describe en el RFC 768. Un segmento UDP consiste en una cabecera de 8 bytes seguida de los datos. La cabecera se muestra a continuación. Los dos puertos sirven para lo mismo que en el TCP: para identificar los puntos terminales de las máquinas origen y destino. El campo delongitud UDP incluye la cabecera de 8 bytes y los datos. La suma de comprobación UDP incluye la misma pseudocabecera de formato, la cabecera UDP, y los datos, rellenados con una cantidad par de bytes de ser necesario.
Esta suma es opcional, y se almacena como 0 si no se calcula. Inutilizarla seria absurdo, a menos que la cantidad de los datos no importe, por ejemplo, voz digitalizada.

UDP no admite numeración de los datagramas, factor que, sumado a que tampoco utiliza señales de confirmación de entrega, hace que la garantía de que un paquete llegue a su destino sea mucho menor que si se usa TCP. Esto también origina que los datagramas pueden llegar duplicados y/o desordenados a su destino. Por estos motivos el control de envío de datagramas, si existe, debe ser implementado por las aplicaciones que usan UDP como medio de transporte de datos, al igual que el reeensamble de los mensajes entrantes.
Es por ello un protocolo del tipo best-effort (máximo esfuerzo), porque hace lo que puede para transmitir los datagramas hacia la aplicación, pero no puede garantizar que la aplicación los reciba.
Tampoco utiliza mecanismos de detección de errores. Cuando se detecta un error en un datagrama, en lugar de entregarlo a la aplicación destino, se descarta.
Cuando una aplicación envía datos a través de UDP, éstos llegan al otro extremo como una unidad. Por ejemplo, si una aplicación escribe 5 veces en el puerto UDP, la aplicación al otro extremo hará 5 lecturas del puerto UDP. Además, el tamaño de cada escritura será igual que el tamaño de las lecturas.

### DHCP (Dynamic Host Configuration Protocol)

DHCP significa Protocolo de configuración de host dinámico . Es un protocolo que permite que un equipo conectado a una red pueda obtener su configuración (principalmente, su configuración de red) en forma dinámica (es decir, sin intervención particular). Sólo tiene que especificarle al equipo, mediante DHCP, que encuentre una dirección IP de manera independiente. El objetivo principal es simplificar la administración de la red.
El protocolo DHCP sirve principalmente para distribuir direcciones IP en una red, pero desde sus inicios se diseñó como un complemento del protocolo BOOTP (Protocolo Bootstrap), que se utiliza, por ejemplo, cuando se instala un equipo a través de una red (BOOTP se usa junto con un servidor TFTP donde el cliente encontrará los archivos que se cargarán y copiarán en el disco duro). Un servidor DHCP puede devolver parámetros BOOTP o la configuración específica a un determinado host.

##### Funcionamiento del protocolo DHCP

Primero, se necesita un servidor DHCP que distribuya las direcciones IP. Este equipo será la base para todas las solicitudes DHCP por lo cual debe tener una dirección IP fija. Por lo tanto, en una red puede tener sólo un equipo con una dirección IP fija: el servidor DHCP.
El sistema básico de comunicación es BOOTP (con la trama UDP). Cuando un equipo se inicia no tiene información sobre su configuración de red y no hay nada especial que el usuario deba hacer para obtener una dirección IP. Para esto, la técnica que se usa es la transmisión: para encontrar y comunicarse con un servidor DHCP, el equipo simplemente enviará un paquete especial de transmisión (transmisión en 255.255.255.255 con información adicional como el tipo de solicitud, los puertos de conexión, etc.) a través de la red local. Cuando el DHCP recibe el paquete de transmisión, contestará con otro paquete de transmisión (no olvide que el cliente no tiene una dirección IP y, por lo tanto, no es posible conectar directamente con él) que contiene toda la información solicitada por el cliente.

### FTP (File Transfer Protocol)

El protocolo FTP (Protocolo de transferencia de archivos) es, como su nombre lo indica, un protocolo para transferir archivos.

##### La función del protocolo FTP

El protocolo FTP define la manera en que los datos deben ser transferidos a través de una red TCP/IP.
El objetivo del protocolo FTP es:
* Permitir que equipos remotos puedan compartir archivos.
* Permitir la independencia entre los sistemas de archivo del equipo del cliente y del equipo del servidor.
* Permitir una transferencia de datos eficaz.

##### El modelo FTP

El protocolo FTP está incluido dentro del modelo cliente-servidor, es decir, un equipo envía órdenes (el cliente) y el otro espera solicitudes para llevar a cabo acciones (el servidor).
Durante una conexión FTP, se encuentran abiertos dos canales de transmisión:
* Un canal de comandos (canal de control)
* Un canal de datos

### Telnet (Telnet Remote Protocol)

TELNET es un protocolo estándar siendo su número STD de 8. Su status es recomendado. Se describe en el RFC 854 - Especificaciones del protocolo TELNET y RFC 855 - "TELNET Option Specifications".
El protocolo TELNET proporciona una interfaz estandarizada, a través de la cual un programa de un host(el cliente de TELNET) puede acceder a los recursos de otro host (el servidor de TELNET) como si el cliente fuera una terminal local conectada al servidor.
Por ejemplo, un usuario de una estación de trabajo situada en una LAN se puede conectar al host. Por supuesto, TELNET se puede usar tanto en LANs como en WANs.

##### Funcionamiento de TELNET

TELNET es un protocolo basado en tres ideas:

* El concepto de NVT(Network Virtual Terminal) (NVT). Una NVT es un dispositivo imaginario que posee una estructura básica común a una amplia gama de terminales reales. Cada host mapea las características de su propia terminal sobre las de su correspondiente NVT, y asume todos los demás hosts harán lo mismo.
* Una perspectiva simétrica de las terminales y los procesos.
* Negociación de las opciones de la terminal. El protocolo TELNET usa el principio de opciones negociadas, ya que muchos host pueden desear suministrar servicios adicionales, más allá de los disponibles en la NVT. Se pueden negociar diversas opciones. El cliente y el servidor utilizan una serie de convenciones para establecer las características operacionales de su conexión TELNET a través de los mecanismos "DO, DON'T, WILL, WON'T"("hazlo, no lo hagas, lo harás, no lo harás")

### SSH (Secure Shell Remote Protocol)

SSH (Secure SHell, en español: intérprete de órdenes segura) es el nombre de un protocolo y del programa que lo implementa, y sirve paraacceder a máquinas remotas a través de una red. Permite manejar por completo la computadora mediante un intérprete de comandos, y también puede redirigir el tráfico de X para poder ejecutar programas gráficos si tenemos un Servidor X (en sistemas Unix y Windows) corriendo.
Además de la conexión a otros dispositivos, SSH nos permite copiar datos de forma segura (tanto archivos sueltos como simular sesiones FTPcifradas), gestionar claves RSA para no escribir claves al conectar a los dispositivos y pasar los datos de cualquier otra aplicación por un canal seguro tunelizado mediante SSH.

### POP3 (Post Office Protocol 3)

Post Office Protocol (POP3, Protocolo de Oficina de Correo o "Protocolo de Oficina Postal") Es un protocolo de red que se utiliza en clientes locales de correo electrónico para obtener los mensajes de correo electrónico almacenados en un servidor remoto. Es un protocolo de nivel de aplicación en el Modelo OSI.
Las versiones del protocolo POP, informalmente conocido como POP1 y POP2, se han hecho obsoletas debido a las últimas versiones de POP3. En general cuando se hace referencia al término POP, se refiere a POP3 dentro del contexto de protocolos de correo electrónico.

El POP3 se basa en la comunicación del protocolo TCP en el puerto 110. El mecanismo de utilización es el siguiente: cuando el POP3 necesita entrar al buzón, se conecta mediante el servidor de POP3, recupera la información que le interesa y después cierra la conexión y para entrar nuevamente al buzón, se establece una conexión nueva. Los comandos de POP3 constituyen cadenas de caracteres ASCII imprimibles acabados con <CRLF>. Cada comando incluye un código alfanumérico de cuatro caracteres que identifica el comando, seguido por uno cero o más parámetros.
Las respuestas de POP3 son con cadenas de caracteres ASCII, y se representan con un indicador de estado como positivo (+OK) o negativo (-ERR) y, también posiblemente con información adicional, 

### SMTP (Simple Mail Transfer Protocol)

Simple Mail Transfer Protocol (SMTP), o protocolo simple de transferencia de correo electrónico. Protocolo de red basado en texto utilizado para el intercambio de mensajes de correo electrónico entre computadoras o distintos dispositivos (PDA's, Celulares, etc).

### STP (Spanning Tree Protocol)

En una red LAN la redundancia se logra teniendo varios enlaces físicos entre los switches, de forma que queden varios caminos para llegar a un mismo destino. El resultado de esto es que la red LAN queda con ciclos o bucles.

### SOAP (Simple Object Access Protocol)

SOAP (siglas de Simple Object Access Protocol) es un protocolo estándar que define cómo dos objetos en diferentes procesos pueden comunicarse por medio de intercambio de datos XML. Este protocolo deriva de un protocolo creado por David Winer en 1998, llamado XML-RPC. SOAP fue creado por Microsoft, IBM y otros y está actualmente bajo el auspicio de la W3C. Es uno de los protocolos utilizados en los servicios Web.
SOAP puede formar la capa base de una "pila de protocolos de web service", ofreciendo un framework de mensajería básica en la cual los web services se puedan construir. Este protocolo basado en XML consiste de tres partes: un sobre (envelope), el cual define qué hay en el mensaje y cómo procesarlo; un conjunto de reglas de codificación para expresar instancias de tipos de datos; y una convención para representar llamadas a procedimientos y respuestas. El protocolo SOAP tiene tres características principales:

* Extensibilidad (seguridad y WS-routing son extensiones aplicadas en el desarrollo).
* Neutralidad (SOAP puede ser utilizado sobre cualquier protocolo de transporte como HTTP, SMTP, TCP o JMS).
* Independencia (SOAP permite cualquier modelo de programación).



![PUERTOS DE RED](https://nksistemas.com/wp-content/uploads/2012/06/puertos.png)

Como vemos en el gráfico, podemos dividir en 3 partes los puertos de red:

* _Conocidos_: del 0 al 1023
* _Registrados_: del 1024 al 49151, son utilizados por procesos de usuarios o programas varios.
* _Privados o dinámicos_: entre el 49152 y 65535, pueden ser utilizados por cualquier aplicación.

### Lista de puertos por protocolo:

**9 discard** -Basura (Dev|Null)

**11 sysstat** - Es un servicio Unix que realiza un listado de todos los procesos que se generan en la máquina. Esto le proporciona al usuario una gran cantidad de información con la que se consigue conocer las vulnerabilidades de los programas que están instalados en la máquina o las cuentas de usuario.

**13 daytime** - Es un servicio que proporciona la fecha y hora del sistema.

**15 netstat** - Muestra las conexiones de TCP activas, los puertos en que el equipo escucha, las estadísticas de Ethernet, la tabla de enrutamiento IP, las estadísticas de IPv4 (para los protocolos IP,ICMP, TCP y UDP) y las estadísticas de IPv6 (para los protocolos IPv6, ICMPv6, TCP sobre IPv6 y UDP sobre Ipv6). Cuando se utiliza sin parámetros, netstat muestra las conexiones de TCP activas. Este servicio da información sobre los archivos compartidos y usuarios que se encuentran en la red.

**19 generador de caracteres** - Este servicio genera caracteres. En una conexión TCP empieza a generar caracteres basura cuando recibe el paquete UDP hasta que la conexión ha finalizado. Los hackers pueden conseguir ventajas cuando el usuario tiene este puerto abierto, como entrar con IPs falsas para realizar ataques múltiples.

**21 FTP transferencia de ficheros** - El ataque más común es que realizan los hackers y crackers que buscan servidores FTP anónimos. Éstos suelen ser servidores que disponen de directorios con permiso de lectura y escritura. El puerto por defecto para intercambio de ficheros.

**22 ssh** - Control remoto de los PCs 

**23 telnet** - El intruso busca un login remoto. La mayoría del tiempo de escaneo de intrusos desde este puerto es simplemente para averiguar que Ssitema Operativo se está usando.

**25 smtp** - Los spammers buscan servidores SMTP que les permiten realizar envío masivo de correos electrónicos.

**37 time** - Este servicio te da la hora del sistema.

**38 rap Route Access Protocol** - Ruta de acceso al protocolo.

**39 rlp Resource Location Protocol** - Con este servicio se conoce la localización del recurso.

**42 name** - Con este servicio se consigue el nombre del servidor.

**43 nicname Who is** - Con este servicio se consigue la información sobre la red o usuario.

**49 tacasc Login Host Protocol** - Con este servicio se consigue el protocolo de Login del host.

**53 DNS** - Con este servicio se conoce el nombre de la máquina remota. Los usuarios intentan acceder a zonas de transferencia (TCP) para engañar DNS (UDP) o incluso para ocultar el trafico que desde el 53 no es recibido por los firewalls.

**63 who is ++** - Este servicio te dice el nombre de propietario de domino de segundo nivel.

**67/68 boot DHCP** - Los firewalls se conectan a las líneas DSL o cable móden para ver cientos de direcciones 255.255.255.255. Estos ordenadores preguntan por la asignación de una dirección de un servidor DHCP.

**69 TFTP** - Algunos servidores soporten este protocolo en conjunto con BOOTP con la intenciön de descargar código del sistema. Sin embargo, algunas veces se desconfigura algún archivo del sistema como los archivos que guardan las contraseñas. Por lo que también, pueden ser usadas para crear archivos dentro del sistema.

**70 gopher** - Buscador de información.

**79 finger** - Los usuarios lo usan para averiguar información del usuario, conseguir información impresa en pantalla o colgar el sistema.

**80 http** - Servidor Web con el que se accede a páginas Web. Con este puerto abierto el usuario se puede conectar con programas chat como el Messenger.

**88 kerberos** - Es un método seguro de autentificación de respuesta. Siempre que quieras acceder a otro ordenador necesitas una respuesta de autentificación del servidor (AS).

**107 rtelnet** - Telnet remoto, es decir, con un telnet accedes a otra ordenador a la que se supone que tienes permiso.

**109 pop2** - Servicio de correo electrónico. Post Office Protocol, versión 2.

**110 pop3** - Un punto de presencia (pop) es un punto de acceso de Internet. Un pop tiene únicamente un protocolo de Internet (IP). Este servicio proporciona el correo entrante.

**111 SUNrpc** - SUN remote Procedure Call.

**113 auth** - Servicio de autentificación.

**115 sftp** - Simple File Transfer Protocol.

**117 uucp-path** - UUCP Path Service.

**119 nntp** - Este servicio proporciona grupos de noticias usenet.

**133 statsrv** - Servicio de estadísticas.

**137 netbios-ns NETBIOS Name Service (Windows)** - NetBios es un programa que permite a las aplicaciones de diferentes ordenadores comunicarse sin una conexión de área local (LAN).

**138 netbios-dgm NETBIOS DatagramServices (Windows)**

**139 netbios-ssn NETBIOS Session (Windows)**

**143 imap** - Servicio de protocolo de mensajes de acceso de Internet (Internet Message Access Protocol)

**144 uma Universal Managment Architecture** - Servicio de noticas.

**161 snmp Simple Network Managment Protocol (SNMP)** - Es el puerto de gestión de dispositivos de red y sus funciones.

**194 irc Protocolo de chat** - Internet Relay Chat (IRC) es un sistema de comunicación instantanéa que está envuelto en una serie de reglas cliente - servidor.

**220 imap3** - Es un protocolo estándar cliente-servidor con el que accedes a tu correo desde el servidor local.

**443 shttp** - Servidor Web seguro.

**513 login** - Servicio que crea un login remoto a la Telnet.

**514 syslog Syslog** - Una lista de todas las peticiones que el usuario ha solicitado de un sitio Web.

**520 router** - Protocolo de información de routing.

**529 irc-serv IRC** - Chats.

**530 RPC Remote Procedure Call (RPC)** - Es un protocolo que un programa puede usar para solicitar un servicio de un programa que se encuentra en otro ordenador.

**1352 lotus notes** - Desde este servicio se accede al servidor de correo Lotus Notes.

**1397 audio-activmail** - Audio active mail.

**1433 ms-spl-s** - Microsoft SQL Server.

**1527 tlisrv** - Utilizado para acceder a Oracle.

**5631 pcanywheredata** - Solución de control remoto que permite a los administradores que se conecten de forma segura y soluciones problemas a través de cualquier tipo de conexión.


##### Puertos de juegos mas populares

**7777** - Unreal, Klingon Honor Guard.

**7778** - Unreal Tournament.

**22450** - Sin.

**26000** - Quake.

**26900** - Hexen 2.

**26950** - Hexenworld.

**27015** - Half-Life, Team Fortress Classic.

**27500** - QuakeWorld.

**27910** - Quake 2

**28000/08** - Starsiege Tribes.

**26900** - Hexen II.

**47624** - Operation Flash Point.

**1030** - Need for Speed 3.

**2346** - Rainbow six.

**16638/39** - Swat 3.

**2300** - Ages of Empires II.

**2350** - Ages of Empires conqueror.

**2611** - Black and white.

**28910/15** - Soldier of fortune.

**6112** - Startcraft658.

**2400** - Everquest, Age of Empires.

**26214** - Dark Reign 2.

**6112** - Diablo II.

**666** - Doom.

**23077** - Tzar.

**531** - Counter Strike.

**47624** - Battlecom.

**28910** - Herectic 2.

**3658** - Delta Force 2.

**6112** - Warcraft III.


##### Puerto usados por Troyanos

**21** - Blade Runner, Doly Trojan, Fore, Invisible FTP, WebEx, WinCrash.

**23** - Tiny Telnet Server.

**25** - Antigen, Email Password Sender, Haebu Coceda, Shtrilitz Stealth.

**80** - Executor.

**456** - Hackers Paradise.

**555** - ni-Kiler, Phase Zero, Stealth Spy.

**666** - Satans Backdoor.

**1001** - Silencer, WebEx.

**1011** - Doly Troyan.

**1170** - Psyber Stream Server, Voice.

**1234** - Ultors Trojan.

**1245** - VooDoo Doll.

**1492** - FTP99CMP.

**1600** - Shivka-Burka.

**1807** - SpySender.

**1981** - Shockrave.

**1999** - BackDoor.

**2001** - Trojan Cow.

**2023** - Ripper.

**2115** - Bugs.

**2140** - Deep Throat, The Invasor.

**2801** - Phineas Phucker.

**3024** - WinCrash.

**3129** - Masters Paradise.

**3150** - Deep Thorat, The Invasor.

**3700** - Portal of Doom.

**4092** - WinCrash.

**4590** - ICQTrojan.

**5321** - Firehotcker.

**5400** - Blade Runner.

**5569** - Robo-Hack.

**5742** - WinCrash.

**6670** - DeepThroat.

**6969** - GateCrasher, Priority.

**7000** - Remote Grab.

**7300** - NetMonitor.

**7301** - NetMonitor.

**7306** - NetMonitor.

**7307** - NetMonitor.

**7308** - NetMonitor.

**7789** - ICKiller.

**9872** -Portal of Doom.

**9873** - Portal of Doom.

**9874** - Portal of Doom.

**9875** - Portal of Doom.

**9989** - iNI-Killer.



## Bibliografía

[Listado de los Protocolos y Puertos de Comunicación](http://www.internetmania.net/int0/int133.htm)

[Apéndice C.Puertos comunes](http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-es-4/ch-ports.html)

[Principales protocolos de comunicación](http://harold-vilchis-isc.blogspot.com/2013/09/principales-protocolos-de-comunicacion.html)

[Lista de protocolos y sus puertos](http://networkips.blogspot.com/2013/03/lista-de-protocolos-y-sus-puertos.html)

[Curso de redes - Parte 4 - Puertos y Protocolos](https://nksistemas.com/curso-de-redes-parte-4-puertos-y-protocolos/)

