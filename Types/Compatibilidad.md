# Type Compatibility
TypeScript utiliza tipado estructural para determinar la compatibilidad de tipos. Esto significa que dos tipos se consideran compatibles si tienen la misma estructura, independientemente de sus nombres.

Aquí hay un ejemplo de compatibilidad de tipos en TypeScript:

``` typescript
interface Point {
  x: number;
  y: number;
}

let p1: Point = { x: 10, y: 20 };
let p2: { x: number; y: number } = p1;

console.log(p2.x); // Output: 10
```

En este ejemplo, p1 tiene el tipo Punto, mientras que p2 tiene el tipo { x: número; y: número }. A pesar de que los dos tipos tienen nombres diferentes, se consideran compatibles porque tienen la misma estructura. Esto significa que puedes asignar un valor de tipo Punto a una variable de tipo { x: número; y: número }, como hacemos con p1 y p2 en este ejemplo.