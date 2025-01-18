# 9 de cada 10 juniors fallan esta prueba tecnica en las entrevistas de trabajo. 

**Problema** : Dado un array de números enteros, encuentra el primer número que no se repite en la lista. Si todos los números se repiten, devuelve `null`.

### Ejemplo de Entrada y Salida:

``` javascript
console.log(primerNoRepetido([4, 5, 1, 2, 0, 4, 5, 1, 2])); // Output: 0
console.log(primerNoRepetido([7, 7, 3, 3, 5, 5])); // Output: null
```

### Enfoque para Resolver el Problema

Para resolver este problema, necesitamos encontrar el primer número único en el array. Podemos hacerlo de varias maneras, pero veremos dos enfoques eficientes.

```javascript
function primerNoRepetido(arr) {
    // Creamos un objeto contador para registrar la frecuencia de cada número en el array
    let contador = {};

    // Recorremos el array y contamos cuántas veces aparece cada número
    for (let num of arr) {
        contador[num] = (contador[num] || 0) + 1;
    }

    // Volvemos a recorrer el array para encontrar el primer número cuya frecuencia sea 1
    for (let num of arr) {
        if (contador[num] === 1) {
            return num;
        }
    }

    // No hay que olvidar que si no encontramos ninguno, retornamos null
    return null;
}
```

Y cuentame, ya sabias como resolver este problema?
