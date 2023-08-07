## Estado y Comportamiento
---V
## Clases
Una clase será la "plantilla" a partir de la cual se *instanciará* una *clase* de **objetos**.  
Al trabajar en el código estaremos trabajando con clases. Pero al iniciar la aplicación se estará trabajando con objetos.
---V
## Objetos
Los objetos son **instancias** de una clase. Es decir, será la ocurrencia o realización concreta de una clase.  
Los objetos se crearán con el **estado y el comportamiento** definido en la clase a partir de la cual se instanciaron.
---V
## Estado
El estado de un objeto refiere a su **conjunto de atributos** o propiedades que describen su condición o datos.
---V
## Atributos
Un atributo almacena información sobre las características de un objeto en un momento determinado.  
Ej: El objeto perro podría tener los atributos raza, peso, edad y nombre. Sin embargo, la edad y el peso son atributos que variarán en distintos puntos del tiempo. 

Los valores correspondientes a los atributos se almacenan en **variables de instancia**.
---V
## Variables de instancia
Son variables declaradas dentro de una clase que harán referencia a los atributos de sus objetos. Cuando se instancie un objeto de la clase, estas variables se inicializarán con valores concretos que luego pueden ser modificados. 
---V
## Comportamiento
El comportamiento de un objeto refiere al **conjunto de acciones o métodos** que puede realizar.
---V
## Métodos
Los métodos es un objeto definen qué puede hacer o cómo se puede comunicar con otros objetos.  
Almacenarán un conjunto de sentencias, pueden tomar parámetros y devolver cierto tipo de dato, tal como lo haría una función o procedimiento en el paradigma imperativo.
---V
## Mensajes
En POO no llamamos a funciones, sino que enviamos mensajes a objetos.  
Un mensaje es una **petición a un objeto de que haga algo**.

```java
//Le enviamos al objeto almacenado en la variable "miPerro" un mensaje de nombre "ladrar()"
miPerro.ladrar();
```
 Le pasamos al objeto "miPerro" el mensaje "ladrar()" y esperamos que encuentre dentro de su comportamiento la implementación de un método con el mismo nombre. Si no la encuentra tendremos un error.
