# Parcial Primer Corte AREP

#### Realizado por:
- Nicolás Pachón Unibio

## Descripción

Para este ejercicio se solicito que se realizara
un almacenamiento llave-valor(key,value) basado
en 3 componentes principales, siendo estos un browser
realizado con html y js, una "fachada" encargada de recibir
los datos enviados por el cliente y asimismo enviarlos al
backend web el cual se encargara de procesar y realizar una 
de las 2 solicitudes planteadas,siendo estas crear una llave
usando el metodo GET o cambiar el valor de dicha llave
asimismo aprovechando el metodo GET.

## Creación

La forma en la que se abordo este ejercicio fue asignandole
una funcionalidad a cada uno de los componentes, generando
que cada uno realice solo una accion cuando cuando se ejecute
el metodo GET, dando como consecuencia el siguiente ciclo al
realizar una solicitud:

- El usuario solicita mediante GET una llave en el
servidor web.
- Esta solicitud se envia a la fachada, la cual estara
a cargo de diferenciar si la solicitud es de crear una llave
o editar el valor de una llave, para posteriormente enviarselo
al backend.
- El backend se encargara de recibir la información enviada
por la fachada sobre el metodo a realizar para posteriormente
realizarlo en su propio logica y devolver el valor retornado de
la operación a la fachada, donde si fue un get key, devolvera su 
valor, en caso de no existir  la creara vacia, en caso contrario
donde se desee cambiar el valor de una llave, devolvera la llave
actualizada con su nuevo valor.
- De vuelta en la fachada en esta ocasión solo se encargara de
devolver al servidor web la información enviada por el backend, actuando
como una especie de puente de comunicación entre los 2.
- El servidor web desplegara en texto plano los resultados, es decir, si
la llave se creo u obtuvo de forma exitosa o si fue editada,mostrando 
ahora el nuevo valor adquirido.

## Como correr el programa

- Primero hay que descargar el repositorio en el computador local
- posterior a esto hay que iniciar el programa de java, esto se puede realizar 
mediante un IDE que permita la funncionalidad de "Run Java" en el programa, en caso contrario
otra alternativa es utilizar el siguiente comando desde una terminal ubicada 
en los archivos del ejercicio:
```
Java -cp target/classes com.mycompany.parcial
```
- Una vez inicializado deberia verse en la terminal el siguiente mensaje:
![Inicio servidor](/images/inicio.png)

- Ahora en un buscador web digitamos el siguiente enlace:

```
http://localhost:5000
```
**Ejemplo:**
![Enlace](/images/enlace.png)

El cual devolvera el siguiente mensaje en texto plano:

![Mensaje](/images/mensaje.png)

Esto se debe a que no se ha digitado un valor de llave a crear o buscar, por lo
cual el programa no sabe como reaccionar ante esto y despliega ese mensaje, es
decir, hay conexion pero no hay algo que hacer al respecto.

- Para dar instrucciones con respecto a que llaves utilizara y bajo que metodo, 
debe incluir la ruta en la dirección, de la siguiente forma:

**Crear o llamar una llave**
```
http://localhost:5000/getKey?key=[identificador de la llave]&value=[valor presente en la llave]
```

**Editar llave**
```
http://localhost:5000/setKey?key=[identificador de la llave]&value=[nuevo valor en la llave]
```






