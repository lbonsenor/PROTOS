R: Nuestra computadora REAL que levanta una VM
R.ip = 192.168.123.1
VM.ip = 192.168.123.2

Como el router nos asigna una IP 10.2.2.19 => La subred es 10.2.2.0/24

1. Para conocer todos los que estan conectados en la red: `nmap -sn 10.2.2.*`
2. Para desactivar una interfaz: `sudo ifocnfig <interfaz> down`
3. Para asignar una IP a una interfaz: `ifconfig <interfaz> <ip>/<mask>`
4. Para agregar a la tabla de ruteo: `sudo route add -net 10.2.2.0/24 gw 192.168.19.1`

## Firewall
1. Para borrar las cadenas input, forward y output: `iptables -F` 
2. Para borrar todas las cadenas intermedias: `iptables -X`

### Politicas
3. Cuando el paquete no esta destinado al host: `iptables -P FORWARD ACCEPT`
4. Cuando el paquete tiene como destino el sistema local: `iptables -P INPUT ACCEPT`
5. Cuando el paquete tiene como origen el sistema local: `iptables -P OUTPUT ACCEPT`

ACCEPT: Acepta
DROP: Rechaza silenciosamente
REJECT: Rechazar con aviso
RETURN: Volver a la cadena anterior
