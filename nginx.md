1. `sudo apt install nginx`
2. `cd /etc/nginx` Para verificar que exista `sites-available` y `sites-enabled`
3. `cd /var/www`, `mkdir bar` y `nano index.html`
4. `cd /etc/nginx/sites-available/` y `cp default bar`
```
server {
        listen 80 ; 
        listen [::]:80 ;

        root /var/www/bar;

        access_log /var/log/nginx/bar_access.log;            
        error_log  /var/log/nginx/bar_error.log;            

        index index.html index.htm index.nginx-debian.html;

        server_name bar;
         
        location / {
                try_files $uri $uri/ =404;
        }
}
```
5. `cd /etc/nginx/sites-enabled/` y `ln -s ../sites-available/bar .`
6. `nano /etc/hosts` y modificar para que bar se resuelva a 127.0.0.1
7. `service nginx restart`
8. `curl -H "Host: bar" http://bar/`

