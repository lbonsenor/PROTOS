## Para encontrar direcciones IP de los servidores SMTP que reciben correos
`dig -t MX +short proto.leak.com.ar | sort -n`

## Direcciones IP permitidas para enviar mails (Segun SPF)
`dig -t TXT +short itba.edu.ar.` y buscar por v=spf1

## Enviar un correo a alguien del ITBA
`dig +short -t MX itba.edu.ar. | sort -n` y nos conectamos al primer servidor

`nc -v -C aspmx.l.google.com. 25`
EHLO hola.com.ar
MAIL FROM: <lala@leak.com.ar>
RCPT TO: <cditoro@itba.edu.ar>
DATA

From: "Camila Di Toro" (personal) <cami@leak.com.ar>
To: "Camila Di Toro" <cditoro@itba.edu.ar>
Subject: prueba pdc 
MIME-Version: 1.0
Content-type: text/plain; charset=UTF-8
Content-transfer-Encoding: quoted-printable

Holiiiis
.
