### Principales Protocolos de Internet y sus Puertos

* _Protocolo de internet_: El protocolo internetwork m�s com�n es el Protocolo de Internet (IP). IP es responsable de tomar los segmentos formateados del TCP, encapsularlos en paquetes, asignarles las direcciones correctas y seleccionar la mejor ruta hacia el host de destino.

* _Protocolos de acceso a la red_: Estos protocolos describen dos funciones principales: administraci�n de enlace de datos y transmisi�n f�sica de datos en los medios. Los protocolos de administraci�n de enlace de datos toman los paquetes IP y los formatean para transmitirlos por los medios. Los est�ndares y protocolos de los medios f�sicos rigen de qu� manera se env�an las se�ales por los medios y c�mo las interpretan los clientes que las reciben. Los transceptores de las tarjetas de interfaz de red implementan los est�ndares apropiados para los medios que se utilizan.

* _Protocolo de aplicaci�n_: Protocolo de transferencia de hipertexto (HTTP) es un protocolo com�n que regula la forma en que interact�an un servidor Web y un cliente Web. HTTP define el contenido y el formato de las solicitudes y respuestas intercambiadas entre el cliente y el servidor. Tanto el cliente como el software del servidor Web implementan el HTTP como parte de la aplicaci�n. El protocolo HTTP se basa en otros protocolos para regir de qu� manera se transportan los mensajes entre el cliente y el servidor.

* _Protocolo de transporte_: Protocolo de control de transmisi�n (TCP) es el protocolo de transporte que administra las conversaciones individuales entre servidores Web y clientes Web. TCP divide los mensajes HTTP en peque�as partes, denominadas segmentos, para enviarlas al cliente de destino. Tambi�n es responsable de controlar el tama�o y los intervalos a los que se intercambian los mensajes entre el servidor y el cliente.

### UDP (User Datagram Protocol)

El grupo de protocolos de Internet tambi�n maneja un protocolo de transporte sin conexiones, el UDP (User Data Protocol, protocolo de datos de usuario). El UDP ofrece a las aplicaciones un mecanismo para enviar datagramas IP en bruto encapsulados sin tener que establecer una conexi�n.
Muchas aplicaciones cliente-servidor que tienen una solicitud y una respuesta usan el UDP en lugar de tomarse la molestia de establecer y luego liberar una conexi�n. El UDP se describe en el RFC 768. Un segmento UDP consiste en una cabecera de 8 bytes seguida de los datos. La cabecera se muestra a continuaci�n. Los dos puertos sirven para lo mismo que en el TCP: para identificar los puntos terminales de las m�quinas origen y destino. El campo delongitud UDP incluye la cabecera de 8 bytes y los datos. La suma de comprobaci�n UDP incluye la misma pseudocabecera de formato, la cabecera UDP, y los datos, rellenados con una cantidad par de bytes de ser necesario.
Esta suma es opcional, y se almacena como 0 si no se calcula. Inutilizarla seria absurdo, a menos que la cantidad de los datos no importe, por ejemplo, voz digitalizada.

UDP no admite numeraci�n de los datagramas, factor que, sumado a que tampoco utiliza se�ales de confirmaci�n de entrega, hace que la garant�a de que un paquete llegue a su destino sea mucho menor que si se usa TCP. Esto tambi�n origina que los datagramas pueden llegar duplicados y/o desordenados a su destino. Por estos motivos el control de env�o de datagramas, si existe, debe ser implementado por las aplicaciones que usan UDP como medio de transporte de datos, al igual que el reeensamble de los mensajes entrantes.
Es por ello un protocolo del tipo best-effort (m�ximo esfuerzo), porque hace lo que puede para transmitir los datagramas hacia la aplicaci�n, pero no puede garantizar que la aplicaci�n los reciba.
Tampoco utiliza mecanismos de detecci�n de errores. Cuando se detecta un error en un datagrama, en lugar de entregarlo a la aplicaci�n destino, se descarta.
Cuando una aplicaci�n env�a datos a trav�s de UDP, �stos llegan al otro extremo como una unidad. Por ejemplo, si una aplicaci�n escribe 5 veces en el puerto UDP, la aplicaci�n al otro extremo har� 5 lecturas del puerto UDP. Adem�s, el tama�o de cada escritura ser� igual que el tama�o de las lecturas.

