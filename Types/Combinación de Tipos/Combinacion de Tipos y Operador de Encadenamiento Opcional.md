# Combinación de Tipos

En algunas ocaciones, vamos a necesitar que nuestras variables sean de dos tipos.

+ Un ejemplo, puede ser una variable en la que pueda aceptar un tipo de dato numerico y un tipo de dato string

``` typescript
let response: string | null;
```
Esta declaración, representa una variable declarada, pero que no le estamos dando ningun uso ya que no tiene ningun valor agregado.
Vamos a asignarle un valor.
``` typescript
let response: string | null = 5;
```

## Importante
Esta forma de usar tipos de datos combinados, sirve mucho cuando nosotros no cargamos los datos, simplemente nos llegan los datos desde una fuente externa mediante un servicio.

# Operador de encadenamiento opcional

Este snippet de TypeScript está declarando una variable llamada `response` con un tipo que puede ser `string` o `undefined`. Luego, utiliza el operador de encadenamiento opcional (`?.`) para intentar llamar al método `toString()` solo si `response` no es `undefined`.

```typescript
let response: string | undefined;
response?.toString();
```

La expresión `response?.toString()` es una forma segura de llamar al método `toString()` en `response` sin causar un error si `response` es `undefined`. Si `response` es `undefined`, la expresión se evalúa a `undefined` y no se produce ningún error. Si `response` es una cadena, entonces se llamará al método `toString()` en esa cadena.

Este uso del operador de encadenamiento opcional es particularmente útil cuando trabajas con objetos o propiedades que pueden ser `null` o `undefined`, ya que evita tener que realizar comprobaciones explícitas antes de acceder a propiedades o métodos.