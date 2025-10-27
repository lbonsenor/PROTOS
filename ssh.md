1. `sudo apt install ssh`
## Transferencia de Archivos
`scp usuario@servidor.com:/archivo/a/enviar /archivo/donde/recibir`

## Tunel local
1. `ssh -L<local_port>:<remote_ip>:<remote_port> usuario@servidor.com -g`

## Tunel remoto
1. `ssh -R1234:127.0.0.1:9090 protos`	<!-- Expon el puerto 9090 de mi maquina en el puerto 1234 de SABF -->
2. Desde otra terminal local: `ncat -l 9090`
3. Desde la terminal donde hice ssh (servidor): `nc localhost 1234`

## Tunel dinamico
1. `ssh -Dlocalhost:8080 lbonsenor@pampero.itba.edu.ar`
