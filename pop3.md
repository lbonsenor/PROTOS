1. `sudo apt install postfix`
2. En la configuracion de postfix: Internet Site > foo.pdc > 
3. `sudo apt install net-tools`
4. `nc -C localhost 25`
	EHLO postfix
	MAIL FROM: <mail@itba.edu.ar>
	RCPT TO: <lbonsenor@foo.pdc>
	DATA
	content
	.
	QUIT
5. `cat /var/spool/mail/lbonsenor` Dice el contenido del mail
6. `mkdir maildir` y agregamos al final de `/etc/postfix/main.cf` `home_mailbox= maildir/`
7. Ahora si mandamos un mail, podemos leerlo con `cat ~/maildir/new/*`

## DOVECOT
1. `sudo apt install dovecot-pop3d`
2. `netstat -ntlp | grep :110` para checkear que este corriendo
	CAPA 			<!-- Capacidades -->
	USER mi-user-de-linux	
	PASS mi-passwd-de-linux
	LIST			<!-- Mails -->
	RETR 1			<!-- Leo el primer mail y se mueve de new a cur -->
	DELE 1			<!-- Borro el primer mail -->
	RSET			<!-- Me arrepenti -->
	QUIT
3. `nano /etc/dovecot/conf.d/10-mail.com` y cambiar `mail_location = maildir:~/maildir`
