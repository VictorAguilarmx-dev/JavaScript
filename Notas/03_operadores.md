# Operadores

## Índice
- [Operadores Aritméticos](#operadores-aritméticos)
- [Operadores Relacionales](#operadores-relacionales)
    - [Diferencia entre `=`, `==` y `===`](#diferencia-entre---y)
- [Operadores de Incremento y Decremento](#operadores-de-incremento-y-decremento)
- [Operadores Lógicos](#operadores-lógicos)
***
## Operadores Aritméticos
Estos operadores retornan un número

- Suma ( `+` )
- Resta( `-` )
- Multiplicación ( `*` )
- División( `/` )
- Módulo ( `%` )

El módulo regresa el residuo de una división

## Operadores Relacionales
Permiten comparar valores y retornan un booleano.

- Mayor que ( `>` )
- Menor que ( `<` )
- Igual que ( `=` )
- Mayor o igual que ( `>=` )
- Menor o igual que ( `<=` )
- Igual igual ( `==` )
- Diferente que ( `!=` )
- Igual igual igual ( `===` )
- Diferente diferente ( `!==` )

### Diferencia entre `=`, `==` y `===`
- Para hacer referencia a la asignación de valores utilizamos `=`
- Para hacer referencia a una comparación de valores utilizamos `==`
- Para hacer referencia a una comparación de valores y tipo de datos utilizamos `===`

Una buena practica es utilizar `===` para hacer comparaciones.

## Operadores de Incremento y Decremento
Se utilizan para aumentar o disminuir el valor de una variable en una unidad o más.

Se pueden encontrar el loops
```javascript
let i = 1;
i = 1 + 2
console.log(i)

i += 2
console.log(i)
```
Los operadores de incremento son los siguientes:
- Suma y asigna ( `+=` )
- Multiplica y asigna ( `*=` )
- Aumento en una unidad ( `++` )

Los operadores de decremento son los siguientes:
- Resta y asigna ( `-=` )
- Divida y asigna ( `/=` )
- Módulo y asinga ( `%=` )
- Decremente en una unidad ( `--` )

A los operadores `++` y `--` se les llama ‘‘**operadores unarios**’’

Los operadores unarios se pueden colocar antes o después, pero hay que tener cuidado con el flujo del código, por eso es recomendable utilizarlos después de la variable.

## Operadores Lógicos
Éstos se utilizan cuando tenemos 2 o más condiciones.

Tenemos 3 tipos de operadores lógicos
- Not ( `!` )
- Or ( `||` )
- And ( `&&` )

El operador Not ( `!` ) niega, es decir lo que es verdadero lo convierte en falso y viceversa.

| P | !P |
|:---:|:---:|
| V | F |
| F | V |

El operador Or ( `||` ) es verdadera cuando almenos una condición es verdadera, es decir, una condición es falsa cuando todas sus condiciones son falsas.

| P |  Q | P \|\| Q |
|:---: | :---: | :---: | 
|V | V | V |
|V | F | V |
|F | V | V |
|F | F | F |

El operador And ( `&&` ) es verdadera cuando todas las condiciones son verdaderas, es decir, si almenos una condición es falsa entonces la condición completa es falsa.

| P | Q | P && Q |
|:---: | :---: | :---: |
| V | V | V |
| V | F | F |
| F | V | F |
| F | F | F |