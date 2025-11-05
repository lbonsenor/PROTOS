Realizar los cambios necesarios para que al ingresar a http://foo.example.org se sirva el contenido de http://protos.sebikul.com/. 
Conservando el valor del header X-Parcial-Protos

1. Para testear: `curl http://foo.example.org/`
2. En `/etc/nginx/sites-available`: sudo nano parcial1
```
	server {
		listen 80;
		server_name foo.example.org;
	
		location / {
			proxy_pass http://protos.sebikul.com;
			proxy_set_header Host $host;
			proxy_set_header X-Parcial-Protos $http_x_parcial_protos;
		}
	}

```
3. En `/etc/nginx/sites-enabled`: `ln -s ../sites-available/parcial1 .`
4. En `/etc/hosts` agrego foo.example.org
5. `service nginx restart`
