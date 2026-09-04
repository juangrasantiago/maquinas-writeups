# FindYourStyle

## ESCANEO DE PUERTOS

![](screenshots/01.png)

Identificamos que es un Drupal gracias al escaneo.

## ENUMERACIÓN DE EXPLOIT

Tras investigar observamos el siguiente

## CVE-2018-7600

![](screenshots/02.png)

Añadimos los datos que nos pida (LHOST Y RHOSTS)

![](screenshots/03.png)

Y estamos dentro

![](screenshots/04.png)

## ESCALADA DE PRIVILEGIOS

Con este comando podremos tener una shell más comoda **script /dev/null -c bash**

![](screenshots/05.png)

Vemos que existe un usuario llamado ballenita

También buscamos los binarios

![](screenshots/06.png)

Utilizaremos el binario su para intentar cambiar de usuario.

Para ello buscaremos la contraseña de “ballenita”

Investigaremos todos los directorios.

Se inspecciona el fichero settings.php localizado en /var/www/html/sites/default

![](screenshots/07.png)

Encontramos aquí las credenciales ballenita:ballenitafeliz

Cambiamos de usuario con su ballenita y su contraseña

Ejecutamos sudo -l para ver que binarios puede ejecutar ballenita

![](screenshots/08.png)

y observamos que ls y grep ambos pueden ejecutarse, por lo que buscaremos

`sudo ls -la /root`

![](screenshots/09.png)

Y para ver el contenido de cualquier archivo añadiremos a grep “” para que nos muestre todo lo que contiene.

![](screenshots/10.png)

Y ahora si entramos como root.

![](screenshots/11.png)