1. `sudo apt install apache2`
2. `nano /etc/apache2/sites-available/000-default.conf` y cambiar a <VirtualHost *:8080>
3. `nano /etc/apache2/ports.conf`
```conf
# If you just change the port or add more ports here, you will likely also
# have to change the VirtualHost statement in
# /etc/apache2/sites-enabled/000-default.conf

Listen 8080

<IfModule ssl_module>
	Listen 443
</IfModule>

<IfModule mod_gnutls.c>
	Listen 443
</IfModule>
```
4. `systemctl restart apache2`

# Reverse Proxy
5. `nano /etc/nginx/sites-available/bar` y agregar en location / `proxy_pass http://localhost:8080`
6. `service nginx restart`
