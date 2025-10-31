# Con TCP
1. Terminal que escucha: `nc -l 9090 > miarchivo.txt`
2. Terminal que envia: `cat archivo.txt | nc pampero.it.itba.edu.ar 9090`

# Con UDP
1. Terminal que escucha: `nc -u -l 9090 > miarchivo.txt`
2. Terminal que envia: `cat archivo.txt | nc -u pampero.it.itba.edu.ar 9090`
