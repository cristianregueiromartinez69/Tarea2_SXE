### Explicacion de comandos de Docker

1. Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo.

Para esto primero de todo necesitamos asegurarnos de una serie de cosas:
- Comprobar que docker está instalado
- Comprobar que docker funciona
Una vez hecho esto, ejecutamos el siguiente comando:

**sudo docker pull alpine**

Este comando usa sudo, pero se puede hacer sin él. Ahora vamos a comprobar que se instaló, probemos este comando:
**sudo docker images**

Si nos sale Alpine, es que funciona.

2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre.

- Vamos a crear un contenedor sin nombre:
**sudo docker run -i alpine /bin/sh

## Vamos a explicar el comando:
- docker run: Este comando arranca el contenedor
- it: ejecutamos el contenedor de manera que aparece el terminal, como en una shell
- alpine: usamos la imagen de alpine
- /bin/sh: ejecutamos la shell dentro del contenedor

Para comprobar que el contenedor está o no arrancado, lo comprobamos con el siguiente comando:
**docker ps**

Comprobamos que no lo está, así que ejecutamos:

**docker ps -a**

Con este comando comprobamos los contenedores apagados y sin apagar.
El nombre del contenedor es: peaceful_pare (el nombre es aleatorio ya que no ha sido especificado)



