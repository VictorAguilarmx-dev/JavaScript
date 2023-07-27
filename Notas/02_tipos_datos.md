# Tipos de datos

## Índice
- [Variables](#variables)
    - [var vs let](#var-vs-let)
    - [constantes](#constantes)
- [Strings](#strings)
    - [Template strings](#template-strings)
- [Numbers](#numbers)
- [Booleans](#boolean)
- [Undefined, Null, NaN](#undefined-null-nan)
- [Funciones](#funciones)
    - [Funciones Declaradas](#funciones-declaradas)
    - [Funciones Expresadas](#funciones-expresadas)
- [Arrays](#arrays)
- [Objects](#objects)
***
## Variables
Una variable en js es un lugar en la memoria de la computadora que sirve para almacenar datos

Declaramos una variable de la siguiente forma:

```javascript
var hola = "Hola Mundo";
let hello = "Hola Mundo";
```

### var vs let
Las variables tienen un ambito de existencia llamado el "scope" de las variables, en js teneíamos 2

- Scope global
    - Tiene como alcance todo el documento
- Scope funcional
    - Tiene alcance sólo una función

En la actualidad js tiene 2 formas de scope
- Scope global
    ```javascript
    var hola = "Hola Mundo"
    ```
- Scope ambito de bloque
    ```javascript
    let hola = "Hola mundo"
    ```

Actualmente no es bien visto usar var, por lo tanto !!! Siempre usar let!!!!

Las variables en Scope global se guardan en el en el objeto ‘‘window’’

### constantes
Usamos const para declarar constantes, este tipo de variables no cambian a lo largo del script
```javascript
const PI = 3.141516
```

- Podemos definir variables vacías, excepto con const
- Si definimos un valor primitivo con const no podemos cambiar el valor.
- Si definimos un valor compuesto con const si podemos modificar el valor.

## Strings
Un string es una cadena de texto que se encuentra entre comillas simples o comillas dobles
```javascript
let nombre = "Victor"
```

- Podemos unir valores esto gracias a la concatenación
    ```javascript
    let saludos = "Hola mi nombre es: " + nombre + " " + apellido + ".";
    ```

### Template Strings
Los Template Strings permiten generar strings de forma dinámica.
```javascript
let nombre = 'Víctor';
    apellido = 'Aguilar';
    saludo = `Hola mi nombres es ${nombre} ${apellido}.`
```
Al mostrar por pantalla la variable `saludo` nos mostrará lo siguiente:

    `Hola mi nombre es Víctor Aguilar`

Podemos generar código html de forma dinámica gracias al Template String. Por ejemplo,

El siguiente código se utlizó para escribir código html en formato string
```javascript
    let ul = "<ul><li>Primavera</li><li>Verano</li><li>Otoño</li><li>Invierno</li></ul>"

console.log(ul);
```
Al ejecutar obtendremos lo siguiente

`<ul><li>Primavera</li><li>Verano</li><li>Otoño</li><li>Invierno</li></ul>`

En cambio si utilizamos Template Strings tenemos que
```javascript
let ul = `<ul>
    <li>Primavera</li>
    <li>Verano</li>
    <li>Otoño</li>
    <li>Invierno</li>
</ul>`;
console.log(ul);
```
Y al ejecutar el código obtenemos
```html
<ul>
    <li>Primavera</li>
    <li>Verano</li>
    <li>Otoño</li>
    <li>Invierno</li>
</ul>
```

## Numbers

En JavaScript sólo tenemos un tipo de dato para los números, es decir, no hay diferencia entre un numero entero y un valor float.
```javascript
let n = 3 // int
let m = 3.4 // float
```
Hay dos formas para definir un número
- Como una variable
    ```javascript
    let a = 2;
    let b = 2.2
    ```
- Con el contructor
    ```javascript
    let a = new Number(2);
    let b = new Number(2.2);
    ```

## Boolean
Sólo hay dos valores posibles, true / false
```javascript
let T = true;
let F = false;
```

## Undefined, Null, NaN
Son casos muy particulres de js

- Undefined y Null representan un valor ausente, es decir, no tiene valor
- Undefined es una variable no inicializada, es decir no se le ha asignado un valor a la variable
- Null es una variable vacía que el programador de ha asignado ese valor.
- NaN significa Not a Number
- La consola nos regresa un NaN cuando el resultado no es un número.

## Funciones
Una función es un bloque de código autocontenido independiente que se define una sóla vez y se puede ejecutar en cualquier momento.

- Puede o no recibir multiples parámetros
- Puede o no devolver multiples valores
- En Js las funciones también son objetos

Hay dos tipos de funciones

### Funciones Declaradas
```javascript
function estoEsUnaFuncion () {
    console.log("Uno");
    console.log("Dos");
    console.log("Tes");
}

estoEsUnaFuncion();
```
Si una función declarada devuelve un valor esta debe de llevar la palabra reservada **`return`**

Este tipo de funciones se pueden invocar incluso antes de ser declaradas.

### Funciones Expresadas
```javascript
        const funcionExpresada = function () {
            console.log("Esto es una función expresada");
        }
```
Una función expresada es una función que se le ha asignado como valor a una variable, si invocamos esta función antes de su definición JS nos dirá

## Arrays
También se les puede llamar ‘‘Listas’’, almacenan múltiples datos
```javascript
let arreglo = [valor1, valor2, ...]
```

- Se pueden definir con let o const
- Los datos de una lista pueden ser del mismo tipo o de multiples tipos.
- Se pueden definir con let o con const
- El índice en los arreglos inicia en el 0

Podemos acceder a los valores de un arreglo de la siguiente forma
```javascript
arreglo[indice]
```

## Objects
También llamados ‘‘Diccionarios’’
```javascript
    let objeto = {
        key1: valor1,
        key2: valor2,
    }
```
- Se pueden definir con let o const.
- Los valores pueden ser de cualquier tipo, ya sean primitivos o compuestos.
- Dentro de un objeto a las variables se llaman atributos / propiedades.
- Dentro de un objeto a las funciones se llaman métodos.

Accedemos a los valores del objeto de la siguiente forma:
```javascript
objeto[key]

objeto.key
```