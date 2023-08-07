## Características del paradigma orientado a objetos
---V
## Herencia
Una clase puede heredar el *estado y comportamiento* de una **superclase**, así como puede ser la que le brinda lo mismo a una **subclase**.

Asimismo, una subclase puede **sobreescribir** comportamiento heredado, siempre y cuando se mantengan las *mismas firmas* de los métodos.

Firma: nombre y parámetros que recibe un método  
Ej: ladrar(cantVeces) 
---V
## Herencia - ¿Para qué?
Mediante la herencia podemos reutilizar código idéntico entre múltiples clases y establecer una relación jerárquica que facilita la comprensión del diseño de la aplicación.  

También facilita la extensión de funcionalidades, ya que ante nuevos requisitos en nuestra aplicación podemos extender una nueva subclase de clases ya existentes, en vez de meter mano en el código que ya hicimos y funciona.
---V
## Herencia - Ejemplo
```java
//La clase Animal será una superclase de Perro
class Animal {
    private String especie;

    public void hacerSonido() {
        System.out.println("Sonido de animal");
    }
}

//La subclase Perro recibe el método hacerSonido() pero lo sobreescribe para modificar su implementación
class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Guau!"); //Implementación sobreescrita
    }
```
---V
## Abstracción
La abstracción nos permite simplificar clases y enfocarse sólo en declarar sus atributos y comportamientos, pero sin especificar su implementación.

Esto nos permite modelar de forma más sencilla nuestras superclases y establecer un contrato de lo que se debe cumplir en sus subclases, pero sin definir cómo lo harán.
---V
## Clases abstractas
Hasta ahora vimos métodos que traen consigo su implementación, es decir, **métodos concretos**. Pero existe otro tipo de métodos *sin implementación*: los **métodos abstractos**.  

Si una clase tiene como mínimo un método abstracto, entonces es una **clase abstracta**. De lo contrario, si no posee ningún método abstracto, es una **clase concreta**.
---V
## Clases abstractas - Ejemplo
```java
abstract class Animal {
    private String nombre;

    // Método abstracto para ser implementado por subclases
    abstract void hacerSonido();
}

class Dog extends Animal {

    //Hereda el método abstracto, pero lo sobreescribe para agregarle implementación
    @Override
    void hacerSonido() {
        System.out.println("Guau!");
    }
}
```
---V
## Polimorfismo
Los objetos de diferentes clases pueden ser tratados como objetos de una misma superclase.

Esto permite escribir código que hace referencia a una clase en específico, pero que también funcionará si en su lugar se utilizan objetos correspondientes a cualquiera de sus subclases.
---V
## Polimorfismo - Interfaz
Una **interfaz** es el conjunto de métodos que un objeto posee (o visto desde afuera, el conjunto de mensajes que un objeto puede comprender).

El polimorfismo nos brinda una *interfaz* unificada para un conjunto de clases, haciendo el código mucho más flexible y extendible.  
---V
## Polimorfismo - ¿Para qué?
Podemos escribir código que funcionará con múltiples clases, ya que a través de la **vinculación dinámica** (o en inglés, dynamic binding) se resolverá en tiempo de ejecución cómo un objeto interpreta el *mensaje* que le enviamos.

Si una subclase es utilizada en lugar de la superclase definida en el código, entenderá los mismos mensajes pero les aplicará su propia implementación.
---V
## Polimorfismo - Ejemplo
```java
class Aplicacion {
    public void ejecutarAplicacion(){
        Animal animal = new Animal();
        animal.hacerSonido()

        //Ahora animal almacena un objeto Gato, subclase de Animal
        Animal animal = new Gato();
        //Esta línea funciona igual!
        animal.hacerSonido();
    }
}


class Gato extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Miau!");
    }
```
---V
## Encapsulamiento
Es un principio que establece que todos los datos y su manipulación (atributos y métodos) se deben contener en unidades llamadas objetos.  
Pero también establece que **la única forma de acceder al estado de un objeto debe ser mediante métodos bien definidos** (getters y setters) y jamás de forma directa.  

Esto facilita el mantenimiento y la modularidad del código.
---V
## Setters y getters
Los métodos para modificar u obtener los atributos de un objeto se llaman por convención "setters" y "getters".

```java
class Perro {
    private String nombre;
    private int edad;

    // Setter para nombre
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    // Getter para nombre
    public String getnombre() {
        return nombre;
    }

    // Setter para edad
    public void setEdad(int edad) {
        if (edad >= 0) {
            this.edad = edad;
        }
    }

    // Getter para edad
    public int getEdad() {
        return edad;
    }
```
---V
## Constructores
Cuando instanciamos un objeto tenemos que inicializar sus variables de instancia. Para esto existen métodos que por convención se llaman "constructores" que se encargan de ello.

Podemos tener múltiples constructores que varían en la cantidad de parámetros que reciben. El lenguaje interpretará según qué parámetros recibe, cuál de todos ellos debe utilizar.
---V
## Constructores - Ejemplo
```java
class Perro {
    private String nombre;
    private int edad;

    // Constructor
    //Por convención se llama igual que la clase
    public Perro(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public Perro(String nombre) {
        this.nombre = nombre;
        this.edad = 0;
    }

    public Perro() {
        this.nombre = Perro sin nombre;
        this.edad = 0;
    }
}
```
