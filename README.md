### Principales Protocolos de Internet y sus Puertos

* _Protocolo de internet_: El protocolo internetwork m�s com�n es el Protocolo de Internet (IP). IP es responsable de tomar los segmentos formateados del TCP, encapsularlos en paquetes, asignarles las direcciones correctas y seleccionar la mejor ruta hacia el host de destino.

* _Protocolos de acceso a la red_: Estos protocolos describen dos funciones principales: administraci�n de enlace de datos y transmisi�n f�sica de datos en los medios. Los protocolos de administraci�n de enlace de datos toman los paquetes IP y los formatean para transmitirlos por los medios. Los est�ndares y protocolos de los medios f�sicos rigen de qu� manera se env�an las se�ales por los medios y c�mo las interpretan los clientes que las reciben. Los transceptores de las tarjetas de interfaz de red implementan los est�ndares apropiados para los medios que se utilizan.

* _Protocolo de aplicaci�n_: Protocolo de transferencia de hipertexto (HTTP) es un protocolo com�n que regula la forma en que interact�an un servidor Web y un cliente Web. HTTP define el contenido y el formato de las solicitudes y respuestas intercambiadas entre el cliente y el servidor. Tanto el cliente como el software del servidor Web implementan el HTTP como parte de la aplicaci�n. El protocolo HTTP se basa en otros protocolos para regir de qu� manera se transportan los mensajes entre el cliente y el servidor.

* _Protocolo de transporte_: Protocolo de control de transmisi�n (TCP) es el protocolo de transporte que administra las conversaciones individuales entre servidores Web y clientes Web. TCP divide los mensajes HTTP en peque�as partes, denominadas segmentos, para enviarlas al cliente de destino. Tambi�n es responsable de controlar el tama�o y los intervalos a los que se intercambian los mensajes entre el servidor y el cliente.

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
**194 irc Protocolo de chat** - Internet Relay Chat (IRC) es un sistema de comunicaci�n instantan�a que est� envuelto en una serie de reglas cliente � servidor.
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
