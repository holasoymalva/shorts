# Retos de programacion para principiantes

**Ejercicio** : Escribe una función en JavaScript que tome un número entero positivo y devuelva true si el número es un número de Armstrong, o false si no lo es.

Un número de Armstrong es un número en el que la suma de sus dígitos elevados a la potencia de la cantidad de dígitos en el número es igual al número mismo.

### Ejemplo de Entrada y Salida:

``` javascript
console.log(esNumeroArmstrong(153)); // Output: true
console.log(esNumeroArmstrong(9474)); // Output: true
console.log(esNumeroArmstrong(123)); // Output: false
```

### Enfoque para Resolver el Problema

Este problema puede resolverse mediante programación dinámica para optimizar su ejecución.

```javascript
function esNumeroArmstrong(num) {
    // Convertimos el número en una cadena para contar la cantidad de dígitos
    let strNum = num.toString();
    let numDigitos = strNum.length;
    let suma = 0;

    // Usamos un bucle para recorrer cada dígito, elevarlo a la potencia de la cantidad de dígitos y sumarlo
    for (let i = 0; i < numDigitos; i++) {
        suma += Math.pow(parseInt(strNum[i]), numDigitos);
    }

    // Comparamos la suma con el número original
    return suma === num;
}
```

Este reto de programación es excelente para principiantes, ya que pone en práctica el uso de bucles, conversión de datos y manipulación de números en JavaScript. Resolver ejercicios como este te ayudará a mejorar tu lógica y prepararte para desafíos más avanzados.

Y cuentame, ya sabias como resolver este problema?
