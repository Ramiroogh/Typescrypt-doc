# Diferencia en la sintaxis: () y {}

+ Ejemplo muy comun:
``` typescript
FC<CardReviewProps> = ( {} ) => (
)
y esto? FC<CardReviewProps> = ( {} ) => {
}
```

La diferencia entre las dos sintaxis que has proporcionado está en cómo se maneja el cuerpo de la función de flecha. Ambas son válidas y ambas formas hacen prácticamente lo mismo, pero hay una diferencia sutil:

1. **Con Paréntesis:**
   ```tsx
   const Component: FC<CardReviewProps> = () => (
     // cuerpo de la función
   );
   ```

2. **Con Llaves:**
   ```tsx
   const Component: FC<CardReviewProps> = () => {
     // cuerpo de la función
   };
   ```

La principal diferencia está en cómo JavaScript interpreta el bloque de código:

- Con paréntesis `()`, JavaScript asume que lo que sigue es una expresión y automáticamente retorna el valor de esa expresión. En este caso, retorna el JSX sin necesidad de una declaración `return`.

- Con llaves `{}`, se espera que uses la palabra clave `return` explícitamente si deseas devolver un valor. Si no usas `return`, se devuelve `undefined` de forma implícita.

En términos de React y JSX, ambas formas son comúnmente utilizadas y aceptadas. La elección entre ellas a menudo se reduce a la preferencia del desarrollador o al estilo de codificación del equipo. Algunos desarrolladores prefieren la concisión de la sintaxis con paréntesis, mientras que otros prefieren la claridad de las llaves y la capacidad de incluir múltiples declaraciones dentro del cuerpo de la función sin necesidad de una declaración `return`. En general, puedes elegir la forma que encuentres más legible y cómoda para tu código.