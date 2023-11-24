# MappedTypes
Un MappedType, son crear tipos de manera dinamica, basandonos en otros tipos o interfaces.

**Mapped Types en TypeScript: Transformación Dinámica de Tipos**

Mapped Types es una característica avanzada en TypeScript que permite crear tipos nuevos a partir de tipos existentes mediante la aplicación de una transformación sobre cada propiedad del tipo original. Estos tipos mapeados son especialmente útiles para la creación de tipos dinámicos y genéricos, brindando una forma poderosa de trabajar con estructuras de datos de manera más flexible y abstracta.

## Sintaxis Básica

La sintaxis básica de un Mapped Type implica el uso del operador `in` para iterar sobre todas las claves de un tipo y aplicar una transformación a cada una.

```typescript
type ConvertirOpcionales<T> = {
  [K in keyof T]?: T[K];
};

interface Ejemplo {
  nombre: string;
  edad: number;
}

const opcionalEjemplo: ConvertirOpcionales<Ejemplo> = {};
// opcionalEjemplo tiene las propiedades "nombre?" y "edad?" de Ejemplo
```

En este ejemplo, `ConvertirOpcionales` convierte cada propiedad de `Ejemplo` en una propiedad opcional.

## Restricciones y Modificadores

Mapped Types pueden aplicarse con restricciones y modificadores, permitiendo un control más preciso sobre las transformaciones.

```typescript
type SoloLectura<T> = {
  readonly [K in keyof T]: T[K];
};

interface Datos {
  nombre: string;
  edad: number;
}

const datosSoloLectura: SoloLectura<Datos> = { nombre: "Juan", edad: 30 };
// datosSoloLectura tiene propiedades solo de lectura "nombre" y "edad" de Datos
```

En este caso, `SoloLectura` convierte cada propiedad de `Datos` en una propiedad de solo lectura.

## Condiciones en Mapped Types

Mapped Types también pueden incluir condiciones para aplicar transformaciones basadas en el tipo de las propiedades originales.

```typescript
type FiltrarNumerico<T> = {
  [K in keyof T]: T[K] extends number ? T[K] : never;
};

interface Datos {
  nombre: string;
  edad: number;
  altura: number;
}

const datosNumericos: FiltrarNumerico<Datos> = { edad: 25, altura: 175 };
// datosNumericos tiene solo propiedades numéricas de Datos
```

En este ejemplo, `FiltrarNumerico` selecciona solo las propiedades numéricas de `Datos`.

## Uso Práctico

Mapped Types son útiles en situaciones donde necesitas crear tipos dinámicos y genéricos, como en la manipulación de datos, la validación de formas, y la definición de interfaces flexibles. Su aplicación puede simplificar el código y hacerlo más genérico y adaptable a diferentes escenarios.

## Conclusiones

Mapped Types en TypeScript representan una característica avanzada pero potente que facilita la manipulación y transformación dinámica de tipos existentes. Su capacidad para crear tipos nuevos basados en otros abre posibilidades para escribir código más abstracto, flexible y reutilizable. Al entender y aplicar Mapped Types de manera efectiva, los desarrolladores pueden mejorar significativamente la calidad y la flexibilidad de su código TypeScript.