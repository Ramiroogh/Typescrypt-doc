En TypeScript, los arrays pueden contener elementos de un solo tipo o de varios tipos, dependiendo de cómo los declares. Aquí tienes 10 ejemplos de tipos de arrays en TypeScript:

1. **Array de números:**
   ```typescript
   let numeros: number[] = [1, 2, 3, 4, 5];
   ```

2. **Array de cadenas:**
   ```typescript
   let palabras: string[] = ["hola", "typescript", "arrays"];
   ```

3. **Array de booleanos:**
   ```typescript
   let booleanos: boolean[] = [true, false, true];
   ```

4. **Array de objetos:**
   ```typescript
   interface Persona {
     nombre: string;
     edad: number;
   }

   let personas: Persona[] = [
     { nombre: "Juan", edad: 25 },
     { nombre: "María", edad: 30 }
   ];
   ```

5. **Array de cualquier tipo (any):**
   ```typescript
   let cualquierCosa: any[] = [1, "dos", true, { key: "value" }];
   ```

6. **Array de tuplas:**
   ```typescript
   let tupla: [string, number] = ["typescript", 2023];
   let arrayDeTuplas: [string, number][] = [["uno", 1], ["dos", 2]];
   ```

7. **Array de tipos unión:**
   ```typescript
   let union: (string | number)[] = ["hola", 42, "typescript"];
   ```

8. **Array de tipos intersección:**
   ```typescript
   type A = { a: number };
   type B = { b: string };
   let interseccion: (A & B)[] = [{ a: 1, b: "dos" }, { a: 2, b: "tres" }];
   ```

9. **Array de tipos personalizados:**
   ```typescript
   type DiaLaboral = "Lunes" | "Martes" | "Miércoles" | "Jueves" | "Viernes";
   let diasLaborales: DiaLaboral[] = ["Lunes", "Miércoles", "Viernes"];
   ```

10. **Array de funciones:**
    ```typescript
    let funciones: ((x: number) => number)[] = [
      (x) => x * 2,
      (x) => x + 5,
      (x) => x - 3
    ];
    ```

Estos ejemplos muestran diversas formas en las que puedes declarar y utilizar arrays en TypeScript, aprovechando las capacidades de tipado estático del lenguaje.