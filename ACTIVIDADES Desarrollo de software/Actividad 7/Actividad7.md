# Actividad7: Pruebas BDD con behave en español
![alt text](<Imagenes act7/10.png>)

#### Instalacion:
1. Clona el repositorio o descarga el código fuente:
![alt text](<Imagenes act7/11.png>)

2. Crea y activa un entorno virtual llamado act9:
![alt text](<Imagenes act7/12.png>)

3. Instala las dependencias necesarias:
![alt text](<Imagenes act7/13.png>)



## Ejercicios
Estructura del proyecto

```
.
├── features
│   ├── belly.feature
│   ├── environment.py
│   └── steps
│       └── steps.py
├── src
│   ├── belly.py
│   ├── clock.py
│   └── __init__.py
├── tests
│   ├── test_belly.py
│   └── __init__.py
├── requirements.txt
```
* **features:** Contiene los archivos relacionados con Behave.
    * **belly.feature:** Archivo que describe las características y escenarios en lenguaje Gherkin.
    ![alt text](<Imagenes act7/14.png>)

    * **environment.py:** Archivo de configuración para inicializar el contexto de Behave.
    ![alt text](<Imagenes act7/15.png>)
    * **steps:** Carpeta que contiene las definiciones de los pasos.
        * **steps.py:** Implementación de los pasos definidos en belly.feature.
        ![alt text](<Imagenes act7/16.png>)

* **src:** Contiene el código fuente del proyecto.
    * **belly.py:** Implementación de la clase Belly.
    ![alt text](<Imagenes act7/17.png>)
* **README.md:** Este archivo de documentación.

## Ejecutar pruebas:
Utilizamos el comando `behave`:
![alt text](<Imagenes act7/18.png>)

## Ejercicio 1: Añadir soporte para minutos y segundos en tiempos de espera

1. Modificamos la función que maneja el tiempo de espera en belly_steps.py (o donde parsees el tiempo) para que acepte:
    * "1 hora y 30 minutos"
    * "90 minutos"
    * "3600 segundos"
    * Variaciones que incluyan segundos (por ejemplo, "1 hora, 30 minutos y 45 segundos").
![alt text](<Imagenes act7/19.png>)

2. Implementa un escenario de prueba en Gherkin (belly.feature) que valide que el estómago gruñe o no según estas variaciones de tiempo.
![alt text](<Imagenes act7/20.png>)

3. Considera también crear pruebas unitarias con Pytest para la lógica de parsing (función que convierte el texto de tiempo en horas decimales).
![alt text](<Imagenes act7/21.png>)
![alt text](<Imagenes act7/22.png>)

4. En un entorno DevOps:
    * Agrega la ejecución de behave y pytest en tu pipeline de CI/CD, de modo que al hacer push de los cambios se ejecuten automáticamente las pruebas.
![alt text](<Imagenes act7/23.png>)

## Ejercicio 2: Manejo de cantidades fraccionarias de pepinos

1. Modifica el sistema (la clase Belly y los steps en Behave) para que acepte entradas como `"0.5"`, `"2.75"`.
![alt text](<Imagenes act7/24.png>)

2. Implementa un nuevo escenario en Gherkin donde se ingiera una cantidad fraccionaria y verifica el comportamiento.
![alt text](<Imagenes act7/25.png>)

3. Valida que el sistema lance una excepción o error si se ingresa una cantidad negativa de pepinos.
![alt text](<Imagenes act7/26.png>)
![alt text](<Imagenes act7/27.png>)

4. Pruebas unitarias:
    * Cubre el caso de pepinos fraccionarios en test_belly.py.
![alt text](<Imagenes act7/28.png>)   

## Ejercicio 3: Soporte para idiomas múltiples (Español e Inglés)

1. Modifica el parsing de tiempo para que reconozca palabras clave en inglés, además de español (por ejemplo, `"two hours"`, `"thirty minutes"`).
![alt text](<Imagenes act7/29.png>)

2. Escribe al menos dos escenarios de prueba en Gherkin que usen tiempos en inglés.

![alt text](<Imagenes act7/30.png>)

