1. `sudo apt install nginx`
2. `cd /etc/nginx` Para verificar que exista `sites-available` y `sites-enabled`
3. `cd /var/www`, `mkdir foo` y `nano index.html`
4. `cd /etc/nginx/sites-available/` y `cp default foo`
```
server {
        listen 80 ; 
        listen [::]:80 ;

        root /var/www/foo;

        access_log /var/log/nginx/foo_access.log;            
        error_log  /var/log/nginx/foo_error.log;            

        index index.html index.htm index.nginx-debian.html;

        server_name foo;
         
        location / {
                try_files $uri $uri/ =404;
        }
}
```
5. `cd /etc/nginx/sites-enabled/` y `ln -s ../sites-available/foo .`
6. `nano /etc/hosts` y modificar para que foo se resuelva a 127.0.0.1
7. `service nginx restart`
8. `curl -H "Host: foo" http://foo/`

