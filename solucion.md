### Correcciones del diseño 1

1. **Modificar la relación entre `Espacio` y `Reserva`**  
   - Cambiamos la composición por una agregación o asociación simple para evitar que la eliminación de una reserva afecte al espacio.

2. **Especificar correctamente el tipo de lista en `GestorReservas`**  
   - Definir `List<Reserva> reservas` en lugar de `list reservas` para hacer explícita la estructura de datos utilizada.

3. **Modificar el parámetro de `cancelarReserva`**  
   - En lugar de `cancelarReserva(Espacio)`, debe ser `cancelarReserva(Reserva)` para identificar correctamente la reserva que se quiere cancelar.

4. **Agregar un identificador único a `Reserva`**  
   - Incluir un campo `+int id` en `Reserva` para facilitar la gestión de reservas.

5. **Representar de manera clara la relación entre `GestorReservas` y `Reserva`**  
   - Indicar que `GestorReservas` administra instancias de `Reserva` mediante su lista de reservas.


### Correcciones del diseño 2

1. **Revisar la relación entre `Espacio` y `Reserva`**  
   - `Reserva` tiene un puntero a `Espacio`, lo que indica agregación, pero el diagrama usa composición (rombo lleno), lo que implica que una reserva no puede existir sin un espacio. Hay que decidir si realmente se necesita composición o si la agregación es suficiente.  

2. **Especificar el tipo de lista en `GestorReservas`**  
   - En lugar de solo poner `list reservas`, es mejor escribir `List<Reserva> reservas` para dejar claro el tipo de datos.  

3. **Corregir el parámetro de `cancelarReserva`**  
   - No tiene sentido que se cancele una reserva pasando un `Espacio`, debería ser `cancelarReserva(Reserva)` para identificar correctamente qué reserva se quiere eliminar.  

4. **Agregar un identificador en `Reserva`**  
   - Sería útil incluir un `id` en `Reserva` para facilitar su gestión. Esto ayudaría a buscar, modificar o cancelar reservas sin depender de la combinación de `Espacio` y `duracion`.  

5. **Aclarar la relación entre `GestorReservas` y `Reserva`**  
   - No queda claro si `GestorReservas` maneja reservas de varios espacios o solo de uno. Si maneja múltiples, podría ser útil agregar una referencia a `Espacio` dentro de `Reserva`.  

6. **Mejorar la función `calcularCosto()`**  
   - Para que `calcularCosto()` funcione bien, debería asegurarse de que `Espacio.tarifa` sea accesible desde `Reserva`, ya sea haciendo `tarifa` pública o agregando un método `getTarifa()`.  


