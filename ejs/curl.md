Obtenga la representacion textual en el lenguaje español del recurso <http://ejercicio2.sebikul.com:8080/foo/> usando curl
Dato: La red no rutea paquetes hacia el host ejercicio2.sebikul.com, pero este es accesible mediante un proxy <socks5h://proxy.sebikul.com:1080>

1. Para cambiar el idioma: `curl -H "Accept-Language: es"`
2. Para aceptar texto plano: `curl -H "Accept: text/plain"`
3. Para que use un proxy: `curl -x socks5h://proxy.sebikul.com:1080`

RTA: `curl -x socks5h://proxy.sebikul.com:1080 -H "Accept-Language: es" -H "Accept: text/plain" http://ejercicio2.sebikul.com:8080/foo/
