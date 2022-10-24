# Object Oriented Programming

- [Object Oriented Programming](#object-oriented-programming)
  - [Que es OOP?](#que-es-oop)
    - [Que son las clases/objetos?](#que-son-las-clasesobjetos)
  - [Clases y Objetos em Java](#clases-y-objetos-em-java)
    - [Creacion de clases](#creacion-de-clases)
    - [Creacion de Objetos](#creacion-de-objetos)
    - [Uso multiple de clases](#uso-multiple-de-clases)
  - [Java Class Attributes](#java-class-attributes)
    - [Atributos en Java](#atributos-en-java)
    - [Aceso a los atributos](#aceso-a-los-atributos)
    - [Modificar atributos](#modificar-atributos)
  - [Java Class Methods](#java-class-methods)
    - [Metodos en Java](#metodos-en-java)
    - [Metodos Publicos vs Estaticos](#metodos-publicos-vs-estaticos)
  - [Java Constructors](#java-constructors)
    - [Constructores en Java](#constructores-en-java)
    - [Parametros del contructor](#parametros-del-contructor)
  - [Java Modifiers](#java-modifiers)
    - [Modifiers/Modificadores](#modifiersmodificadores)
    - [Access Modifiers](#access-modifiers)
    - [Non-Access Modifiers](#non-access-modifiers)
    - [Final, Static y Abstract](#final-static-y-abstract)
  - [Java Encapsulation](#java-encapsulation)
    - [Encapsulación.](#encapsulación)
    - [Get y Set](#get-y-set)
    - [Beneficios de encapsular](#beneficios-de-encapsular)
  - [Java Packages](#java-packages)
    - [Java Packages & API](#java-packages--api)
    - [Built-in Packages](#built-in-packages)
    - [Importar una clase](#importar-una-clase)
    - [Importar un paquete](#importar-un-paquete)
    - [User-defined Packages](#user-defined-packages)
  - [Java Herencia](#java-herencia)
    - [Java Inheritance (Subclases y Superclases)](#java-inheritance-subclases-y-superclases)
    - [Por que ocupar "Herencia"?](#por-que-ocupar-herencia)
    - [Palabra Clave `final`](#palabra-clave-final)
  - [Polimorfismo](#polimorfismo)
    - [Polimorfismo en Java](#polimorfismo-en-java)
  - [Java Inner Classes](#java-inner-classes)
    - [CLases Internas en Java](#clases-internas-en-java)
  - [Java Exceptions](#java-exceptions)
    - [Excepciones en Java](#excepciones-en-java)
    - [Java try and catch](#java-try-and-catch)
    - [Finally](#finally)
    - [`throw` Keyword](#throw-keyword)
---
## Que es OOP?
- **Programacion Procedural**: crear metodos o operaciones en base a datos.
- **Object Oriented Programming**: creacion de objetos que contienen ambos, datos y metodos.

**Beneficios**: Facil de ejecutar, estructura clara, DRY "Don't Repeat Yourself" code haciendo mas facil su mantencion, modificacion y eventual debugging

>**Tip:** "Don't Repeat Yourself" (DRY) o "No te repetitas", consiste en reducir la repeticion de codigo. Extrayendo los codigod comunes en la aplicacion y colocarlos en un solo lugar y reutilizarlos en lugar de repetirlos.
### Que son las clases/objetos?
Clases y objetos son los dos aspectos principales de la programacion orientada a objeto.

>Una clase es una plantilla de objetos y un objeto es una instancia de una clase. Cuando se crean Objetos individuales, heredan todas los atributos y metodos de la clase.

| Clase | Objeto |
| ----- | ------ |
| Auto  | Volvo  |
|       | Audi   |
|       | Toyota |

---
## Clases y Objetos em Java
Java es un lenguaje orientado al objeto.

Todo en java esta asociado a clases y objetos, junto con sus atributos y metodos. Por enemplo: En la vida real un auto es un objeto, y este auto tiene **atributos** los cuales pueden ser, color, marca, al igual tiene **metodos** como, manejar, frenar...

Una clase es como un constructor de objetos, o una "base" para su creacion.

- Clase: Una clase es una plantilla para los objetos
- Objeto: Es una instancia a una clase, al crear un objeto se heredan todas los atributos (variables) y metodos de la clase.

### Creacion de clases
Para crear una clase se utilza la palabra reservada: `class` Una clase siempre debe comenzar con una primera letra mayúscula, y que el nombre del archivo java debe coincidir con el nombre de la clase.
Example:
>Creacion de clase llamada "`Main`" con una variable x:
```java
public class Main {
  int x = 5;
}
```

### Creacion de Objetos
Para crear un objeto necesitamos, especificar el nombre de la clase `clase`, seguido del nombre del objeto y utilizando la palabra clave `new`.

Se pueden crear multiples objetos en una clase y tratarlos.
>Ejemplo: Creacion de objeto llamado `myObj` y impresion del valor de x:
```java
public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj1 = new Main();  // Object 1
    Main myObj2 = new Main();  // Object 2
    System.out.println(myObj1.x);
    System.out.println(myObj2.x);
  }
}
```
### Uso multiple de clases
También se puede crear un objeto de una clase y acceder a él en otra clase. Esto se utiliza a menudo para una mejor organización de las clases (una clase tiene todos los atributos y métodos, mientras que la otra clase contiene el método `main()` (código a ejecutar)).

Recuerda que el nombre del archivo java debe coincidir con el nombre de la clase. En este ejemplo, hemos creado dos archivos en el mismo directorio/carpeta:
- Main.java
- Segundo.java

```java
// Main.java
public class Main {
  int x = 5;
}
```
```java
// Second.java
class Second {
  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```
```cmd
#Debemos de compilar ambos archivos
C:\Users\Your Name>javac Main.java
C:\Users\Your Name>javac Second.java

#Ejecutamos Second.java
C:\Users\Your Name>java Second

#Output:
5
```
---
## Java Class Attributes
### Atributos en Java
Cuando hablamos de un objeto en OOP, las "variables" de cada objeto las llamamos **Atributos**, en otras palabras, los atributos son las variables de una clase.

Podemos espeficar tantos atributos como queramos.
>Otro termino para referirse a los atributos es campos o **filds**
>Clase llamada "`Main`" con dos atributos: `x` y `y`:
```java
public class Main {
  int x = 5;
  int y = 3;
}
```
### Aceso a los atributos
Para acceder a los atributos de un objeto lo hacemos mediante la sintaxis (`.`):

>Ejemplo: Creacion de objeto "`myObjet`" y imprimir el valor de `x`:
```java
public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```
### Modificar atributos
Podemos modificar los atributos de un objeto o sobreescribirlos, en el caso de que sean modificables.

En caso contrario si nosotros queremos que una variable no sea modificable la asignamos como `final`.
>La palabra clave `final` es llamada un **modifier** o **modificador**.

En caso de tener multiples objetos podemos modificar o acceder a cada uno individualmente, sin afectar a los demas.
```java
public class Main {
  final int x = 10;
  int y = 20;

  public static void main(String[] args) {
    Main myObj = new Main();
    myObj.x = 25; // will generate an error: cannot assign a value to a final variable
    myObj.y = 15;
    System.out.println(myObj.y); //imprimira el nuevo valor de y
  }
}
```
---
## Java Class Methods
### Metodos en Java
Los metodos los declaramos dentro de una clase y estos se utilizan para realizar ciertas acciones.

Para llamar un metodo podemos o hacerlo directamente en una clase o llamarlo mediante el nombre del objeto `.` el nombre del metodo, en ambos casos escribimos el nombre del metodo seguido de `()` y un `;` 

```java
public class Main {
  static void miMetodo() {
    Sytem.out.println("llamada del metodo");
  }

  public void miMetodoSaluda() {
    Sytem.out.println("Hola Mundo!");
  }

  public static void main(String[] args) {
    Main myObj = new Main();
    miMetodo(); //al ser un metodo estatico podemos acceder a el sin crear un objeto.
    miObjeto.miMetodoSaluda(); //llamamos al metodo mediante el objeto
  }
}
```

### Metodos Publicos vs Estaticos
A menudo en Java tenemos metodos o atributos que pueden ser **publicos** o **estaticos**:
- `public` Los métodos públicos solo pueden ser llamados mediante la creación y acceso de objetos.
- `static` Los métodos estáticos se pueden llamar sin crear objetos.

```java
// Creacion de la clase main
public class Main {
  int x;  // Creacion del atributo x
  // Constructor de la clase Main
  public Main() {
    x = 5;  // Asigna el valor incial del atributo x;
  }
  public static void main(String[] args) {
    Main miObj = new Main(); //Crea un objeto de la clase main (este llama al constructor)
    System.out.println(miObj.x); // Imprime el valor de x
  }
}
```
Es una buena práctica crear un objeto de una clase y acceder a él en otra clase.

> **Tener en mente**
- El punto `.` se utiliza para acceder a los atributos y métodos del objeto.
- Para llamar a un método en Java, escriba el nombre del método seguido de un conjunto de paréntesis `()`, seguido de un punto y coma (`;`).
- Una clase debe coincidir con el nombre del archivo (Main and Main.java).
  
---
## Java Constructors
### Constructores en Java
Un constructor en Java es un **método especial** que se utiliza para inicializar objetos. El constructor es llamado cuando se crea un objeto de una clase. Se puede utilizar para establecer los valores iniciales de los atributos del objeto.

 - El metodo constructor debe tener el mismo nombre que la clase y no debe tener tipo retorno (no incluir el `void`).
 - El constructor es llamado cuando el objeto es creado.
 - Todas las clases tienen un constructor por defecto, en caso de no crearlo nosotros java lo hace automaticamente sin enmbargo no podremos declarar los valores iniciales para nuestros atributos

### Parametros del contructor
Los metodos constructores pueden contener Parametros de entrada, y ser usado para inicializar los atributos.
Al llamar al constructor pasamos el parameto al constructor y pasar la cantidad de parametros que nosotros queramos.

- Para asignar al atributo una variable con el mismo nombre podemos ocupar la palabra clave `this.` La cual hara referencia al objeto actual y a sus atributos.
```java
public class Main {
  int x;

  public Main(int y) {
    this.x = y; //asinga el valor recibido y y lo asina a x
  }

  public static void main(String[] args) {
    Main myObj = new Main(5);
    System.out.println(myObj.x);
  }
}
```

---
## Java Modifiers
### Modifiers/Modificadores
Como ya utilizamos recurrentemente la palabra clave `public` 
Que es la palabra clave `public`?
La palabra clave `public` es un **access modifier** (modificador de acceso) es decir que es el encargado de establecer el nivel de acceso de clases, atributos, metodos y constructores.
Los modificadores se dividen en 2 grupos:
  - **Access Modifiers** - Aquellos que controlan el nivel de acceso
  - **Non-Access Modifiers** - No controlan el nivel de acceso pero proveen de otras funcionalidades

**Syntaxis**: Access + Non-Access + Type + Name(Parameters);

### Access Modifiers
#### Clases <!-- omit in toc -->
  > - `public` - Esta clase es accesible por cualquier otra clase
  > - *default* - La clase solo es accesible por clases del mismo paquete. Es usado cuando no se especifica el modificador.
#### Atributos, Metodos y Constructores <!-- omit in toc -->
  > - `public` - el codigo es accesible para todas las clases
  > - `private` - el codigo es solo accesible en la clase declarada
  > - *default* - el codigo es accesible solo en el mismo paquete. Es usado cuando no se especifica el modificador.
  > - `protected` - El codigo es accesible en el mismo paquete y **subclases**

### Non-Access Modifiers
#### Clases <!-- omit in toc -->
  > - `final` - la clase no podra ser heredada por otras clases
  > - `abstract` - la clase no puede ser usada para crear objetos
#### Atributos y Metodos <!-- omit in toc -->
  > - `final` - atributos y metodos no pueden ser sobreescritos/modificados
  > - `static` - atributos y metodos pertenecen a la clase, en lugar del abstract
  > - `abstract` - solo podran ser usadas en una clase abstracta, y solo usada en metodos. El metodo no debe tener un cuerpo, por ejemplo: **abstract void aña();** El cuerpo es proporcionado por la subclase.
  > - `transient` - atributos y metodos son omitidos cuando al serializar un objeto que los contiene
  > - `synchronized` - medotos solo pueden ser accedidos por un hilo a la vez
  > - `volatile` - el valor de un atributo no se almacena en el cache de forma local, y siempre es leido de la "memoria principal"
### Final, Static y Abstract
`Final` - Si no queremos tener la capacidad de sobreescribir valores de atributos ya existentes
```java
  final int x = 10;
```
`Static` - Un metodo estatico significa que se puede acceder a el sin crear un objeto de la clase, a diferencia de los publicos
```java
  static void helloWorld() {
    System.out.println("Hello World!!!");
  }
  //Puede ser llamado como helloWorld() ya que no necesario crear un objeto para llamarlo
```
`Abstract` - Un metodo abstracto pertence a una clase abstracta y no tiene cuerpo. El cuerpo lo proporcionara la subclase.

Ejemplo: Clase abstracta `Hola` que extiende a la subclase `Mundo`, asigna el texto **"Hola Mundo"** a la variable protegida y la imprime.
```java
abstract class Hola {
  protected String texto;
  public abstract void saludar(); //metodo abstracto
}
//Subclase (heredada de la clase hola)
class Mundo extends Hola {
  public void saludar() { //cuerpo del metodo abstracto
    texto = "Hola Mundo";
    System.out.println(texto);
  }
}
```
---
## Java Encapsulation
### Encapsulación.
Se podria definir **encapsulacion** como, asegurarse de que los datos "sensibles" esten ocultos a los usuarios.
Para lograrlo:
  - Declarar atributos de clase en `privado`
  - Proveer de public get y set metodos para acceder y actualizar los valores de los atributos `privados`

### Get y Set
Como vimos las variables `privadas` solo se pueden acceder dentro de la misma clase.

Sin embargo, podemos acceder a ellos mediante metodos publicos **get** y **set**.
Los metodos `get` retornan el valor de la variable, y los metodos `set` establecen el valor.

La sintaxis para ambos es comenzar con `get` o `set`, seguido del nombre de la variable, con la primera letra en mayuscula.
```java
public class Person {
  private String name; // private = restricted access
  // Getter
  public String getName() {
    return name;
  }
  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}
```
### Beneficios de encapsular
  - Mejor control de los arubutos y metodos dentro de la clase
  - Encapsular puede ser muy util en clases que solo esten hechas para lectura **solo-lectura** (`get` method) o **solo-escritura** (`set` method)
  - Flexibilidad: Al programar podemos cambiar una parte del codigo sin afectar otras partes.
  - Incrementar la seguridad de los datos.
  
---
## Java Packages
### Java Packages & API
Un paquete en java se utiliza para agrupar clases relacionadas. Se podria decir que es **una carpeta en un directorio de archivos**. Utilizamos los paquetes para evitar conflictos de nombre y tener un codigo mas facil de mantener. Los paquetes se dividen en dos categorias:
 - Built-in Packages (paquetes de los API de Java)
 - User-defined Packages (Paquetes creados por el usuario)
### Built-in Packages
La API de Java es una libreria de clases preescritas, de uso libre, incluidas en el entorno de desarrollo de java.
Las librerias contienen componentes para la gestion de entrada, la programacion de bases de datos, etc. [Revisar Java API](#https://docs.oracle.com/javase/8/docs/api/)

La libreria esta dividida en **Paquetes** y **Clases**. Esto significa que se puede importar una sola clase (junto con sus metodos y atributos), o un paquete completo que contenga todas las clases pertenecientes al paquete en especifico.

Pars importar una clase o paquete desde una libreria, usamos la palabra clave `import`:

```java
import package.name.Class;   // Importar una sola clase
import package.name.*;   // Importar todo un paquete
```

### Importar una clase
Si queremos usar una clase en especifico, por ejemplo, la clase `Scanner`, **usada para la entrada del Usuario**.

```java
import java.util.Scanner;
```
En el ejemplo de arriba, `java.util` es el paquete, mientras que `Scanner` es la clase del paquete `java.util`.

Para utilizar la clase `Scanner`, se debe crear un objeto de la clase y utilizar cualuqiera de sus metodos disponibles que se encuentran en su documentacion. En el siguiente ejemplo utilizamos el metodo `nextLine()`, que se utiliza para leer una linea completa:
```java
import java.util.Scanner;
class MyClass {
  public static void main(String[] args) {
    Scanner myObj = new Scanner(System.in);
    System.out.println("Enter username");

    String userName = myObj.nextLine();
    System.out.println("Username is: " + userName);
  }
}
```

### Importar un paquete
Hay muchos paquetes a elegir, junto con diversos metodos utiles al momento de programar, por ejemplo del paquete `java.util` tambien contiene utilidades para fecha y hora, generar numeros aleatorios, etc.

Para importar un paquete completo, se debe terminar la frase con un asterisco (`*`).
```java
import java.util.*;
```
### User-defined Packages
User-defined Packages o Paquetes creados por el usuario).
Para crear nuestro propio paquete, debemos de comprender como JAVA se utiliza el sistema de directorios de archivos de almacenamiento.

``` java
└── root
  └── mypack
    └── MyPackageClass.java
```
Para crear nuestro propio paquete, usamos la palabra clave `package`:
> MyPackageClass.java
```java
package mypack;
class MyPackageClass {
  public static void main(String[] args) {
    System.out.println("This is my package!");
  }
}
```
Guardamos el archivo como **MyPackageClass.java** y compilamos
```cmd
C:\Users\Your Name>javac MyPackageClass.java
C:\Users\Your Name>javac -d . MyPackageClass.java
```
Cuando el paquete este compilado, una nueva carpeta sera creada y llamada "mypack".

Para ejecutar **MyPackageClass.java** escribimos y esta sera ejecutada.

```cmd
C:\Users\Your Name>java mypack.MyPackageClass
This is my package!
```
## Java Herencia
### Java Inheritance (Subclases y Superclases)
En java, es posible heredar atrubutos y metodos de una clase a otra, a esto lo llamamos **"Herencia"**, la cual esta dividida en dos categorias:
 - **subclase** (hijo) - la clase hereda desde otra clase
 - **superclase** (padre) - la clase de la cual es heredada

Para heredar desde una clase usamos la palabra clave `extends`.
> Ejemplo: Clase `Auto` (subclase), hereda atributos y metodos de la clase `Vehiculo` (superclase):
```java
class Vehiculo {
  protected String marca = "Ford";  //atributo vehiculo
  public void bocina() {  //metodo vehiculo
    System.out.println("Piii, Pii!");
  }
}

class Auto extends Vehiculo {
  private String modeloNombre = "Mustang";  //atributo auto
  public void autoMarca(){
    System.out.println(marca + " " + modeloNombre); //metodo que imprime la marca heredada de vehiculo y el modelo del auto.
  }
  public static void main(String[] args) {
    Auto auto = new Auto();
    auto.bocina(); //imprime "Piii, Pii!"
    auto.autoMarca(); //imprime los atrubutos marca y modeloNombre: "Ford Mustang".
  }
}
```
>Como vimos anteriormente, usamos el modificador `protected` en el atributo marca, para de esta manera poder acceder a el sin que pueda acceder el usuario, en aso contrario si usasemos `private` la subclase auto no tendria acceso a esta.

### Por que ocupar "Herencia"?
Es util para la reutilizacion del codigo (DRY "Don't Repeat Yourself") y mantener un codigo limpio manteniendo una estructura clara haciendo mas facil su mantencion, modificacion y eventual debugging.

### Palabra Clave `final`
En el caso de que no queramos que otras clases hereden a nuestra clase, usamos la palabra `final`.
H~2~O
>Si intentamos acceder a ella siendo una clase `final`, Java nos generara un error:
```java
final class Vehiculo {
  ...
}

class Auto extends Vehiculo {
  ...
}
```
>El resultado sera algo asi:
```cmd
Main.java:9: error: cannot inherit from final Vehicle
class Main extends Vehiculo {
                  ^
1 error)
```
---
## Polimorfismo
### Polimorfismo en Java
Polimorfismo se define como "muchas formas", y se produce cuando tenemos muchas clases relacionadas entre si por herencia.

Como vimos anteriormente la **Herencia** nos permite heredar atributos y metodos de otra clase. **Polimorfismo** usa aquellos metodos para realizar diversas tareas. Permitiendonos hacer una misma accion de diversas maneras.

Por ejemplo, pensemos en una super clase llamada `Animal` que tiene un metodo llamado `sonidoAnimal()`. Las sublcases de `Animal` podrian ser Cerdos, Gatos, Perros, Aves, etc y que cada uno de ellos tenga su propia implementacion de un sonido animal (el cerdo oink, el gato miau, etc);
>usamos la palabra clave `extends` para heredar desde una clase
```java
class Animal {
  public void sonidoAnimal() {
    System.out.println("El animal hace sonido");
  }
}

class Chanchito extends Animal {
  public void sonidoAnimal() {
    System.out.println("The Chanchito says: oink oink");
  }
}

class Perro extends Animal {
  public void sonidoAnimal() {
    System.out.println("The Perro says: guau guau");
  }
}

class Main {
  public static void main(String[] args) {
    //creamos objeto Animal, Chanchito y Perro
    Animal miAnimal = new Animal();
    Animal miChanchito = new Chanchito();
    Animal miPerro = new Perro();
    //llamamos al medoto sonidoAnimal de cada uno
    miAnimal.sonidoAnimal();
    miChanchito.sonidoAnimal();
    miPerro.sonidoAnimal();
  }
}
```
---
## Java Inner Classes
### CLases Internas en Java
En java es posible anidar clases (Una clase dentro de otra). El proposito de anidar clases es agrupar las clases y hacer que estas sean mas legibles y mantenible.

Para acceder a una clase interior, se debe crear un objeto de la clase exterior luego crear un objeto de la clase interior:
> Ejemplo:


## Java Exceptions
### Excepciones en Java
Cuando ejecutamos un codigo en Java, diferentes errores pueden ocurrir, debido a errores de codificacion, entrada u otros.

Cuando se produce un error, Java normalmente se detiene y genera un mensaje de error. El termino tecnico para esto es: Java lanzara una **Excepcion** (lanzara un error).
### Java try and catch
La palabra clave `try` permite definir un bloque de codigo para que se compruebe si hay errores mientras se ejecuta.

La palabra `catch` permite definir un bloque de codigo que se ejecutara si se produce un error en el bloque `try`.

La palabra `try` y `catch` vienen en pares.

```java
try {
  // Bloque de codigo a probar
}
catch(Exception e) {
  // Bloque de codigo para gestionar el error
}
```

Cosideramos el siguiente ejemplo:
```java
public class Main {
  public static void main(String[ ] args) {
    int[] myNumbers = {1, 2, 3};
    System.out.println(myNumbers[10]); // error!
  }
}
```
El output seria algo asi:
```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 10
        at Main.main(Main.java:4)
```
En caso de ocurrir, podriamos ocupar `try...catch`para atrapar el error y ejecutar algun codigo para manejarlo.
```java
public class Main {
  public static void main(String[ ] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    }
  }
}
```
> Output:
```
Something went wrong.
```

### Finally
La palabra clave `finally` permite ejecutar codigo despues del `try...catch`, independiente del resultado:

```java
public class Main {
  public static void main(String[] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    } finally {
      System.out.println("The 'try catch' is finished.");
    }
  }
}
```
>Output
```
Something went wrong.
The 'try catch' is finished.
```
### `throw` Keyword
La palabra clave `throw` permite crear un error personalizado.

La sentencia `throw` se utiliza junto con un tipo de **excepcion**. Hay muchas tipos de excepcion disponibles en Java: `ArithmeticException`, `FileNotFoundException`, `ArrayIndexOutOfBoundsException`, `SecurityException`, etc.

> Lanzar una excepcion si la **edad** es menos a 18 (imprimir "Acceso denegado!"), en caso contrario imprimir "Acceso concedido".
```java
public class Main {
  static void checkAge(int age) {
    if (age < 18) {
      throw new ArithmeticException("Access denied - You must be at least 18 years old.");
    }
    else {
      System.out.println("Access granted - You are old enough!");
    }
  }

  public static void main(String[] args) {
    checkAge(15); // Set age to 15 (which is below 18...)
  }
}
```
>Output:
```
Exception in thread "main" java.lang.ArithmeticException: Access denied - You must be at least 18 years old.
        at Main.checkAge(Main.java:4)
        at Main.main(Main.java:12)
```
---