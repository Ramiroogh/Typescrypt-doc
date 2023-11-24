Podemos crear un tipo, que herede o se base en otro tipo existente, y ademas podemos agregarle un valor mas pordefecto, aqui un ejemplo:

## Union Types

``` typescript
type User = {
    id: string;
};

type Admin = User & { token: string };

const myAdmin: Admin = {

}
```
Tambien podemos unir dos tipos, a partir de crear un tipo nuevo
``` typescript
type Person = {
    name: string;
    age: number;
};
type User = {
    id: string;
};

// Nuevo Tipo UNIDO
type Admin = User & Person;
```
## Unir Type con Interface
Tambien podemos unir un Type con un Interface:
``` typescript
type Person = {
    name: string;
    age: number;
};
interface Employee extends Person {
    name: '',
    age: 40,
    charge: '',
}

// Nuevo Tipo UNIDO con (TYPE & INTERFACE)
type Admin = User & Employee;
```

## Conclusion
Des estas maneras, podemos lograr una extension de un type con otro type, similar a una especie de Herencia.