### DHCP (Dynamic Host Configuration Protocol)

DHCP significa Protocolo de configuraci�n de host din�mico . Es un protocolo que permite que un equipo conectado a una red pueda obtener su configuraci�n (principalmente, su configuraci�n de red) en forma din�mica (es decir, sin intervenci�n particular). S�lo tiene que especificarle al equipo, mediante DHCP, que encuentre una direcci�n IP de manera independiente. El objetivo principal es simplificar la administraci�n de la red.
El protocolo DHCP sirve principalmente para distribuir direcciones IP en una red, pero desde sus inicios se dise�� como un complemento del protocolo BOOTP (Protocolo Bootstrap), que se utiliza, por ejemplo, cuando se instala un equipo a trav�s de una red (BOOTP se usa junto con un servidor TFTP donde el cliente encontrar� los archivos que se cargar�n y copiar�n en el disco duro). Un servidor DHCP puede devolver par�metros BOOTP o la configuraci�n espec�fica a un determinado host.

##### Funcionamiento del protocolo DHCP

Primero, se necesita un servidor DHCP que distribuya las direcciones IP. Este equipo ser� la base para todas las solicitudes DHCP por lo cual debe tener una direcci�n IP fija. Por lo tanto, en una red puede tener s�lo un equipo con una direcci�n IP fija: el servidor DHCP.
El sistema b�sico de comunicaci�n es BOOTP (con la trama UDP). Cuando un equipo se inicia no tiene informaci�n sobre su configuraci�n de red y no hay nada especial que el usuario deba hacer para obtener una direcci�n IP. Para esto, la t�cnica que se usa es la transmisi�n: para encontrar y comunicarse con un servidor DHCP, el equipo simplemente enviar� un paquete especial de transmisi�n (transmisi�n en 255.255.255.255 con informaci�n adicional como el tipo de solicitud, los puertos de conexi�n, etc.) a trav�s de la red local. Cuando el DHCP recibe el paquete de transmisi�n, contestar� con otro paquete de transmisi�n (no olvide que el cliente no tiene una direcci�n IP y, por lo tanto, no es posible conectar directamente con �l) que contiene toda la informaci�n solicitada por el cliente.

### FTP (File Transfer Protocol)

El protocolo FTP (Protocolo de transferencia de archivos) es, como su nombre lo indica, un protocolo para transferir archivos.

##### La funci�n del protocolo FTP

El protocolo FTP define la manera en que los datos deben ser transferidos a trav�s de una red TCP/IP.
El objetivo del protocolo FTP es:
* Permitir que equipos remotos puedan compartir archivos.
* Permitir la independencia entre los sistemas de archivo del equipo del cliente y del equipo del servidor.
* Permitir una transferencia de datos eficaz.

##### El modelo FTP

El protocolo FTP est� incluido dentro del modelo cliente-servidor, es decir, un equipo env�a �rdenes (el cliente) y el otro espera solicitudes para llevar a cabo acciones (el servidor).
Durante una conexi�n FTP, se encuentran abiertos dos canales de transmisi�n:
* Un canal de comandos (canal de control)
* Un canal de datos

### Telnet (Telnet Remote Protocol)

TELNET es un protocolo est�ndar siendo su n�mero STD de 8. Su status es recomendado. Se describe en el RFC 854 - Especificaciones del protocolo TELNET y RFC 855 - "TELNET Option Specifications".
El protocolo TELNET proporciona una interfaz estandarizada, a trav�s de la cual un programa de un host(el cliente de TELNET) puede acceder a los recursos de otro host (el servidor de TELNET) como si el cliente fuera una terminal local conectada al servidor.
Por ejemplo, un usuario de una estaci�n de trabajo situada en una LAN se puede conectar al host. Por supuesto, TELNET se puede usar tanto en LANs como en WANs.

##### Funcionamiento de TELNET

TELNET es un protocolo basado en tres ideas:

