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
$TTL 604801					# TTL in secs
practica.dns.bind.	IN SOA leak.com.ar. lbonsenor.itba.edu.ar (
				1		# Serial
				604800		# Refresh in secs (7 days)
				86400		# Retry in secs (1 day)
				60		# Expire in secs (1 min)
				60)		# Negative-Caching TTL

@			IN NS leak.com.ar.
www.practica.dns.bind.	IN A 1.2.3.4
www			IN A 2.3.4.5
@			IN A 2.3.4.5
```

4. `dig practica.dns.bind. @127.0.0.1 any`

5. Para obtener detalles: `dig SOA sitio.web.com @dns`

6. Para obtener las tablas de routeo: `route` o `ip route`

7. Para ver que puertos estan abiertos: `nmap 123.456.0.1 -p [FROM]-[TO]`

