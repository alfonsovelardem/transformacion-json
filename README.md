# transformacion-json
Transformación de estructura JSON en PHP

Este repositorio contiene un algoritmo que transforma un JSON

## Casos de prueba.

# Caso 1
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

# Caso 2
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

    transformacion_json.pseudocode