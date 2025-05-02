# Actividad 8: El patrón Arrange-Act-Assert

## Ejercicios:
### Ejercicio 1: Método para vaciar el carrito
Implementa en la clase Carrito un método llamado vaciar() que elimine todos los items del carrito. 
![alt text](Img/10.png)

Luego, escribe pruebas siguiendo el patrón AAA para verificar que, al vaciar el carrito, la lista de items quede vacía y el total sea 0.
![alt text](Img/11.png)

Testeo:
![alt text](Img/11.png)

### Ejercicio 2: Descuento por compra mínima

Amplía la lógica del carrito para aplicar un descuento solo si el total supera un monto determinado. Por ejemplo, si el total es mayor a $500, se aplica un 15% de descuento.
![alt text](Img/12.png)

Sus pruebas unitarias:
![alt text](Img/13.png)


### Ejercicio 3: Manejo de stock en producto
Modifica la clase Producto para que incluya un atributo stock (cantidad disponible). 
![alt text](Img/14.png)
![alt text](Img/15.png)

Luego, actualiza el método agregar_producto en Carrito para que verifique que no se agregue una cantidad mayor a la disponible en stock. Si se intenta agregar más, se debe lanzar una excepción.
![alt text](Img/16.png)

Sus pruebas unitarias:
![alt text](Img/17.png)

### Ejercicio 4: Ordenar items del carrito
Agrega un método en Carrito que devuelva la lista de items ordenados por un criterio (por ejemplo, por precio unitario o por nombre del producto).
![alt text](Img/18.png)

Sus pruebas unitarias:
![alt text](Img/19.png)

### Ejercicio 5: Uso de Pytest Fixtures
Refactoriza las pruebas para que utilicen fixtures de Pytest, de modo que se reutilicen instancias comunes de Carrito o de productos.
![alt text](Img/20.png)

### Ejercicio 6: Pruebas parametrizadas
![alt text](Img/21.png)
#
![alt text](Img/22.png)

