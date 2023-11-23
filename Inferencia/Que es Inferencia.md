# Inferencia en Typescript

En TypeScript, la inferencia de tipos se refiere a la capacidad del compilador para deducir automáticamente el tipo de una variable o expresión en función de su contexto. TypeScript utiliza un sistema de tipos estáticos que permite especificar tipos para variables, parámetros de funciones, propiedades de objetos, etc. Sin embargo, no siempre es necesario proporcionar explícitamente los tipos, ya que TypeScript puede **inferirlos automáticamente** en muchos casos.

Aquí hay un ejemplo simple para ilustrar la inferencia de tipos en TypeScript:

```typescript
// Variable con inferencia de tipo
let mensaje = "Hola, TypeScript";

// TypeScript infiere que 'mensaje' es de tipo string
console.log(mensaje.toUpperCase()); // Esto es válido

// Intentar asignar un valor de otro tipo generará un error
// mensaje = 123; // Esto generará un error de tipo
```

En este ejemplo, TypeScript infiere que la variable `mensaje` es de tipo `string` porque se inicializa con una cadena. Si intentaras asignarle un valor de otro tipo, como un número, TypeScript mostraría un error de tipo.

La inferencia de tipos también es útil al trabajar con funciones y objetos. Por ejemplo:

```typescript
// Inferencia de tipo en funciones
function sumar(a: number, b: number) {
    return a + b;
}

// TypeScript infiere que el resultado es de tipo number
let resultado = sumar(3, 5);

// Inferencia de tipo en objetos
let persona = {
    nombre: "Juan",
    edad: 30
};

// TypeScript infiere que 'persona' es de tipo { nombre: string, edad: number }
console.log(persona.nombre);
console.log(persona.edad);
```

En estos ejemplos, TypeScript puede inferir los tipos de los parámetros de la función `sumar` y de las propiedades del objeto `persona` en función de cómo se utilizan.

La inferencia de tipos es una característica poderosa de TypeScript que ayuda a escribir código más conciso y menos propenso a errores al tiempo que aprovecha las ventajas de un sistema de tipos estáticos.

