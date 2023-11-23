# Type Assertions

Aserciones de tipo
Las aserciones de tipo en TypeScript son una forma de decirle al compilador que trate un valor como un tipo específico, independientemente de su tipo inferido.

Hay dos sintaxis para las aserciones de tipo en TypeScript:

+ The “angle-bracket” syntax: <T>value
+ The “as” syntax: value as T

``` typescript
let num = 42;

// using angle-bracket syntax
let str = <string>num;

// using as syntax
let str2 = num as string;
```
[Tipos de Asersiones](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-assertions)

# as const
as const es una aserción de tipo en TypeScript que te permite afirmar que una expresión tiene un tipo específico, y que su valor debe ser tratado como un valor de sólo lectura.

Por ejemplo:
``` typescript
const colors = ['red', 'green', 'blue'] as const;

// colors is now of type readonly ['red', 'green', 'blue']
```
El uso de **as const** permite a TypeScript inferir tipos más precisos para las constantes, lo que puede conducir a una mejor comprobación de tipos y a una mejor inferencia de tipos en tu código.

# as Type
as es una aserción de tipo en TypeScript que te permite decirle al compilador que trate un valor como un tipo específico, independientemente de su tipo inferido.

``` typescript
let num = 42;
let str = num as string;

// str is now of type string, even though num is a number
```
Es importante tener en cuenta que las aserciones de tipo no cambian el tipo en tiempo de ejecución de un valor, y no causan ningún tipo de conversión. Simplemente proporcionan una forma para que **el programador anule la inferencia de tipo realizada por el compilador**.

# as Any
any es un tipo especial en TypeScript que representa un valor de cualquier tipo. Cuando un valor se declara con el tipo any, el compilador no realizará ninguna comprobación de tipo o inferencia de tipo sobre ese valor.

``` typescript
let anyValue: any = 42;

// we can assign any value to anyValue, regardless of its type
anyValue = 'Hello, world!';
anyValue = true;
```