El host en 192.168.1.3 es el gateway de la red 10.0.0.0/24. Descubra los servicios que tiene expuesto el host 10.0.0.1
De existir, muestre el resultado de acceder via HTTP a dicho servidor
Muestre todos los routers que intervienen en esta comunicacion

1. Poner la VM en modo Bridge conectado a Protos-Lab
2. `sudo ip route add 10.0.0.0/24 via 192.168.1.3`
3. `nmap -sS 10.0.0.1`
	-sS: Escaneo rapido y silencioso
	-Pn: No haga ping
	-sV: Para obtener versiones de los servicios

4. En caso de que haya un servidor http usamos curl a [ip]:[port]
5. Para mostrar los routers que intervienen: sudo traceroute 10.0.0.1
