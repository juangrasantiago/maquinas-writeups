# AnonymousPingu

## ESCANEO DE PUERTOS

`nmap -p- -sS -sC -sV --open --min-rate=5000 -vvv -n -Pn 172.17.0.2`

![](screenshots/01.png)

vemos los puertos 21 y 80 abiertos , pero vemos que podemos acceder por protocolo ftp mediante Anonymous, como también vemos varios archivos como el upload para subir contenido.

## EXPLOTACIÓN MEDIANTE REVERSE SHELL

Entramos dentro mediante ftp Anonymous.

creamos un archivo malicioso php desde reverse shell

![](screenshots/02.png)

Dentro de upload procedemos a subirlo con put

![](screenshots/03.png)

Luego hacemos tratamiento de tty

## ESCALADA DE PRIVILEGIOS

usamos ***sudo -l*** para ver que binarios se pueden ejecutar

![](screenshots/04.png)

Vemos que pingu puede ejecutar "man"

Buscamos en GTFObins man y ejecutamos lo siguiente "sudo -u pingu man man"

y dentro !/bin/bash

![](screenshots/05.png)

Volvemos a repetir sudo -l y vemos que gladys puede ejecutar nmap y dpkg

![](screenshots/06.png)

**sudo -u gladys dpkg -l** ejecutamos el comando anterior y seguido de nuevo !/bin/bash

Entramos dentro de gladys,

![](screenshots/07.png)

y buscamos de nuevo binarios donde encontramos chown. Posteriormente lo buscamos en gtfobins.

![](screenshots/08.png)

cambiamos las carpetas finales a estas: sudo chown (id -un):(id -gn) /etc/passwd

Con esto podremos editar la carpeta /etc/passwd

![](screenshots/09.png)

La cual quitaremos la "x" de root copiando todo lo que contiene en ella.

![](screenshots/10.png)

Una vez echo esto accedemos con ***su root***.