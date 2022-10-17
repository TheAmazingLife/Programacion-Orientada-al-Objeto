Object Oriented Programming

Programacion Procedural: crear metodos o operaciones en la Data
Object Oriented Programming: creacion de objetos que contienen ambos, data y metodos

Beneficios: Facil de ejecutar, estructura clara, DRY "Don't Repeat Yourself" code haciendo mas facil su mantencion, modificacion y eventual debugging

~Classes/Objects~
Clase: Una clase es una plantilla para los objetos
Objeto:
Es una instancia a una clase
Al crear un objeto se heredan todas los atributos(variables) y metodos de la clase.

Un auto es un objeto, y este auto tiene atributos los cuales pueden ser, color, marca, al igual tiene metodos como, manejar, frenar...

Creacion de clases
Para crear una clase se utilza la palabra reservada: class
Una clase siempre debe comenzar con una primera letra mayúscula, y que el nombre del archivo java debe coincidir con el nombre de la clase.
Example:
Create a class named *Main* with a variable x:
public class Main {
  int x = 5;
}

Creacion de Objetos
Para crear un objeto necesitamos, especificar el nombre de la clase *clase*, seguido del nombre del objeto y utilizando la palabra clave *new*.
Se pueden crear multiples objetos en una clase y tratarlos.
Example
Create an object called *myObj* and print the value of x:
public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj1 = new Main();  // Object 1
    Main myObj2 = new Main();  // Object 2
    System.out.println(myObj1.x);
    System.out.println(myObj2.x);
  }
}

También se puede crear un objeto de una clase y acceder a él en otra clase. Esto se utiliza a menudo para una mejor organización de las clases (una clase tiene todos los atributos y métodos, mientras que la otra clase contiene el método main() (código a ejecutar)).

Recuerda que el nombre del archivo java debe coincidir con el nombre de la clase. En este ejemplo, hemos creado dos archivos en el mismo directorio/carpeta:

Main.java
Segundo.java

Main.java
public class Main {
  int x = 5;
}
Second.java
class Second {
  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}

~Java Class Attributes~
Cuando hablamos de un objeto en OOP, las *variables* de cada objeto las llamamos Atributos, en otras palabras, los atributos son las variables de una clase
(otro termino para referirse a los atributos es campos o *filds*)
Podemos espeficar tantos atributos como queramos.

Aceso a los atributos
Para acceder a los atributos de un objeto lo hacemos mediante la sintaxis (.)

Modificar atributos
Podemos modificar los atributos de un objeto o sobreescribirlos, en el caso de que sean modificables.
En caso contrario si nosotros queremos que una variable no sea modificable la asignamos como *final*.
final int edad = 20;
(La palabra clave *final* es llamada un *modifier*)

En caso de tener multiples objetos podemos modificar o acceder a cada uno individualmente, sin afectar a los demas

~Java Class Methods~
Los metodos los declaramos dentro de una clase y estos se utilizan para realizar ciertas acciones
Para llamar un metodo podemos o hacerlo directamente en una clase o llamarlo mediante el nombre del objeto (.) el nombre del metodo, en ambos casos escribimos el nombre del metodo seguido de () y un ; 

Metodos Publicos vs Estaticos
A menudo en Java tenemos metodos o atributos que pueden ser publicos o estaticos
*public* Los métodos públicos deben ser llamados por la creación de objetos 
*static* Los métodos estáticos se pueden llamar sin crear objetos

Es una buena práctica crear un objeto de una clase y acceder a él en otra clase.

*Tener en mente*
El punto (.) se utiliza para acceder a los atributos y métodos del objeto.
Para llamar a un método en Java, escriba el nombre del método seguido de un conjunto de paréntesis (), seguido de un punto y coma (;).
A class must have a matching filename (Main and Main.java).

~Java Constructors~
Un constructor en Java es un método especial que se utiliza para inicializar objetos. El constructor es llamado cuando se crea un objeto de una clase. Se puede utilizar para establecer los valores iniciales de los atributos del objeto.

