# Introducción

## Índice
- [Historia](#historia)
- [Isomorfismo.](#isomorfismo)
- [Características.](#características)
- [Escritura de código.](#escritura-de-código)
- [Palabras reservadas.](#palabras-reservadas)
- [Orden del código.](#orden-del-código)
- [Tipos de datos en JS.](#tipos-de-datos-en-js)
***
## Historia
Creado por Brendan Eich en la década de los 90

En 1997 Netscape estandarizó el lenguaje en su versión 1.1, esto para neutralizar posible contienda tecnológica.

La cuarta edición fue abandonada por diferencias políticas respecto a la complejidad del lenguaje.

En 2009 se lanza ECMAScript 5 y en 2011 se alinea con la tercera edición estándar internacional.

A partir del 2015 se actualiza constantemente 

Actualmente estamos en la versión 6 del estándar.

## Isomorfismo
Hoy JS, es el único lenguaje capaz de ejecutarse en las 3 capas de una aplicación:

- Frontend (JS).
- Backend (Node.js).
- Persistencia de Datos (MongoDB, Couch DB, Firebase, etc).

Con JS puedes hacer:

- Diseño y Desarrollo Web.
- Videojuegos.
- Experiencias 3D, Realidad Aumentada, Realidad Virtual.
- Controlar Hardware (Drones, robots, electrodomésticos).
- Aplicaciones Híbridas y Móviles.
- etc.

## Características
- Lenguaje de Alto Nivel.
- Interpretado.
- Dinámico.
- Débilmente Tipado.
- Multi paradigma.
- Sensible a MAYUSCULAS y minúsculas.
- No necesitas los puntos y comas al final de cada línea.

## Escritura de código
Los identificadores deben coenzar con:
  - Una letra
  - Un signo de dolar $
  - Un guión bajo \_
  - Nunca con números o caracteres especiales

Usa **snake_case** en:
- Archivos:

    `mi_archivo_javascript.js`

Usa **UPPER_CASE** en:
- Constantes:
    ```javascript
    const UNA_CONSTANTE = 'Soy una constante'
    ```

Usa **UpperCamelCase** en:

- Clases:
    ```javascript
    class SerHumano {
        constructor (nombre, genero) {
            this.nombre = nombre
            this.genero = genero
        }
        miNombreEs () {
        return `Mi nombre es ${ this. nombre }`
        }
    }
    ```

Usa **lowerCamelCase** en:
- Objetos:
    ```javascript
    const unObjeto {
        nombre: 'Víctor',
        email: 'victor@gmail.com'
    }
    ```

- Primitivos:
    ```javascript
    let unaCadena = 'Hola Mundo',
        unNumero = 19,
        unBooleano = true
    ```

- Funciones:
    ```javascript
    function holaMundo ( nombre ) {
        alert( `Hola mundo ${ nombre }` )
    }
    holaMundo( 'Víctor' )
    ```

- Instancias
    ```javascript
    const ajax = new XMLHttpRequest(),
        vic = new SerHumano( 'Víctor', 'Hombre' )        
    ```

## Palabras reservadas
| Letra | Palabras |
| :---: | --- |
| A | abstract |
| B | bollean, break, byte |
| C | case, catch, char, class, const, continue |
| D | debugger, default, delete, do, double |
| E | else, enum, export, extends |
| F | false, final, finally, float, for, function |
| G | goto |
| I | if, implements, imort, in, instanceof, int, interface |
| L | long |
| N | native, new, null |
| P | package, private, protectd, publec |
| R | return |
| S | short, static, super, switch, synchronized |
| T | this, throw, throws, transient, true, try, typeof |
| V | var, volatile, void |
| W | while, with |

## Orden del código
1. Importación de módulos.
2. Declaración de variables.
3. Declaración de funciones.
4. Ejecución de código.

## Tipos de datos en JS
1. Primitivos: Se accede directamente al valor.
    - string
    - number
    - boolean
    - null
    - undefined
    - NaN
2. Compuestos: Se accede a la referencia del valor.
    - object = {}
    - array = []
    - function () {}
    - Class {}
    - etc.