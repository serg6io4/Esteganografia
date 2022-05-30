# Esteganografia

La Esteganografia trata el estudio y aplicación de técnicas que permiten ocultar mensajes u objetos, dentro de otros, llamados portadores, de modo que no se perciba su existencia. Es decir, procura ocultar mensajes dentro de otros objetos y de esta forma establecer un canal encubierto de comunicación, de modo que el propio acto de la comunicación pase inadvertido para observadores que tienen acceso a ese canal.

Puntos básicos:

-Partiendo de que una imagen a color cada píxel viene determinado por sus valores RGB que determinan la tonalidad del mismo.
-El tamaño de la imagen va correspondiendo al tamaño del mensaje a ocultar.
-Toda letra tiene su representación ASCII y por consiguiente su valor binario, necesitaremos su valor binario que es representable mediante 8bits.
![image](https://user-images.githubusercontent.com/48441610/170986615-762172b0-9d0e-4c81-8d9e-f36c99d062b6.png)


Por lo que partiendo la encriptación llevará este proceso: 
Pongamos que queremos ocultar la "A" que como se puede ver tiene el valor ASCII de 65, que en binario sería 0100 0001.
La queremos ocultar en una imagen por lo que solo necesitamos los 3 primeros píxeles de la imagen(debido a que es solo una letra), debido a que seguirá la siguiente lógica:
Se posiciona cada número del binario en RGB por ejemplo:
![image](https://user-images.githubusercontent.com/48441610/170987536-0b43f833-0503-4943-a2be-3a20ad2f710e.png)

Y ahora viene la asociación de los píxeles con los números binarios, si el número binario es 1, el número del píxel tiene que ser impar y por el contrario si el número binario es 0, el número del píxel debe ser par. Por lo que si no coinciden de primera habrá que modificar el número del píxel sumando uno para que sea impar o par.
![image](https://user-images.githubusercontent.com/48441610/170988058-4371f375-a7c3-4061-9404-acaba43f214f.png)

Por último, si el último número del píxel de la imagen es par se termina el mensaje, y si es par se continua el mensaje. En nuestro caso es 120 por lo que se termina el mensaje.

Para extraer la información simplemente se hace el paso contrario, y cada 3 píxeles vas mirando el último número del píxel RGB, para saber si sigue o no.
