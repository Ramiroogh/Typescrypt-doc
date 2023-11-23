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