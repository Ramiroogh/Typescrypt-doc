En TypeScript, puedes crear tus propios tipos personalizados mediante el uso de `type` o `interface`. Estos tipos personalizados permiten definir estructuras de datos específicas, facilitan la lectura del código y proporcionan una manera de reutilizar tipos en diferentes partes de tu aplicación.

### Usando `type`

```typescript
type Coordenadas = {
  x: number;
  y: number;
};

let punto: Coordenadas = { x: 10, y: 20 };
```

En este ejemplo, hemos creado un tipo personalizado llamado `Coordenadas` que representa un objeto con propiedades `x` e `y`. Luego, declaramos una variable `punto` de tipo `Coordenadas` y le asignamos un objeto que cumple con esa estructura.

### Usando `interface`

```typescript
interface Persona {
  nombre: string;
  edad: number;
  direccion?: string; // Propiedad opcional
}

let usuario: Persona = { nombre: "Juan", edad: 30 };
```

En este caso, hemos utilizado una interfaz llamada `Persona` para definir la estructura de un objeto que debe tener propiedades `nombre` y `edad`. La propiedad `direccion` es opcional, ya que tiene un signo de interrogación (`?`). Luego, creamos una variable `usuario` de tipo `Persona` y le asignamos un objeto que se ajusta a la interfaz.

### Uniones de tipos personalizados

```typescript
type Resultado = number | string;

function procesarResultado(resultado: Resultado): void {
  if (typeof resultado === "number") {
    console.log(`El resultado es un número: ${resultado}`);
  } else {
    console.log(`El resultado es una cadena: ${resultado}`);
  }
}

procesarResultado(42);       // El resultado es un número: 42
procesarResultado("Hola");   // El resultado es una cadena: Hola
```

En este ejemplo, hemos creado un tipo personalizado llamado `Resultado` que puede ser `number` o `string`. La función `procesarResultado` toma un parámetro de tipo `Resultado` y realiza una verificación de tipo para determinar si es un número o una cadena.

Estos son solo algunos ejemplos de cómo puedes utilizar tipos personalizados en TypeScript para mejorar la claridad y la robustez de tu código. Los tipos personalizados son especialmente útiles cuando trabajas con estructuras de datos complejas o cuando deseas definir contratos claros entre diferentes partes de tu código.