El metodo constructor debe tener el mismo nombre que la clase y no debe tener tipo retorno (no incluir el *void*)
El constructor es llamado cuando el objeto es creado
Todas las clases tienen un constructor por defecto, en caso de no crearlo nosotros java lo hace automaticamente sin enmbargo no podremos declarar los valores iniciales para nuestros atributos

Parametros del contructor
Los metodos constructores pueden contener Parametros de entrada, y ser usado para inicializar los atributos.
Al llamar al constructor pasamos el parameto al constructor y pasar la cantidad de parametros que nosotros queramos

Para asignar al atributo una variable con el mismo nombre podemos ocupar la palabra clave "this."
La cual hara referencia al objeto actual y a sus atributos

~Java Modifiers~
Modifiers/Modificadores
Como ya utilizamos recurrentemente la palabra clave "public" 
Que es la palabra clave "public"
La palabra clave "public" es un *access modifier* (modificador de acceso) es decir que es el encargado de establecer el nivel de acceso de clases, atributos, metodos y constructores.
Los modificadores se dividen en 2 grupos:
  Access Modifiers - Aquellos que controlan el nivel de acceso
  Non-Access Modifiers - No controlan el nivel de acceso pero proveen de otras funcionalidades

Syntaxis: Access + Non-Access + Type + Name(Parameters);

*Access Modifiers*
Clases
  public - Esta clase es accesible por cualquier otra clase
  default - La clase solo es accesible por clases del mismo paquete. Es usado cuando no se especifica el modificador.
Atributos, Metodos y Constructores
  public - el codigo es accesible para todas las clases
  private - el codigo es solo accesible en la clase declarada
  default - el codigo es accesible solo en el mismo paquete. Es usado cuando no se especifica el modificador.
  protected - El codigo es accesible en el mismo paquete y *subclases*

*Non-Access Modifiers*
Clases
  final - la clase no podra ser heredada por otras clases
  abstract - la clase no puede ser usada para crear objetos
Atributos y Metodos
  final - atributos y metodos no pueden ser sobreescritos/modificados
  static - atributos y metodos pertenecen a la clase, en lugar del abstract - solo podran ser usadas en una clase abstracta, y solo usada en metodos. El metodo no debe tener un cuerpo, por ejemplo:
  abstract void aña(); El cuerpo es proporcionado por la subclase.
  transient - atributos y metodos son omitidos cuando al serializar un objeto que los contiene
  synchronized - medotos solo pueden ser accedidos por un hilo a la vez
  volatile - el valor de un atributo no se almacena en el cache de forma local, y siempre es leido de la "memoria principal"

Final - Si no queremos tener la capacidad de sobreescribir valores de atributos ya existentes, ejemplo: final int x = 10;
Static - Un metodo estatico significa que se puede acceder a el sin crear un objeto de la clase, a diferencia de los publicos
Abstract - Un metodo abstracto pertence a una clase abstracta y no tiene cuerpo. El cuerpo lo proporcionara la subclase.

~Encapsulation~
Encapsulación.
Se podria definir encapsulacion como, asegurarse de que los datos "sensibles" esten ocultos a los usuarios.
Para lograrlo:
  *Declarar atributos de clase en privado
  *Proveer de public get y set metodos para acceder y actualizar los valores de los atriobutos privados

Get y Set
Como vimos las variables privadas solo se pueden acceder dentro de la misma clase.
Sin embargo, podemos acceder a ellos mediante metodos publicos get y set.
Los metodos get retornan el valor de la variable, y los metodos set establecen el valor.

La sintaxis para ambos es comenzar con get o set, seguido del nombre de la variable, con la primera letra en mayuscula.
`public class Person {
  private String name; // private = restricted access

  // Getter
  public String getName() {
    return name;
  }

  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}`
H~2~O
