# **Sesión 3 - Redes - Ejercicios para entregar**

### Trabajar con redes docker
1. Vamos a crear dos redes de ese tipo (BRIDGE) con los siguientes datos:

##### Red1
- Nombre: red1  
- Dirección de red: 172.28.0.0  
- Máscara de red: 255.255.0.0  
- Gateway: 172.28.0.1  

![img1](img/img1.PNG)

##### Red2
- Nombre: red2  
- El resto de los datos será proporcionado automáticamente por Docker.proporcionados automáticamente por Docker.

![img2](img/img2.PNG)

2. Poner en ejecución un contenedor de la imagen `ubuntu:20.04` que tenga como hostname `host1`, como IP `172.28.0.18` y que esté conectado a la `red1`. Lo llamaremos `u1`.

![img3](img/img3.PNG)

3. Entrar en ese contenedor e instalar la aplicación ping (`apt update && apt install inetutils-ping`).

![img4](img/img4.PNG)

4. Poner en ejecución un contenedor de la imagen `ubuntu:20.04` que tenga como hostname `host2` y que esté conectado a la red2. En este caso será docker el que le de una IP correspondiente a esa red. Lo llamaremos `u2`.

![img5](img/img5.PNG)

5. Entrar en ese contenedor e instalar la aplicación ping (`apt update && apt install inetutils-ping`).

![img6](img/img6.PNG)

Deberás entregar los siguientes pantallazos comprimidos en un zip o en un documento pdf:

- Pantallazo donde se vea la configuración de red del contenedor u1.

![img7](img/img7.PNG)

- Pantallazo donde se vea la configuración de red del contenedor u2.

![img8](img/img8.PNG)

- Pantallazo donde desde cualquiera de los dos contenedores se pueda ver que no podemos hacer ping al otro ni por ip ni por nombre.

![img9](img/img9.PNG)

- Pantallazo donde se pueda comprobar que si conectamos el contenedor u1 a la red2 (con docker network connect), desde el contenedor u1, tenemos acceso al contenedor u2 mediante ping, tanto por nombre como por ip.

![img10](img/img10.PNG)


###  Despliegue de Nextcloud + mariadb/postgreSQL


Vamos a desplegar la aplicación nextcloud con una base de datos (puedes elegir mariadb o PostgreSQL) (**NOTA: Para que no te de errores utiiliza la imagen** `mariadb:10.5`). Te puede servir el ejercicio que hemos realizado para desplegar Wordpress. Para ello sigue los siguientes pasos:

1. Crea una red de tipo bridge.

![img11](img/img11.PNG)

2. Crea el contenedor de la base de datos conectado a la red que has creado. La base de datos se debe configurar para crear una base de dato y un usuario. Además el contenedor debe utilizar almacenamiento (volúmenes o bind mount) para guardar la información. Puedes seguir la documentación de mariadb o la de PostgreSQL.

3. A continuación, siguiendo la documentación de la imagen nextcloud, crea un contenedor conectado a la misma red, e indica las variables adecuadas para que se configure de forma adecuada y realice la conexión a la base de datos. El contenedor también debe ser persistente usando almacenamiento.

4. Accede a la aplicación usando un navegador web.

Deberás entregar los siguientes pantallazos comprimidos en un zip o en un documento pdf:

- Pantallazo con la instrucción para crear el contenedor de la base de datos.

![img12](img/img12.PNG)
![img13](img/img13.PNG)

- Pantallazo con la instrucción para crear el contenedor de la aplicación.

![img14](img/img14.PNG)

- Pantallazo donde se ve el acceso a 
 aplicación desde un navegador web.

 ![img15](img/img15.PNG)