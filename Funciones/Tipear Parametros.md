# Tipar parametros
Hay que tener mucho cuidado al tipar parametros en una funcion, ya que typescript puede parsearlo y nos da la ilusin de que esta tipeado correctamente pero NO, solamente esta como del tipo 'any' y luego lo parsea a un tipo.

Esto esta mal, veamos un ejemplo:

``` typesript
function saludar({ name: string, age: number }) {
    console.log(`Hola ${name}, tenes ${age} años`)
}

saludar({ name: 'Pepe', age: 5 })
```

Aca lo que podemos ver, es que typescript por debajo esta parseando los tipos de datos y (ESTA COLISIONANDO CON LA SINTAXIS DE JAVASCRIPT), ya que primitivamente tienen el tipo any, y luego los parsea.

+ La manera correcta de tiparlo es la siguiente, de dos formas:

1. La primera:
``` typesript
function saludar({ name, age }: { name: string, age: number }) {
    console.log(`Hola ${name}, tenes ${age} años`)
}

saludar({ name: 'Pepe', age: 2 })
```
---
2. La segunda:
``` typesript
function saludar(persona: { name: string, age: number }) {
    const { name, age } = persona
    console.log(`Hola ${name}, tenes ${age} años`)
}

saludar({ name: 'Pepe', age: 2 })
```
+ Lo unico malo, o desventaja es que esta manera, te obliga a desestructurar.