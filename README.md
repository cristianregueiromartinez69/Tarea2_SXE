### Explicacion de comandos de Docker

1. ***Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo.***

Para esto primero de todo necesitamos asegurarnos de una serie de cosas:
- Comprobar que docker está instalado
- Comprobar que docker funciona
Una vez hecho esto, ejecutamos el siguiente comando:

**sudo docker pull alpine**

Este comando usa sudo, pero se puede hacer sin él. Ahora vamos a comprobar que se instaló, probemos este comando:
**sudo docker images**

Si nos sale Alpine, es que funciona.

2. ***Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre.***

- Vamos a crear un contenedor sin nombre:
**sudo docker container create -i -t alpine

## Vamos a explicar el comando:
- docker container create: Este comando arranca el contenedor
- i: ejecutamos el contenedor de manera que aparece el terminal, como en una shell
- t: Se asocia un terminal (tty) al contenedor
- alpine: usamos la imagen de alpine

Para comprobar que el contenedor está o no arrancado, lo comprobamos con el siguiente comando:
**docker ps**

Comprobamos que no lo está, así que ejecutamos:

**docker ps -a**

Con este comando comprobamos los contenedores apagados y sin apagar.
El nombre del contenedor es: peaceful_pare (el nombre es aleatorio ya que no ha sido especificado)

3. ***Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?***
Ahora vamos a crear un contenedor con nombre, para ello ejecutamos:
- sudo docker container create -i -t --name dam_alp1 alpine

La sintaxis es la misma que en el comando anterior, pero especificamos un parametro más.
- --name (nombre del contenedor): entre parentesis ponemos el nombre del contenedor y comprobamos que fue creado con el comando del paso 2.

Accedemos a él con el siguiente comando:

**sudo docker container start --attach -i dam_alp1**

Con esto no solo lo iniciamos si no que con el --attack accedemos directamente

4. ***Comprueba que ip tiene y si puedes hacer un ping a google.com***

Lo primero es arrancar y meternos en el contenedor, ejecutamos:

**sudo docker container start --attach -i dam_alp1**

ahora metemos:

**ip a**

La cual nos dará la dirección ip de nuestro contenedor. Si ejecutamos:

**ping google**
 podremos hacer un ping a google.com

5. ***Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?***

## Explicacion del proceso:
- primero arrancar el contenedor dam_alp1:

**sudo docker container start --attach -i dam_alp1**

- Nos vamos a otro terminal con alt + f2 y creamos un contenedor:ç

**sudo docker container create -i -t --name dam_alp2 alpine**

- Accedemos a el:

**sudo docker container start --attach -i dam_alp2**

- Ahora ejecutamos en ambos terminales, siempre dentro del contenedor claro:

**ip a** y luego **ping 172.17.0.2**

cada uno pondra la ip que le corresponda para hacer el ping
