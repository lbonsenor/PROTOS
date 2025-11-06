# nmap [opciones] <objetivo>
	-p <puerto(s)>: Escanea puertos específicos (ej. -p 22,80 o -p 1-1000)
	-Pn: No hace ping (útil si el host bloquea ICMP)
	-T<0-5>: Velocidad/agresividad del escaneo (0 = más lento, 5 = más rápido)
	-A: Detección de SO, versión de servicios, traceroute y scripts comunes
	-O: Detección del sistema operativo.
	-sS: Escaneo TCP SYN
	-sT: TCP connect scan
	-sU: Escaneo UDP
	-sV: Detecta versiones de servicios
	-v: Modo verboso (más salida)
	--open: Muestra solo puertos abiertos
	-iL <archivo>	: Leer lista de objetivos desde archivo
	-6: Escaneo sobre IPv6
	-sS: Escaneo TCP SYN (stealth scan)
	-sT: Escaneo TCP connect (más visible)
	-sU: Escaneo de puertos UDP

