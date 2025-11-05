1. `sudo apt install bind9`
2. `nano /etc/bind/named.conf` y agregar
```
zone "practica.dns.bind" {
	type master;
	file "/etc/bind/bind.local";
};
```
3. `nano /etc/bind/bind.local`
```
	$TTL 604800 
	@ IN SOA ns1.it.itba.edu.ar. admin.it.itba.edu.ar. ( 
	 	202506051	; Serial (actualizar cada vez que se hace un cambio)
	 	604800		; Refresh
	 	86400		; Retry
	 	2419200 Expire
	 	604800		; Negative Cache TTL 
		)
	
	; 
	; Name Servers 
	@	IN NS ns1.it.itba.edu.ar. 

	; Mail
	@	IN MX 10 correo 

	; Hosts 
	ns1.it.itba.edu.ar.	IN A 192.168.70.1
	pampero			IN A 192.168.70.10

	; Aliases 
	www		IN CNAME pampero 
	correo		IN CNAME pampero
```

4. `dig practica.dns.bind. @127.0.0.1 any`

5. Para obtener detalles: `dig SOA sitio.web.com @dns`

6. Para obtener las tablas de routeo: `route` o `ip route`

7. Para ver que puertos estan abiertos: `nmap 123.456.0.1 -p [FROM]-[TO]`