* El concepto de NVT(Network Virtual Terminal) (NVT). Una NVT es un dispositivo imaginario que posee una estructura b�sica com�n a una amplia gama de terminales reales. Cada host mapea las caracter�sticas de su propia terminal sobre las de su correspondiente NVT, y asume todos los dem�s hosts har�n lo mismo.
* Una perspectiva sim�trica de las terminales y los procesos.
* Negociaci�n de las opciones de la terminal. El protocolo TELNET usa el principio de opciones negociadas, ya que muchos host pueden desear suministrar servicios adicionales, m�s all� de los disponibles en la NVT. Se pueden negociar diversas opciones. El cliente y el servidor utilizan una serie de convenciones para establecer las caracter�sticas operacionales de su conexi�n TELNET a trav�s de los mecanismos "DO, DON'T, WILL, WON'T"("hazlo, no lo hagas, lo har�s, no lo har�s")

### SSH (Secure Shell Remote Protocol)

SSH (Secure SHell, en espa�ol: int�rprete de �rdenes segura) es el nombre de un protocolo y del programa que lo implementa, y sirve paraacceder a m�quinas remotas a trav�s de una red. Permite manejar por completo la computadora mediante un int�rprete de comandos, y tambi�n puede redirigir el tr�fico de X para poder ejecutar programas gr�ficos si tenemos un Servidor X (en sistemas Unix y Windows) corriendo.
Adem�s de la conexi�n a otros dispositivos, SSH nos permite copiar datos de forma segura (tanto archivos sueltos como simular sesiones FTPcifradas), gestionar claves RSA para no escribir claves al conectar a los dispositivos y pasar los datos de cualquier otra aplicaci�n por un canal seguro tunelizado mediante SSH.

### POP3 (Post Office Protocol 3)

Post Office Protocol (POP3, Protocolo de Oficina de Correo o "Protocolo de Oficina Postal") Es un protocolo de red que se utiliza en clientes locales de correo electr�nico para obtener los mensajes de correo electr�nico almacenados en un servidor remoto. Es un protocolo de nivel de aplicaci�n en el Modelo OSI.
Las versiones del protocolo POP, informalmente conocido como POP1 y POP2, se han hecho obsoletas debido a las �ltimas versiones de POP3. En general cuando se hace referencia al t�rmino POP, se refiere a POP3 dentro del contexto de protocolos de correo electr�nico.

El POP3 se basa en la comunicaci�n del protocolo TCP en el puerto 110. El mecanismo de utilizaci�n es el siguiente: cuando el POP3 necesita entrar al buz�n, se conecta mediante el servidor de POP3, recupera la informaci�n que le interesa y despu�s cierra la conexi�n y para entrar nuevamente al buz�n, se establece una conexi�n nueva. Los comandos de POP3 constituyen cadenas de caracteres ASCII imprimibles acabados con <CRLF>. Cada comando incluye un c�digo alfanum�rico de cuatro caracteres que identifica el comando, seguido por uno cero o m�s par�metros.
Las respuestas de POP3 son con cadenas de caracteres ASCII, y se representan con un indicador de estado como positivo (+OK) o negativo (-ERR) y, tambi�n posiblemente con informaci�n adicional, 

### SMTP (Simple Mail Transfer Protocol)

