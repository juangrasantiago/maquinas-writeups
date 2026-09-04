# BreakMySSH

## ESCANEO DE PUERTOS

`nmap -p- -sS -sC -sV --open --min-rate=2000 -vvv -n -Pn 172.17.0.2`

![](screenshots/01.png)

vemos el puerto 22 ssh abierto

En este caso como no tenemos referencias de usuarios y ningún dato que nos de alguna pista realizaremos desde metasploit una búsqueda de usuarios de ssh con **ssh_enum**

## BÚSQUEDA DE USUARIOS DESDE METASPLOIT PARA SSH

![](screenshots/02.png)

elegimos la primera opción "use 0"

Y rellenamos todos los datos, en este caso el RHOSTS y el USER_FILE con el diccionario correspondiente.

![](screenshots/03.png)

Una vez echo esto lo lanzamos y nos encontrará los siguientes usuarios.

![](screenshots/04.png)

## FUERZA BRUTA CON HYDRA AL PROTOCOLO SSH

Probamos con el usuario root

`hydra -l root -P /usr/share/wordlists/rockyou.txt -t 64 ssh://172.17.0.2`

![](screenshots/05.png)

conseguimos las credenciales root:estrella

hacemos la intrusión.

![](screenshots/06.png)

En este caso ya somos usuario root al entrar con estas credenciales.

En el caso de acceder con el usuario lovely, explorariamos los diferentes directorios, siendo el /opt donde encontremos un archivo hash que descifrado contiene la credencial "estrella" para subir a root.