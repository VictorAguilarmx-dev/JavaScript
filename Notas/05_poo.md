# Programación Orientada a Objetos (P.O.O.)

## Índice
- [Prototipos](#prototipos)
- [Herencia](#herencia)
- [Clases](#clases)
- [Métodos estáticos](#métodos-estáticos)
- [Métodos getters y setters](#métodos-getters-y-setters)
***
En POO tenemos 4 conceptos que tenemos que entender

- Clases: Modelo a seguir
- Objetos: Instancia de una clase
  - Atributos: Caracteristica o propiedad del objeto (variables dentro del objeto)
  - Métodos: Accionesque un objeto puede realizar (funciones dentro de un objeto).

## Prototipos
Un **prototipo** es un mecanismo por el cual un objeto puede heredar de un objeto padre atributos y métodos

Gracias a las clases el uso de prototipos ha quedad en desuso.

Dentro de un prototipo tenemos una función que se llama **función constructura**, la cual sólo construiremos una vez, esta nos ayudará a construir un prototipo

Dentro de nuestra función constructura tanto los objetos como los métodos deben de tener un this antes.

La función contructora nos permite crear objetos, por ejemplo:
```javascript
function Animal(nombre, genero) {
    // Atributos
    this.nombre = nombre;
    this.genero = genero;
    // Métodos
    this.sonar = function () {
        console.log("Hago sonidos por que estoy vivo");
    }
}

const snoopy = new Animal("Snoopy", "Macho"),
    lolaBunny = new Animal("Lola Bunny", "Hembra");

console.log(snoopy);
console.log(lolaBunny);
```
Podemos anexar métodos a un prototipo, por ejemplo:
```javascript
function Animal(nombre, genero) {
    // Atributos
    this.nombre = nombre;
    this.genero = genero;
}
    // Métodos
    Animal.prototype.sonar = function () {
        console.log("Hago sonidos por que estoy vivo");
    }

const snoopy = new Animal("Snoopy", "Macho"),
    lolaBunny = new Animal("Lola Bunny", "Hembra");

console.log(snoopy);
console.log(lolaBunny);
```

## Herencia
La **herencia** es la capacidad de heredar caracteristicas de un padre a un hijo. Por ejemplo:

Consideremos la siguiente función constructora
```javascript
function Animal(nombre, genero) {
    this.nombre = nombre;
    this.genero = genero;
}

Animal.prototype.sonar = function () {
    console.log("Hago sonidos por que estoy vivo");
}
Animal.prototype.saludar = function (thisnombre) {
    console.log(`Hola mi nombre es ${this.nombre}`);
}
```

Esta función constructora nos genera un objeto padre llamado Animal con las propiedades nombre y genero y con los métodos sonar saludar. Ahora construiremos un objeto hijo de Animal con la siguiente función constructora.
```javascript
function Perro(nombre, genero, tamanho) {
    this.super = Animal;
    this.super(nombre, genero);
    this.tamanho = tamanho
}

Perro.prototype = new Animal();

Perro.prototype.constructor = Perro;
```

Lo que hacemos en la línea de `Perro.prototype = new Animal();` es crear una nueva instancia del prototipo Animal

Como podemos ver el prototipo padre tiene un método llamada sonar, podemos sobreescribir el método sonar para ‘‘personalizarlo’’ en la instancia Perro
```javascript
Perro.prototype.sonar = function () {
    console.log("Soy un perro y mi sonido es un ladrido");
}
```

También podemos crear métodos para el prototipo hijo que no se encuentren en el protipo padre
```javascript
Perro.prototype.ladrar = function () {
    console.log("Guauuu Guauuu");
}
```

## Clases
A partir del año 2015 JS permite el uso de clases.

Para entender mejor el como definir una clase y como usar la herencia tenemos el siguiente ejemplo:

Primero crearemos una clase padre llamada Animal de la siguiente forma:
```javascript
class Animal {
    // Constructor
    constructor(nombre, genero) {
        this.nombre = nombre;
        this.genero = genero;
    }

    // Métodos
    sonar() {
        console.log("Hago sonidos por que estoy vivo");
    }

    saludar() {
        console.log(`Hola me llamo ${this.nombre}`);
    }
}
```

como podemos ver en el método `constructor(){}` definiremos todas las propiedades de nuestra clase, para definir una propiedad de nuestra clase utilizaremos la palabra reservada this de la siguiente forma:

`this.<nombre_propiedad> = <propiedad>;`

Para definir métodos lo haremos como si fuera una función normal, el único requisito es que esta función esté adentro de la clase y la sintaxis sería la siguiente:

`<nombre_método> () { <lineas_código> }`


Ahora veremos como se utiliza la herencia en clases, para ello definiremos la clase hijo Perro de la siguiente forma:
```javascript
class Perro extends Animal {
    constructor(nombre, genero, tamanho) {
        // Con el método super() se manda a llamar el constructor de la clase padre
        super(nombre, genero);
        this.tamanho = tamanho;
    }

    sonar() {
        console.log("Soy un perro y mi sonido es un ladrido");
    }

    ladrar() {
        console.log("Guauu Guauu!!!");
    }
}
```

Como podemos ver en una clase hijo tenemos que especificar el padre de nuestra clase, esto se hace con la palabra extends, es decir:

`class <nombre_clase_hijo> extends <nombre_clase_padre>`


Al igual que nuestra clase padre nuestra clase hijo tiene un constructor, en el cual definiremos todas las propiedades de nuestra clase, pero como nuestra clase hijo usa las propiedades de nuestra clase padre lo lógico es que podamos llamar al constructor de nuestra clase padre para que le herede las propiedades a nuestra clase hijo, esto se hace con el método super(), este método llamará a las propiedades de nuestra clase padre que queremos heredar a nuestra clase hijo.

Si queremos definir una nueva propiedad en la clase hijo que no esté en la clase padre utilizaremos la misma sintaxis, es decir:
```javascript
this.<nombre_propiedad> = <propiedad>;
```

La definición de métodos en la clase hijo se hacer igual que en la clase padre sólo que no es necesario reescribir los métodos de nuestra clase padre, ya que estos se heredarán automáticamente al especificar el vinculo entre las clases, en cambio podemos sobre escribir un método de la clase padre en la clase hijo volviendo a definir el método, como ejemplo tenemos el método sonar() de nuestras clases padre e hijo.

## Métodos estáticos
Un método estático es un método que se puede ejecutar sin la necesidad de instanciar la clase, estos métodos se definen con la palabra reservada static, por ejemplo:
```javascript
class Perro {
    constructor(nombre, genero, tamanho) {
        this.nombre = nombre;
        this.genero = genero;
        this.tamanho = tamanho;
    }

    sonar() {
        console.log("Hago sonidos por que estoy vivo");
    }

    saludar() {
        console.log(`Hola mi nombre es ${this.nombre}`);
    }

    static queEres() {
        console.log("Los perros somos animales mamíferos que pertenecemos a la familia de los caninos. Somos considerados los mejores amigos del hombre");
    }
}

Perro.queEres();
```

En este ejemplo el método queEres() es un método estático.

## Métodos getters y setters
Los métodos setter y getters son métodos especiales que permiten establecer y obtener el valor de un atributo que existe en la clase, pero que a la hora de que el usuario la creo o nosotros a la hora de invocar la instancia basada en nuestra clase no la definimos

Para definir un getter y un setter usaremos el siguiente ejemplo:
```javascript
class Perro {
    constructor(nombre, genero, tamanho) {
        this.nombre = nombre;
        this.genero = genero;
        this.tamanho = tamanho;
        this.raza = null;
    }

    sonar() {
        console.log("Hago sonidos por que estoy vivo");
    }

    saludar() {
        console.log(`Hola me llamo ${this.nombre}`);
    }
    // para detectar método get anteponemos la palabra get
    get getRaza() {
        return this.raza;
    }

    // para detectar método set anteponemos la palabra set
    set setRaza(raza) {
        this.raza = raza;
    }

}
```

Note que para definir un método get y set este se debe de definir dentro de la clase.

Además tenemos que señalar que es un getter o un setter colocando las palabras reservadas get y set respectivamente. Por comodidad a la hora de definir los metodos getter y setter se antepone la palabra get y set en el nombre del método, es decir:

`get get<nombre_método>(){}`

`set set<nombre_método>(){}`

Como ejemplo tenemos los métodos getRaza y setRaza

A la hora de definir un getter es importante el uso del return
```javascript
get get<nombre_método>(){
    return this.<propiedad>
}
```

A la hora de definir un setter es importante señalar como parámetro el objeto que queremos dar, esto debido a que no tenemos definido el parámetro en la clase, es decir,
```javascript
get get<nombre_método>(<parámetro>) {
    this.propiedad = <parámetro>
}
```

Es importante señalar que aunque definimos los métodos getter y setter como un método, los debemos de trabajar como propiedades, por ejemplo:
```javascript
const scooby = new Perro("Scooby", "Macho", "Gigante");
console.log(scooby.getRaza);
scooby.setRaza = "Grán Danés";
console.log(scooby.getRaza);
```

En este caso definimos la instancia scooby de la clase Perro y queremos dar un valor a la propiedad raza, la cual la definimos con valor null, para darle un nuevo valor escribimos scooby.setRaza = "valor", en lugar de `scooby.setRaza("valor")`.