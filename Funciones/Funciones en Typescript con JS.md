``` javascript
function saludar(name) {
    console.log(`Hola ${name}`)
}
```
Vamos a analizar el parametro "name" de la funcion saludar().
Este parametro, implicitamente tiene el tipado de 'any', por lo cual, es mejor asignarle un tipo o tipearlo.

Correjido:
``` javascript
function saludar(name: string) {
    console.log(`Hola ${name}`)
}
```
# Definir el retorno del Tipo de dato, de una Funcion
```typescript
function show(): number {
  console.log("hola");
  return 1;
}
```
La función está explícitamente declarada para retornar un valor de tipo numérico (`number`). La declaración `: number` después de los paréntesis `()` indica que el tipo de retorno de la función debe ser un número.

Por lo tanto, el código cumple con esa declaración al tener la instrucción `return 1;` que devuelve un valor numérico. Si intentaras retornar un valor de otro tipo (por ejemplo, una cadena), TypeScript generaría un error en tiempo de compilación para indicar que no estás cumpliendo con la declaración de tipo especificada.
---

# Comportamiento de Funciones en TypeScript: Claridad y Flexibilidad

En TypeScript, las funciones son elementos fundamentales que permiten organizar y modular el código de manera eficiente. A través de un sistema de tipos sólido, TypeScript mejora la claridad y la seguridad al trabajar con funciones, ofreciendo una serie de características que van más allá de lo que proporciona JavaScript.
---

## Declaración y Tipado de Parámetros

Las funciones en TypeScript permiten la especificación de tipos para los parámetros y el tipo de retorno, proporcionando un nivel adicional de información para el desarrollador y el compilador.

```typescript
function sumar(a: number, b: number): number {
  return a + b;
}
```

En este ejemplo, la función `sumar` acepta dos parámetros numéricos y devuelve un resultado numérico, lo que facilita la comprensión y el uso correcto de la función.
---

## Parámetros Opcionales y Predeterminados

En TypeScript, se pueden declarar parámetros opcionales mediante el uso del símbolo `?`. Además, es posible asignar valores predeterminados a los parámetros para proporcionar flexibilidad en la llamada de la función.

```typescript
function saludar(nombre: string, saludo?: string): string {
  if (saludo) {
    return `${saludo}, ${nombre}!`;
  } else {
    return `Hola, ${nombre}!`;
  }
}

console.log(saludar("Juan")); // Hola, Juan!
console.log(saludar("Ana", "¡Saludos")); // ¡Saludos, Ana!
```

## Rest Parameters

Los "rest parameters" permiten que una función acepte un número variable de argumentos, agrupándolos en un array.

```typescript
function concatenar(...palabras: string[]): string {
  return palabras.join(" ");
}

console.log(concatenar("Esto", "es", "una", "cadena")); // "Esto es una cadena"
```

## Funciones de Flecha

Las funciones de flecha en TypeScript proporcionan una sintaxis más concisa y retienen el valor de `this` del contexto circundante.

```typescript
const multiplicar = (a: number, b: number): number => a * b;

console.log(multiplicar(5, 3)); // 15
```

## Sobrecarga de Funciones

TypeScript permite declarar múltiples firmas para una función mediante la sobrecarga de funciones, permitiendo un manejo más específico de diferentes casos de uso.

```typescript
function obtenerValor(elemento: HTMLElement): string;
function obtenerValor(elemento: HTMLInputElement): string | null;
function obtenerValor(elemento: HTMLElement | HTMLInputElement): string | null {
  if (elemento instanceof HTMLInputElement) {
    return elemento.value;
  } else {
    return elemento.textContent || null;
  }
}
```

## Contexto y Callbacks

En situaciones asincrónicas, como las operaciones de lectura de archivos o las solicitudes de red, TypeScript facilita el manejo de funciones de retorno de llamada, garantizando que los tipos sean coherentes y comprensibles.

```typescript
function descargarArchivo(url: string, callback: (data: string) => void): void {
  // Lógica para descargar el archivo
  const archivoDescargado = "Contenido del archivo descargado";
  callback(archivoDescargado);
}

descargarArchivo("https://ejemplo.com/archivo.txt", (data) => {
  console.log(`Archivo descargado: ${data}`);
});
```

## Conclusiones

El comportamiento de las funciones en TypeScript se destaca por su capacidad para mejorar la claridad del código y reducir la posibilidad de errores mediante la tipificación de parámetros y valores de retorno. La flexibilidad en la declaración de parámetros, las funciones de flecha, y las diversas características ofrecen un amplio rango de posibilidades para adaptarse a las necesidades de desarrollo.

Al comprender y aplicar estas características, los desarrolladores pueden aprovechar al máximo el sistema de tipos de TypeScript y escribir código más seguro, mantenible y comprensible.