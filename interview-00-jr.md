# Retos de programacion para principiantes - Parte 1

Dada una lista enlazada de longitud n, debemos reordenar los nodos de tal forma que sigan el siguiente patrón: 
```python
[0, n-1, 1, n-2, 2, n-3, ...]
```

### Ejemplo de Entrada y Salida:

Ejemplo 1
```python
Entrada: head = [2,4,6,8]
Salida: [2,8,4,6]
```
Ejemplo 2
```python

Entrada: head = [2,4,6,8,10]
Salida: [2,10,4,8,6]
```

### Enfoque para Resolver el Problema
Para resolver este problema, podemos dividirlo en tres pasos clave:

1. Encontrar la mitad de la lista enlazada: Usamos el método de tortuga y liebre (slow and fast pointers) para encontrar el nodo central.

2. Invertir la segunda mitad de la lista: Una vez que encontramos la mitad, invertimos los nodos restantes.

3. Intercalar ambas mitades: Tomamos nodos alternadamente de la primera y la segunda mitad invertida para lograr el orden deseado.

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

    def __str__(self):
        result = []
        current = self
        while current:
            result.append(str(current.val))
            current = current.next
        return " -> ".join(result)


def reorderList(head):
    if not head or not head.next:
        return
    
    # Paso 1: Encontrar la mitad de la lista
    slow, fast = head, head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    
    # Paso 2: Invertir la segunda mitad
    prev, curr = None, slow.next
    slow.next = None  # Separar la primera mitad
    while curr:
        temp = curr.next
        curr.next = prev
        prev = curr
        curr = temp
    
    # Paso 3: Intercalar las dos mitades
    first, second = head, prev
    while second:
        temp1, temp2 = first.next, second.next
        first.next, second.next = second, temp1
        first, second = temp1, temp2
```

Y cuentame, ya sabias como resolver este problema?
