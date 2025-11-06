Envie un correo electronico cumpliendo todos los estandares y buenas practicas que cumpla con los siguientes requisitos:
	a. Contenga el header X-Parcial con el valor 2024/2
	b. Contenga un titulo: ¡Buenos Dias!
	c. Contenga como remitente su nombre, apellido y cuenta de correo del ITBA
	d. Contenga el texto ¡Hola mundo!
	e. Que se entrege a la direccion [legajo]@mail.sebikul.com
	f. Debe poder ser leido por MUAs que no soporten la codificacion quoted printable

Se debe poder verificar su recepcion utilizando el protocolo POP3
	Host: mail.sebikul.com
	Usuario: [legajo]@mail.sebikul.com
	Password: [legajo]@mail.sebikul.com

1. `host -t mx mail.sebikul.com`
2. `nc -C mail.sebikul.com smtp`

EHLO holis
MAIL FROM: <lbonsenor@itba.edu.ar>
RCPT TO: <62842@mail.sebikul.com>
DATA

MIME-Version: 1.0
Date: Wed, 5 Nov 2025 16:36:24 -0300
Message-ID: <CAFR8JkZBvHL8NtWQnm_DjwqyzMCm0Kqf_KVgN_EW=HJrFuDLKQ@mail.gmail.com>
Subject: =?UTF-8?B?[CODIGO EN BASE64]?=
X-Parcial: 2024/2
From: "LAUTARO BONSEÑOR" <lbonsenor@itba.edu.ar>
To: "LAUTARO BONSEÑOR" <62842@mail.sebikul.com>
Content-Type: multipart/alternative; boundary="000000000000fd22230642dde83f"

--000000000000fd22230642dde83f
Content-Type: text/plain; charset="UTF-8"
Content-Transfer-Encoding: base64

[CODIGO EN BASE64]

--000000000000fd22230642dde83f

Content-Type: text/html; charset="UTF-8"
Content-Transfer-Encoding: base64

[CODIGO HTML EN BASE64]
<div dir=3D"ltr">=C2=A1Hola! Esto es el subject</div> EN BASE64

--000000000000fd22230642dde83f--


3. Para verificar: `nc -C localhost 110`

USER 62842@mail.sebikul.com
PASS 62842@mail.sebikul.com
LIST
RETR 1
QUIT
