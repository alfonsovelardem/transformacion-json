# transformacion-json
Transformación de estructura JSON en PHP

Este repositorio contiene un algoritmo que transforma un JSON a un formato de salida especifico.

### Descripcion del algoritmo

El algoritmo implementa una transformacion de datos json.

1. **Inicialización**
    * Se inicializan las variables temporales (`$nombre`, `$apellido`) como cadenas vacías (`''`).
    * Se utiliza la función **`isset()`** (el equivalente a un acceso seguro en PHP) para verificar que las claves anidadas existan, previniendo errores si algún campo está ausente (`cliente` u `orden`).


2. **Mapeo y renombrado de la orden**
    * **Renombrado:** El campo de entrada `orden.id` se mapea a la propiedad de salida **`orderId`**. Si falta, se asigna **`NULL`**.
    * **Renombrado:** El campo de entrada `orden.monto` se mapea a la propiedad de salida **`total`**. Si falta, se asigna `0` como valor por defecto.

3. **Extracción y combinación del Cliente**
    * Se extraen los campos `cliente.nombre` y `cliente.apellido` de forma segura.
    * **Combinación de Datos:** Se concatenan el nombre y el apellido. Se aplica la función **`trim()`** para eliminar espacios sobrantes, asegurando un formato limpio.
    * El resultado combinado se asigna a la propiedad de salida **`customerName`**.

4.  **Generación de Salida:**
    * Finalmente, se retorna el objeto de salida con las tres propiedades en el formato deseado.

### Analisis de Complejidad

El diseño prioriza la eficiencia para entornos con alto volumen de transformaciones.

| Aspecto | Complejidad | Justificación |
| :--- | :--- | :--- |
| **Tiempo ($T$)** | **$O(1)$ (Constante)** | El algoritmo realiza un número fijo y predecible de operaciones. El tiempo de ejecución no depende del tamaño total del JSON de entrada. |
| **Espacio ($S$)** | **$O(1)$ (Constante)** | La memoria utilizada es constante, limitada solo al objeto de salida y variables temporales, cuyo tamaño no crece con el volumen de datos. |

## Casos de prueba.

### Caso 1 (Completo)
    Entrada:
    {
        "cliente": {"nombre": "Andrea", "apellido": "Flores"},
        "orden": {"id": 456, "monto": 99.99}
    }

    Salida:

    {
        "orderId": 456,
        "customerName": "Andrea Flores",
        "total": 99.99
    }

### Caso 2 (Datos faltantes)
    Entrada:
    {
        "cliente": {"nombre": "Raúl"}, 
        "orden": {"monto": 750.00}
    }

    Salida:
    {
        "orderId": NULL,
        "customerName": "Raúl",
        "total": 750.00
    }

### Archivos del Pseudocodigo

    *`transformacion_json.pseudocode`
    