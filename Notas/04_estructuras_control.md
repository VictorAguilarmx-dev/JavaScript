# Estructuras de Control

## Índice
- [Condicionales](#condicionales)
    - [If - Else](#if---else)
    - [Operador Ternario](#operador-ternario)
    - [Switch-Case](#switch---case)
- [Ciclos (Loops)](#ciclos-loops)
    - [While](#while)
    - [Do While](#do-while)
    - [For](#for)
    - [For In](#for-in)
    - [For Of](#for-of)
- [Manejo de Errores (Try - Catch)](#manejo-de-errores-try---catch)
- [Breake y Continue](#break-y-continue)
    - [Breake](#break)
    - [Continue](#continue)
- [Desestructuración](#desestructuración)
    - [Desestructuración de objetos](#desestructuración-de-objetos)
    - [Desestructuración de arrays](#desestructuración-de-arrays)
- [Objetos literales](#objetos-literales)
- [Parámetros REST](#parámetros-rest)
- [Operador Spread](#operador-spread)
- [Arrow Functions](#arrow-functions)
***
Una estructura de control es un mecanismo que permite controlar el flujo de programación.

Tenemos diferentes estructuras de control

- Estructuras Secuenciales.
- Esctructuras Condicionales.
- Estructuras Repetitivas.

## Condicionales

### If - Else
Estructura que permite tomar una decisión y si se cumple permite ejecutar ciertas acciones.
```javascript
if (<condición>) {
    <código>
} else {
    <código>
}
```
Podemos anidar condicionales, es decir, si tenemos múltiples condiciones con resultados diferentes podemos escribir de la siguiente forma:
```javascript
if (condicion_1) {
    resultado_condición_1
} else if (condición_2) {
    resultado_condición_2
} else if (condición_3) {
    resultado_condición_3
} else {
    resultado_no_implica_condición_1_2_3
}
```

### Operador Ternario
Podemos simplificar el uso del `if-else` gracias al **operador ternario**, este consta de:
```javascript
(condición) ? resultado_verdadero : resultado_falso
```
- El uso del operador ternario sólo simplifica el uso de un if-else, es decir, no funciona al anidar if-else.
- Podemos simplificar el uso de anidamiento de if-else si colocamos el anidamiento en una función y llamamos la función en el operador ternario.

### Switch - Case
Esta estructura se utiliza cuando tenemos múltiples casos, este puede sustituir el anidamiento de if -else
```javascript
switch (<variable>) {
    case <valor_variable>:
        código
        break
    case <valor_variable>:
        código
        break
    default:
        código
        break
}
```
- Cuando se encuentra un **`break`**, el programa sale del condicional `switch` y ejecuta la declaración que lo procede.
- Si olvidas un `break`, el script se ejecutará desde donde se cumple la condición y ejecutará el siguiente `case` independientemente si esta condición se cumple o no.
- JavaScript retornará a la instancia **`default`** en caso de no encontrar una coincidencia:

## Ciclos (Loops)
Sirven para hacer acciones de forma repetitiva hasta que se cumpla una condición

### While
Sirve para iterar un bloque de código hasta que se cumple una condición
```javascript
let contador = valor

while (condición_sobre_contador) {
    código
    contador++ / contador--
}
```
- Es importante el uso de un contador, pues este nos va a delimitar cuantas iteraciones debe de tener el bucle.
- En caso de no colocar la condición o el contador podemos tener problemas con el programa

Hoy en día es poco probable encontrar código con el bucle while, pero no es imposible

### Do While
Sirve para lo mismo que el while, solo que este ejecuta el código primero y luego itera el contador
```javascript
let contador = valor;

do {
    código
    contador++ / contador--
} while (condición_sobre_contador)
```

### For
Es el ciclo más utilizado en JavaScript, esto por que es más completa y simple que las otras dos
```javascript
for (inicialización_variable ; condición ; decremento_incremento_variable) {
    código
}
```

### For In
El funcionamiento es el mismo que el ciclo for, solo que este es exclusivo para objetos (diccionarios)
```javascript
const nombre_objeto = {
    key1: valor,
    key2: valor,
}

for (const variable in nombre_objeto){
    código
}
```

### For Of
El funcionamiento es igual que el for, solo que este itera cualquier objeto iterable en JavaScript
```javascript
const / let objeto_nombre = objeto_iterable ([] / '')

for (const variable of objeto_nombre){
    código
}
```

## Manejo de Errores (Try - Catch)
Para el manejo o detección de errores JavaScript tiene una estructura llamada `try-catch-finaly`, esta nos permite evaluar fragmentos de código.
```javascript
try {
    <Se_agrega_el_código_a_evaluar>
} catch (error){
    <Captura_cualquier_error_surgido_o_lanzado_en_el_try>
} finally {
    <Se_ejecuta_siempre_al_final_de_un_bloque_try-catch>
}
```
Con `try-catch` podemos generar errores personalizados, esto nos puede ayudar a la hora de hacer testing. Por ejempo
```javascript
try {
    let numero = y;
if (isNaN(numero)) {
    throw new Error("El caracter introducido no es un Número");
}
    console.log(numero * numero);
} catch (error) {
    console.log(`Se produjo el siguiente error: ${error}`)
}
```

## Break y Continue
Estas palabras nos ayudan a controlar el flujo en las estructuras de control

### Break
Una vez que llegues a un cierto numero de iteraciones el `break` hace que te salgas de la estructura de control. Por ejemplo,
```javascript
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0];

for (let i = 0; i < numeros.length; i++) {
    if (i === 5) {
        break;
    }
    console.log(numeros[i]);
}
```

El resultado de este código es que imprime hasta el número 5, pues una vez que `i === 6` entra el break y no se va a ejecutar otro iteración

### Continue
Una vez que llegues a un cierto número de iteraciones el continue hace que no se ejecute la iteración siguiente y se salta hasta la iteracion siguiente. Por ejemplo
```javascript
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

for (let i = 0; i < numeros.length; i++) {
    if (i === 5) {
        continue;
    }
    console.log(numeros[i]);
}
```

Este código imprime del 1 al 5, luego entra el `continue` por lo que se salta el 6 y después imprime del 7 al 0.

## Desestructuración
La desestructuración en JavaScript es una sintaxis o forma de escritura que nos permite extraer valores de un array o propiedades de un objeto en secciones más pequeñas. Esta desestructuración hace que podamos acceder a elementos específicos de un conjunto más grande por medio de distintas variables. Esto abre la posibilidad de pintar un único valor o conjunto de valores de las variables de un objeto, al igual que pintar determinadas propiedades de un valor de un array.

### Desestructuración de objetos
```javascript
const persona = {
    nombre: "Victor",
    apellido: "Aguilar",
    edad: 25
};

let {nombre, apellido, edad} = persona;
console.log(nombre, apellido, edad);
```

### Desestructuración de arrays
```javascript
const numeros = [1, 2, 3];

const [one, two, three] = numeros;

console.log(one, two, three);
```

## Objetos literales
Los **objetos literales** son una forma de escribir objetos ahorrando código. Por ejemplo, Sabemos que un objeto se puede definir de la siguiente forma:
```javascript
    let nombre = "Pepe",
        edad = 7;

    const perro = {
        nombre: nombre,
        edad: edad,
        ladrar: function () {
            console.log('guauu guauu');
        }
    }
```

En formato de un objeto literal este mismo objeto se define de la siguiente forma:
```javascript
    let nombre = "Pepe",
        edad = 7;

    const dog = {
        nombre,
        edad,
        raza: "Tekel",
        ladrar() {
            console.log('guauu guauu guauu');
        }

}
```
Como podemos ver en la forma normal podemos especificar el valor de cada propiedad (prop) o método de nuestro objeto, mientras que en el formato literal no es necesario especificar la prop o el método en nuestro objeto.

## Parámetros REST
Son una forma de ir agregando parámetros dentro de una función o una variable.

Por lo general se utiliza cuando no sabemos cuantos parámetros van a llegar a nuestra función.

La sintaxis de los parámetros rest nos permiten representar un número indefinido de argumentos como un array.

El último parámetro de una función se puede prefijar con `...`, lo que hará que todos los argumentos restantes (suministrados por el usuario) se coloquen dentro de un array de javascript "estándar".

Sólo el último parámetro puede ser un "parámetro rest".

Por ejemplo:
```javascript
function sumar(a, b, ...c) {
    let resultado = a + b;

    c.forEach(function (n) {
        resultado += n;
    });

    return resultado;
}
```

## Operador Spread
Nos permite fusionar 2 o más arreglos en uno sólo. Por ejemplo:
```javascript
const arr1 = [a, b, c],
    arr2 = [d, e, f];

const arr3 = [...arr1, ...arr2];
```

Este código nos mostrará el siguiente arreglo

`[a, b, c, d, e, f]`

En cambio si definimos `arr3` de la siguiente forma:

`const arr3 = [arr1, arr2]`

Tenemos que `arr3` es un arreglo formado por dos arreglos, es decir,

`[[a, b, c], [d, e, f]]`

## Arrow functions
Es una forma de sintetizar la sintaxis de funciones anónimas.

Recordemos que una función anónima es cuando definimos una variable con valor una función. Por ejemplo:
```javascript
const saludo = function () {
    console.log("Hola");
}
```

El ejemplo anterior expresado como arrow function sería de la siguiente forma:
```javascript
const <nombre_variable> = (<parámetros>) => {
    <lineas_de_código>
}
```

Cuando nuestra función sólo tiene una sóla línea de código podemos omitir el uso de llaves, es decir:
```javascript
const saludo = () => console.log("Hola");
```

Cuando una arrow function recibe sólo un parámetro podemos omitr el uso de los paréntesis.
```javascript
const saludo = nombre => console.log(`Hola ${nombre}`);
```