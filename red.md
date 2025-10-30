1. Imprimir tabla de routeo: `route -n`

2. Asignar una IP a una interfaz: `ip addr add 192.168.56.2/24 dev enp0s3` donde
- `192.168.56.2` es la ip
- `/24` es la mascara de red 255.255.255.0
- `enp0s3` es la interfaz

3. `sudo route add -net 192.168.1.0 netmask 255.255.255.0 gw 192.168.56.1`
- Para llegar a la red 192.168.1.0 hay que pasar a traves de 192.168.56.1

4. Ver si tenemos el firewall activado: `sudo iptables -L` y si todo es ACCEPT, no esta activado

5. Para desactivar el firewall: `sudo iptables -F` y despues `sudo iptables -X`

6. Para activar la nat:
- `iptables -L -t nat` 	para ver las reglas
- `iptables -t nat -A POSTROUTING -o wlp2s0 -j SNAT --to-source <ipPublica>`
- `iptables -t nat -A POSTROUTING -o wlp2s0 -j MASQUERADE`

7. Para activar/desactivar forwarding:	`echo 0 > /proc/sys/net/ipv4/ip_forward`
- 0 para desactivar
- 1 para activar

8. Evitar la comunicacion con una red: `route add -net 192.168.14.0/27 reject`
- Otra solucion es `route add -net 192.168.14.0/27 gw 192.168.100.99` (pongo un gw que pertenezca a la red local)

9. Asignar mas de una ip a una interfaz: `ifconfig eth0:0 192.168.1.16 up`
- `eth0:0` es el alias
- `192.168.1.6` es la ip a agregar a la interfaz eth0
- Todas las ips deben estar en la misma subred
