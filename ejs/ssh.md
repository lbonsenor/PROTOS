Realice los cambios necesarios para que: 
Desde una terminal de su host al ejecutar el comando: 
`tail -f archivo.log` 
Pueda seguir los cambios en vivo del archivo `/tmp/pdc` del host `pampero.itba.edu.ar`

1. `ssh -L 12345:localhost:12345 lbonsenor@pampero.itba.edu.ar`
2. Desde pampero: `tail -f /tmp/pdc | nc -l localhost 12345`
3. Desde otra terminal: `nc localhost 12345 > archivo.log`
