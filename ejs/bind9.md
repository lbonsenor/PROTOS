Instale un servidor de nombres BIND y realice los cambios necesarios para servir la zona demiloo.com.ar
	1. Su servidor de DNS sera la autoridad para estas zonas
	2. El correo de contacto es demiloo@leak.com.ar
	3. demiloo.com.ar debe ser un registro A apuntando a la direccion IP de foo.leak.com.ar con validez de 1h
	4. El subdominio www debe ser registros CNAMEs apuntando a la raiz de la zona con validez de 2w
	5. La zona deben poder recibir correos electronicos, atendido por los mismos servidores de correos que proto.leak.com.ar, con validez de 1w 


1. En `/etc/bind/named.conf.local/`
	zone “demiloo.com.ar” {
		type master;
		file “/etc/bind/demiloo.com.ar”;
	};

2. Buscamos la direccion IP de <foo.leak.com.ar> y para el MX de <proto.leak.com.ar> con dig

3. En `/etc/bind/demiloo.com.ar` 
```
$TTL 7d
demiloo.com.ar	IN SOA	ns.demiloo.com.ar	demiloo.leak.com.ar. (
			1	; Serial
			7d	; Refresh
			1d	; Retry
			14d	; Expire
			1m	; Negative TTL
)

@		3600s	IN A 		76.76.21.241			; IP de foo.leak.com.ar
@			IN NS		ns.demiloo.com.ar
ns			IN A		1.2.3.4
www		14d	IN CNAME	demiloo.com.ar
@		7d	IN MX	20	smtp20.proto.leak.com.ar	; IP de proto.leak.com.ar
@		7d	IN MX	21	smtp30.proto.leak.com.ar	; IP de proto.leak.com.ar

```
