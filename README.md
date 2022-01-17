# Práctica patrón worker threads
Práctica sobre uso del patrón *worker threads* en Linux usando C para la materia Programación de Sistemas (CCPG1051) de la ESPOL.

## Instrucciones
La práctica consiste en modificar una aplicación cliente - servidor que implementa una consola remota para que atienda varios clientes de manera simultánea usando *prethreading*.

Este repositorio contiene código ejemplo de una aplicación cliente - servidor que implementa una consola remota básica. Es decir, los comandos que se envian desde el cliente al servidor son ejecutados en el servidor y su salida es enviada al cliente a través del socket de conexión. El servidor es multi-cliente usando hilos.

Es necesario efectuar las siguientes modificaciones:
1. Modificar el repositorio para implementar la técnica de *prethreading*. Es decir, el servidor debe de crear *n* hilos al iniciar los cuales son consumidores de un buffer con conexiones de clientes simultáneas. La cantidad de hilos a crear debe ser especificada usando la opción -j <número de worker threads>.

El programa servidor *server* debe tener el siguiente comportamiento:
```
$ ./server -h
Servidor simple de ejecución remota de comandos.
uso:
 ./server [-j <número de worker threads>] [-d] <puerto>
 ./server -h
Opciones:
 -h			Ayuda, muestra este mensaje
 -d			Funciona en modo daemon
 -j			Especifica el número de worker threads
```

El programa cliente *client* no debe ser modificado.

## Entregable
Modificar el código ejemplo en este repositorio para implementar la funcionalidad requerida. El servidor debe usar un número fijo de worker threads para atender varios clientes de manera simultánea. 
Adicional, subir a sidweb ultimo hash y screenshot del testfile

## Compilación
Para compilar cliente y servidor:
```
$ make
```
Para compilar solo el servidor:
```
$ make server
```
Para compilar cliente y servidor facilitando la depuración con gdb:
```
$ make debug
```
Para compilar cliente y servidor habilitando la herramienta AddressSanitizer, facilita la depuración en tiempo de ejecución:
```
$ make sanitize
```
