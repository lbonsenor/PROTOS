# nc
	-l: Pone a netcat en modo escucha (servidor)
	-p: Especifica el puerto local cuando se usa -l
	-v: Verbose
	-n: Evita la resolucion de nombres DNS
	-u: Usa UDP en lugar de TCP
	-z: Escaneo de puertos sin enviar datos
	-C: Habilitar la conversion de \r a \r\n

Servidor: `nc -l [PUERTO]`
Cliente: `nc localhost [PUERTO]`

