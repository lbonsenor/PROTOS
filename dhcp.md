WARNING: ESTAR EN UNA RED INTERNA

1. `sudo apt install isc-dhcp-server isc-dhcp-client`
2. Para pedir una IP: `sudo dhclient -r -d <interfaz>`

3. En `/etc/dhcp/dhcpd.conf/`: ```
	# Vamos a estar creando una subred.
	subnet 10.5.5.0 netmask 255.255.255.224 { # Red y mascara de red
		range 10.5.5.26 10.5.5.30; # Tangos que vamos a asignar
		option domain-name-servers ns1.internal.example.org; # Servidores de dominios
		option domain-name "internal.example.org"; # No se que es
		option subnet-mask 255.255.255.224; 
		option routers 10.5.5.1; # Gateway de la red
		option broadcast-address 10.5.5.31;
		default-lease-time 600;
		max-lease-time 7200; 
	}
```

4. Para que el network manager no le asigne una direccion ip
```
	subnet 192.168.113.0 netmask 255.255.255.0 {
  		range 192.168.113.100 192.168.113.200; 
  		option domain-name-servers 8.8.8.8; # DNS de Google
  		option subnet-mask 255.255.255.0;
  		option routers 192.168.113.1; # Gateway
  		option broadcast-address 192.168.113.255;
  		default-lease-time 600;
  		max-lease-time 7200;
	}	
```

5. En `/etc/default/isc-dhcp-server` configuramos la interfaz que queremos que escuche
```
INTERFACESv4="<nombre_interfaz_cable_ethernet>"

# En mi caso:
INTERFACESv4="enp0s3"
```
7. `sudo ip addr add 192.168.113.1/24 dev enp0s3`

6. `systemctl restart isc-dhcp-server`
