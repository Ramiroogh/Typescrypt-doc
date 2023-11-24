# Clases en TypeScript: Estructurando Código con Orientación a Objetos

En TypeScript, las clases representan un pilar fundamental de la programación orientada a objetos, ofreciendo una manera estructurada y modular de organizar el código. Las clases permiten la creación de objetos que encapsulan propiedades y métodos relacionados, facilitando la creación de sistemas más complejos y fáciles de mantener.

## Declaración y Uso Básico

La definición de una clase en TypeScript sigue una sintaxis similar a la de JavaScript, pero con la adición de tipos estáticos y otras funcionalidades propias del sistema de tipos de TypeScript.

```typescript
class Producto {
  nombre: string;
  precio: number;

  constructor(nombre: string, precio: number) {
    this.nombre = nombre;
    this.precio = precio;
  }

  mostrarInformacion(): string {
    return `Producto: ${this.nombre}, Precio: ${this.precio}`;
  }
}
```

En este ejemplo, la clase `Producto` tiene propiedades (`nombre` y `precio`), un constructor para inicializar dichas propiedades, y un método `mostrarInformacion` para proporcionar detalles sobre el producto.

## Herencia y Extensibilidad

Las clases en TypeScript admiten la herencia, permitiendo la creación de subclases que pueden heredar propiedades y métodos de una clase base.

```typescript
class Libro extends Producto {
  autor: string;

  constructor(nombre: string, precio: number, autor: string) {
    super(nombre, precio);
    this.autor = autor;
  }

  mostrarInformacion(): string {
    return `${super.mostrarInformacion()}, Autor: ${this.autor}`;
  }
}
```

En este caso, la clase `Libro` extiende la clase `Producto` y agrega una propiedad adicional (`autor`) y una implementación modificada del método `mostrarInformacion`.

## Visibilidad de Miembros

Las clases en TypeScript también ofrecen modificadores de acceso como `public`, `private` y `protected`, que controlan la visibilidad de propiedades y métodos dentro y fuera de la clase.

```typescript
class CuentaBancaria {
  private saldo: number;

  constructor(saldoInicial: number) {
    this.saldo = saldoInicial;
  }

  depositar(monto: number): void {
    this.saldo += monto;
  }

  obtenerSaldo(): number {
    return this.saldo;
  }
}
```

En este ejemplo, la propiedad `saldo` está marcada como `private`, lo que significa que solo es accesible dentro de la propia clase `CuentaBancaria`.

# Classes vs Interfaces: Escogiendo la Mejor Herramienta para el Trabajo

Al abordar la estructuración de código en TypeScript, surge la elección entre el uso de clases y el empleo de interfaces. Ambos conceptos sirven para definir estructuras y contratos en el código, pero difieren en sus propósitos y en la forma en que se aplican.

## Clases

Las clases son constructores de objetos que encapsulan propiedades y métodos relacionados. Permiten la creación de instancias, herencia, y la implementación de la programación orientada a objetos. Utilizar clases es adecuado cuando se necesita representar entidades concretas que tienen un estado y comportamiento asociados.

```typescript
class Coche {
  marca: string;
  modelo: string;

  constructor(marca: string, modelo: string) {
    this.marca = marca;
    this.modelo = modelo;
  }

  acelerar(): void {
    console.log(`${this.marca} ${this.modelo} acelerando...`);
  }
}
```

## Interfaces

Las interfaces, por otro lado, son contratos que definen la forma que debe tener un objeto. No pueden ser instanciadas por sí mismas y no contienen implementaciones de métodos. Son ideales para definir estructuras y contratos que pueden ser implementados por múltiples clases o incluso por otros tipos de datos.

```typescript
interface Animal {
  nombre: string;
  hacerSonido(): void;
}
```

## Elección Sabia

La elección entre clases e interfaces depende de la situación. Si se busca representar entidades concretas y necesitas instancias de objetos, las clases son la elección natural. Si el objetivo es definir contratos que pueden ser implementados por diferentes tipos, las interfaces son la herramienta adecuada.

En muchos casos, la combinación de ambas, aprovechando la herencia y la implementación de interfaces, ofrece la máxima flexibilidad y modularidad en el diseño de código TypeScript. La clave está en comprender las fortalezas y limitaciones de cada concepto y aplicarlos de manera apropiada

### Nota
Las interfaces No ejecutan nada, solo se describen asi mismas, en cambio una clase es distinta, ya que tiene su metodo especial llamado constructor() el cual, construye el objeto cuando se realiza una instancia con new.