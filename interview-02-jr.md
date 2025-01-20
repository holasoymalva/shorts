# Este es uno de los problemas de programacion mas dificiles de resolver.
Ya que solo 1 de cada 10 Juniors logra resolver esta Prueba Técnica en las Entrevistas de Trabajo

**Problema** : Dado un array de números enteros, encuentra la subsecuencia creciente más larga (LIS, por sus siglas en inglés) en la lista.

### Ejemplo de Entrada y Salida:

``` javascript
console.log(longestIncreasingSubsequence([10, 9, 2, 5, 3, 7, 101, 18])); // Output: 4
console.log(longestIncreasingSubsequence([0, 1, 0, 3, 2, 3])); // Output: 4
console.log(longestIncreasingSubsequence([7, 7, 7, 7])); // Output: 1
```

### Enfoque para Resolver el Problema

Este problema puede resolverse mediante programación dinámica para optimizar su ejecución.

```javascript
function longestIncreasingSubsequence(arr) {
    if (arr.length === 0) return 0;
    // Creamos un array dp donde cada posición almacena la longitud de la subsecuencia creciente más larga hasta ese índice    
    let dp = new Array(arr.length).fill(1);

    // Usamos dos bucles anidados para comparar elementos previos y actualizar la longitud máxima 
    for (let i = 1; i < arr.length; i++) {
        for (let j = 0; j < i; j++) {
            if (arr[i] > arr[j]) {
                dp[i] = Math.max(dp[i], dp[j] + 1);
            }
        }
    }

    // Retornamos el valor máximo en dp
    return Math.max(...dp);
}
```
Este enfoque de programación dinámica reduce significativamente el tiempo de ejecución en comparación con una solución de fuerza bruta.

Y cuentame, ya sabias como resolver este problema?
