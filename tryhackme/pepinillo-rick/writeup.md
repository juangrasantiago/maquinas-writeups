# Pepìnillo Rick

## ESCANEO DE PUERTOS

![](screenshots/01.png)

Entramos en el puerto 80 para ver su contenido

![](screenshots/02.png)

Entramos al código fuente y vemos la siguiente información

![](screenshots/03.png)

Username: R1ckRul3s

También haciendo gobuster encontramos un robots.txt y un assets entre otros directorios.

![](screenshots/04.png)

![](screenshots/05.png)

Tras problemas con la plataforma cambiamos de IP en varias ocaciones.

Encontramos también el directorio login.php, el cual nos redirige a esta página de login

![](screenshots/06.png)

Probamos las credenciales encontradas durante la investigación R1ckRul3s:Wubbalubbadubdub y estaremos dentro

## ENUMERACIÓN DE EXPLOIT

Ahora nos encontramos una vez iniciada la sesión dentro de un panel que nos deja ejecutar comandos

![](screenshots/07.png)

Observamos que algunos comandos se nos está restringidos

![](screenshots/08.png)

Usaremos "less" en vez de cat

![](screenshots/09.png)

y aquí encontraremos nuestra primera flag mr. meeseek hair

Creamos una reverse shell que ejecutaremos desde el mismo panel

![](screenshots/10.png)

![](screenshots/11.png)

Abrimos un canal de escucha por dicho puerto y estaremos dentro

![](screenshots/12.png)

Búscamos resultados y en el perfil de Rick encontramos el segundo ingrediente

1 jerry tear

![](screenshots/13.png)

## ESCALADA DE PRIVILEGIOS

Usamos `sudo -l` para ver que binarios podemos usar

![](screenshots/14.png)

Observamos que como usuario data tenemos el poder de usar todos "ALL" y sin contraseña "PASSWORD" Por lo que usaremos `sudo su` y así escalaremos a usuario root como vemos en la imagen.

Ya por último buscamos la 3 flags de nuestra máquina, que se situa en directorio /root

![](screenshots/15.png)