Simple Mail Transfer Protocol (SMTP), o protocolo simple de transferencia de correo electr�nico. Protocolo de red basado en texto utilizado para el intercambio de mensajes de correo electr�nico entre computadoras o distintos dispositivos (PDA's, Celulares, etc).

### STP (Spanning Tree Protocol)

En una red LAN la redundancia se logra teniendo varios enlaces f�sicos entre los switches, de forma que queden varios caminos para llegar a un mismo destino. El resultado de esto es que la red LAN queda con ciclos o bucles.

### SOAP (Simple Object Access Protocol)

SOAP (siglas de Simple Object Access Protocol) es un protocolo est�ndar que define c�mo dos objetos en diferentes procesos pueden comunicarse por medio de intercambio de datos XML. Este protocolo deriva de un protocolo creado por David Winer en 1998, llamado XML-RPC. SOAP fue creado por Microsoft, IBM y otros y est� actualmente bajo el auspicio de la W3C. Es uno de los protocolos utilizados en los servicios Web.
SOAP puede formar la capa base de una "pila de protocolos de web service", ofreciendo un framework de mensajer�a b�sica en la cual los web services se puedan construir. Este protocolo basado en XML consiste de tres partes: un sobre (envelope), el cual define qu� hay en el mensaje y c�mo procesarlo; un conjunto de reglas de codificaci�n para expresar instancias de tipos de datos; y una convenci�n para representar llamadas a procedimientos y respuestas. El protocolo SOAP tiene tres caracter�sticas principales:

* Extensibilidad (seguridad y WS-routing son extensiones aplicadas en el desarrollo).
* Neutralidad (SOAP puede ser utilizado sobre cualquier protocolo de transporte como HTTP, SMTP, TCP o JMS).
* Independencia (SOAP permite cualquier modelo de programaci�n).



![PUERTOS DE RED](https://nksistemas.com/wp-content/uploads/2012/06/puertos.png)

Como vemos en el gr�fico, podemos dividir en 3 partes los puertos de red:

* _Conocidos_: del 0 al 1023
* _Registrados_: del 1024 al 49151, son utilizados por procesos de usuarios o programas varios.
* _Privados o din�micos_: entre el 49152 y 65535, pueden ser utilizados por cualquier aplicaci�n.

### Lista de puertos por protocolo:

**9 discard** -Basura (Dev|Null)
**11 sysstat** - Es un servicio Unix que realiza un listado de todos los procesos que se generan en la m�quina. Esto le proporciona al usuario una gran cantidad de informaci�n con la que se consigue conocer las vulnerabilidades de los programas que est�n instalados en la m�quina o las cuentas de usuario.
**13 daytime** - Es un servicio que proporciona la fecha y hora del sistema.
**15 netstat** - Muestra las conexiones de TCP activas, los puertos en que el equipo escucha, las estad�sticas de Ethernet, la tabla de enrutamiento IP, las estad�sticas de IPv4 (para los protocolos IP,ICMP, TCP y UDP) y las estad�sticas de IPv6 (para los protocolos IPv6, ICMPv6, TCP sobre IPv6 y UDP sobre Ipv6). Cuando se utiliza sin par�metros, netstat muestra las conexiones de TCP activas. Este servicio da informaci�n sobre los archivos compartidos y usuarios que se encuentran en la red.
**19 generador de caracteres** - Este servicio genera caracteres. En una conexi�n TCP empieza a generar caracteres basura cuando recibe el paquete UDP hasta que la conexi�n ha finalizado. Los hackers pueden conseguir ventajas cuando el usuario tiene este puerto abierto, como entrar con IPs falsas para realizar ataques m�ltiples.
**21 FTP transferencia de ficheros** - El ataque m�s com�n es que realizan los hackers y crackers que buscan servidores FTP an�nimos. �stos suelen ser servidores que disponen de directorios con permiso de lectura y escritura. El puerto por defecto para intercambio de ficheros.
**22 ssh** - Control remoto de los PCs 
**23 telnet** - El intruso busca un login remoto. La mayor�a del tiempo de escaneo de intrusos desde este puerto es simplemente para averiguar que Ssitema Operativo se est� usando.
**25 smtp** - Los spammers buscan servidores SMTP que les permiten realizar env�o masivo de correos electr�nicos.
**37 time** - Este servicio te da la hora del sistema.
**38 rap Route Access Protocol** - Ruta de acceso al protocolo.
**39 rlp Resource Location Protocol** - Con este servicio se conoce la localizaci�n del recurso.
**42 name** - Con este servicio se consigue el nombre del servidor.
**43 nicname Who is** - Con este servicio se consigue la informaci�n sobre la red o usuario.
**49 tacasc Login Host Protocol** - Con este servicio se consigue el protocolo de Login del host.
**53 DNS** - Con este servicio se conoce el nombre de la m�quina remota. Los usuarios intentan acceder a zonas de transferencia (TCP) para enga�ar DNS (UDP) o incluso para ocultar el trafico que desde el 53 no es recibido por los firewalls.
**63 who is ++** - Este servicio te dice el nombre de propietario de domino de segundo nivel.
**67/68 boot DHCP** - Los firewalls se conectan a las l�neas DSL o cable m�den para ver cientos de direcciones 255.255.255.255. Estos ordenadores preguntan por la asignaci�n de una direcci�n de un servidor DHCP.
**69 TFTP** - Algunos servidores soporten este protocolo en conjunto con BOOTP con la intenci�n de descargar c�digo del sistema. Sin embargo, algunas veces se desconfigura alg�n archivo del sistema como los archivos que guardan las contrase�as. Por lo que tambi�n, pueden ser usadas para crear archivos dentro del sistema.
**70 gopher** - Buscador de informaci�n.
**79 finger** - Los usuarios lo usan para averiguar informaci�n del usuario, conseguir informaci�n impresa en pantalla o colgar el sistema.
**80 http** - Servidor Web con el que se accede a p�ginas Web. Con este puerto abierto el usuario se puede conectar con programas chat como el Messenger.
**88 kerberos** - Es un m�todo seguro de autentificaci�n de respuesta. Siempre que quieras acceder a otro ordenador necesitas una respuesta de autentificaci�n del servidor (AS).
**107 rtelnet** - Telnet remoto, es decir, con un telnet accedes a otra ordenador a la que se supone que tienes permiso.
**109 pop2** - Servicio de correo electr�nico. Post Office Protocol, versi�n 2.
**110 pop3** - Un punto de presencia (pop) es un punto de acceso de Internet. Un pop tiene �nicamente un protocolo de Internet (IP). Este servicio proporciona el correo entrante.
**111 SUNrpc** - SUN remote Procedure Call.
**113 auth** - Servicio de autentificaci�n.
**115 sftp** - Simple File Transfer Protocol.
**117 uucp-path** - UUCP Path Service.
**119 nntp** - Este servicio proporciona grupos de noticias usenet.
**133 statsrv** - Servicio de estad�sticas.
**137 netbios-ns NETBIOS Name Service (Windows)** - NetBios es un programa que permite a las aplicaciones de diferentes ordenadores comunicarse sin una conexi�n de �rea local (LAN).
**138 netbios-dgm NETBIOS DatagramServices (Windows)**
**139 netbios-ssn NETBIOS Session (Windows)**
**143 imap** - Servicio de protocolo de mensajes de acceso de Internet (Internet Message Access Protocol)
**144 uma Universal Managment Architecture** - Servicio de noticas.
**161 snmp Simple Network Managment Protocol (SNMP)** - Es el puerto de gesti�n de dispositivos de red y sus funciones.
**194 irc Protocolo de chat** - Internet Relay Chat (IRC) es un sistema de comunicaci�n instantan�a que est� envuelto en una serie de reglas cliente - servidor.
**220 imap3** - Es un protocolo est�ndar cliente-servidor con el que accedes a tu correo desde el servidor local.
**443 shttp** - Servidor Web seguro.
**513 login** - Servicio que crea un login remoto a la Telnet.
**514 syslog Syslog** - Una lista de todas las peticiones que el usuario ha solicitado de un sitio Web.
**520 router** - Protocolo de informaci�n de routing.
**529 irc-serv IRC** - Chats.
**530 RPC Remote Procedure Call (RPC)** - Es un protocolo que un programa puede usar para solicitar un servicio de un programa que se encuentra en otro ordenador.
**1352 lotus notes** - Desde este servicio se accede al servidor de correo Lotus Notes.
**1397 audio-activmail** - Audio active mail.
**1433 ms-spl-s** - Microsoft SQL Server.
**1527 tlisrv** - Utilizado para acceder a Oracle.
**5631 pcanywheredata** - Soluci�n de control remoto que permite a los administradores que se conecten de forma segura y soluciones problemas a trav�s de cualquier tipo de conexi�n.

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


## Bibliograf�a

[Listado de los Protocolos y Puertos de Comunicaci�n](http://www.internetmania.net/int0/int133.htm)

[Ap�ndice C.Puertos comunes](http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-es-4/ch-ports.html)

[Principales protocolos de comunicaci�n](http://harold-vilchis-isc.blogspot.com/2013/09/principales-protocolos-de-comunicacion.html)

[Lista de protocolos y sus puertos](http://networkips.blogspot.com/2013/03/lista-de-protocolos-y-sus-puertos.html)

[Curso de redes - Parte 4 - Puertos y Protocolos](https://nksistemas.com/curso-de-redes-parte-4-puertos-y-protocolos/)

