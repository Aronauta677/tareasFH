# Práctica SSH

## Configuración Inicial

1. Creamos las clonaciones de nuestras máquinas y configuramos los puertos de red:
   - Máquina A: puerto `2222`
   - Máquina B: puerto `2223`

![Primera](imagenes/1.png)
![Segunda](imagenes/2.png)

2. Nos conectamos por **SSH** a las dos máquinas.
   
![Tercera](imagenes/3.png)
![Cuarta](imagenes/4.png)

## Creación de Usuarios

- En la máquina **A**, creamos el usuario `Alex`.
  
![Quinta](imagenes/5.png)

- En la máquina **B**, creamos el usuario `Brais`.
  
![Sexta](imagenes/6.png)

## Configuración de IPs

- Configuramos las direcciones IP en ambas máquinas y verificamos la conectividad con un **ping**.
![Septima](imagenes/7.png)

## Conexión SSH entre Máquinas

- Desde la máquina **A**, realizamos una conexión SSH hacia la máquina **B**.

![Octava](imagenes/8.png)

- Al conectarnos, se genera un archivo `known_hosts` en `~/.ssh/` que guarda la huella digital del servidor B.

## Transferencia de Archivos

1. En la máquina **A**, creamos el directorio `prueba` con el archivo `prueba.txt` en la ruta temporal y enviamos la información a la máquina B.

![Novena](imagenes/9.png)

3. En la máquina **B**, creamos el directorio `prueba2` con el archivo `prueba2.txt` en su ruta temporal y lo enviamos al cliente A.

![Décima](imagenes/10.png)

5. Transmitimos los directorios `prueba` y `prueba2` al ordenador anfitrión. Ejecutamos los comandos necesarios desde la máquina anfitrión.

![Undécimo](imagenes/11.png)
![Duodécimo](imagenes/12.png)
![Decimotercero](imagenes/13.png)

7. Creamos el directorio `prueba3` en el servidor con **200 archivos .txt** y lo transmitimos al escritorio del anfitrión.

![Decimocuarto](imagenes/14.png)
![Decimoquinto](imagenes/15.png)


## Autenticación por Clave SSH

- Generamos un **par de claves SSH** en el cliente.

![Decimosexto](imagenes/16.png)

- Establecemos el passphrase: `servidorssh`.

![Decimoséptimo](imagenes/17.png)

- Conectamos desde el usuario `Alex` en A hacia `Brais` en B usando la clave con passphrase `servidorssh`.
