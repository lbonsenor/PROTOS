# traceroute [opciones] destino
	-n: No resuelve nombres de host (muestra solo IPs, más rápido).
	-I: Usa ICMP Echo Request en lugar de UDP (similar a ping).
	-T: Usa TCP SYN en vez de UDP (útil para firewalls que bloquean ICMP/UDP).
	-p <puerto>: Puerto destino (solo para UDP o TCP).
	-m <max_ttl>: Máximo número de saltos (TTL). Por defecto es 30.
	-q <n>: Número de consultas por salto (por defecto es 3).
	-w <segundos>: Tiempo de espera por respuesta de cada salto (timeout)

