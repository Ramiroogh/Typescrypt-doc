# Enums
Un enum, es un tipo de dato, que nos permite almacenar Listas de valores estaticos.
podemos almacenar valores consecutivos, la palabra enum proviene de "Enumeration o Enumeracion".

Sintaxis:
``` typescript
enum Users{
    NormalUser,
    PayedUser,
    AminUser,
    MegaUser,
}

const myUser = User.AdminUser;
console.log(myUser); //Response: 2
```

Las Listas comienzan con el primer elemento, con indice 0.
Los enums nos da la ventaja de almacenar valores en lista, desde 0 al infinito, y tambien dandole un Alias.

Nota: de esta forma, la Filosofia de typescript, por medio de este contexto, como lo es enum, podemos generar codigo mas legible y modularizado, (const myUser = User.AdminUser;).
Al tener el Alias User de la Lista, logramos entender con facilidad a que se refiere.

## Tipear enums
de esta manera centralizamos los datos, en una lista para luego usarlos, de una manera legible, para evitar crear variables apartes o objetos.

``` typescript
enum Users{
    NormalUser = 'normal',
    PayedUser = 'payed',
    AminUser = 'admin',
    MegaUser = 'mega',
}
```

## Ejemplo del beneficio de enums
Mostrare un ejemplo claro y sencillo del potencial de typescript:

``` typescript
enum Users{
    NormalUser = 'normal',
    PayedUser = 'payed',
    AminUser = 'admin',
    MegaUser = 'mega',
}

const myUser = Users.AdminUser;

// SIN TYPESCRIPT
if (myUser === "admin") {

}
console.log(myUser);
```
+ Vamos a usar la filosofia de typescript, mira si el admin ya no es admin, luego deberiamos cambiar en todas las variables este codigo, por todos los lugares del proyecto.

``` typescript
const myUser = Users.AdminUser;

// CON TYPESCRIPT
if (myUser === Users.AdminUsers) {

}
console.log(myUser);
```
En un futuro para mantenimiento, podemos cambiarlo cuando sea necesario, ya que esos datos sensibles estan centralizados.

## Forense: Las Tripas de un enum
vamos a ver bajo el capo, como es que un enum puede funcionar, ya que las Listas no existen en Javascript.

``` javascript
var Users:
(function (Users) {
    Users["NormalUser"] = "normal";
    Users["PayedUser"] = "payed";
    Users[Users["AdminUser"] = 5] = "AdminUser";
    Users["MegaUser"] = "mega";
})(Users || (Users = {}));

var myUser = Users.AdminUser;
if(myUser === Users.AdminUser) {

}
console.log(myUser);
```