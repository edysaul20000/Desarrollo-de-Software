# Actividad: Introduccion a Git - Conceptos basicos y operaciones esenciales


### **git config:** Preséntate a Git
![alt text](C1.png)

### **git init:** Donde comienza tu viaje de código
![alt text](C2.png)

### **git add:** Preparando tu código
![alt text](C3.png)

### **git commit:** registra cambios
![alt text](C4.png)
### **git log:** Recorrer el árbol de commits
![alt text](C5.png)

## Trabajar con ramas: La piedra angular de la colaboración
![alt text](C6.png)

### **git checkout/git switch:** Cambiar entre ramas
![alt text](C7.png)

### **Ejemplos adicionales**
![alt text](C8.png)

### **Crear una rama desde un commit específico**
![alt text](C9.png)

### **git merge :** Fusionando ramas
![alt text](C10.png)

### **git branch -d:** Eliminando una rama
![alt text](C11.png)

### Preguntas
1. **¿Cómo te ha ayudado Git a mantener un historial claro y organizado de tus cambios?**

    Mediante lo comandos vistos puedo ver los cambios que eh realizado con sus descripciones para poder ver el proposito de cada cambio.

2. **¿Qué beneficios ves en el uso de ramas para desarrollar nuevas características o corregir errores?**

    Bueno las ramas nos permiten trabajar en nuevas funcionalidades sin que afecten el resto de codigo, y asi cada integrante del equipo puede tener su rama propia y luego despues de la verificacion unir las ramas.

3. **Realiza una revisión final del historial de commits para asegurarte de que todos los cambios se han registrado correctamente.**

    Ahi en la imagen, gracias al **git log** puedo ver los commits que se hicieron y por quienes.

    ![alt text](C12.png)


4. **Revisa el uso de ramas y merges para ver cómo Git maneja múltiples líneas de desarrollo.**

    Con git podemos manejar varias ramas y al usar **git merge** podemos unirlas pero primero debemos ubicarnos en la rama a la que deseamos fusionar.

    ![alt text](C13.png)
    #
#

# Ejercicios
## **Ejercicio 1:** Manejo avanzado de ramas y resolución de conflictos
1. **Crear una nueva rama para una característica:**
![alt text](E1.10.png)
2. **Modificar archivos en la nueva rama:**
![alt text](E1.20.png)
![alt text](E1.21.png)
3. **Simular un desarrollo paralelo en la rama main:**
![alt text](E1.30.png)
![alt text](E1.31.png)
![alt text](E1.32.png)
4. **Intentar fusionar la rama feature/advanced-feature en main:**
![alt text](E1.40.png)
![alt text](E1.41.png)

5. **Resolver el conflicto de fusión:**
![alt text](E1.50.png)
![alt text](E1.51.png)

6. **Eliminar la rama fusionada:**
![alt text](E1.60.png)


## **Ejercicio 2:** Exploración y manipulación del historial de commits

1. **Ver el historial detallado de commits:**
![alt text](E2.10.png)


2. **Filtrar commits por autor:**
![alt text](E2.20.png)
3. **Revertir un commit:**
![alt text](E2.30.png)
4. **Rebase interactivo:**
![alt text](E2.40.png)
5. **Visualización gráfica del historial:**
![alt text](E2.50.png)
## **Ejercicio 3:** Creación y gestión de ramas desde commits específicos

1. **Crear una nueva rama desde un commit específico:**
![alt text](E3.10.png)
![alt text](E3.11.png)
2. **Modificar y confirmar cambios en la nueva rama:**
![alt text](E3.20.png)
![alt text](E3.21.png)
3. **Fusionar los cambios en la rama principal:**
![alt text](E3.30.png)
4. **Explorar el historial después de la fusión:**
![alt text](E3.40.png)
5. **Eliminar la rama bugfix/rollback-feature:**
![alt text](E3.50.png)

## **Ejercicio 4:** Manipulación y restauración de commits con git reset y git restore

1. **Hacer cambios en el archivo main.py:**
![alt text](E4.10.png)
![alt text](E4.11.png)
2. **Usar git reset para deshacer el commit:**
![alt text](E4.20.png)
3. **Usar git restore para deshacer cambios no confirmados:**
![alt text](E4.30.png)

## **Ejercicio 5:** Trabajo colaborativo y manejo de Pull Requests

1. **Crear un nuevo repositorio remoto:**
![alt text](E5.10.png)
2. **Crear una nueva rama para desarrollo de una característica:**
![alt text](E5.20.png)
3. **Realizar cambios y enviar la rama al repositorio remoto:**
![alt text](E5.30.png)
![alt text](E5.31.png)
4. **Abrir un Pull Request:**
![alt text](E5.40.png)
5. **Revisar y fusionar el Pull Request:**
![alt text](E5.50.png)
6. **Eliminar la rama remota y local:**
![alt text](E5.60.png)
## **Ejercicio 6:** Cherry-Picking y Git Stash

1. **Hacer cambios en main.py y confirmarlos:**
![alt text](E6.10.png)
2. **Crear una nueva rama y aplicar el commit específico:**
![alt text](E6.20.png)
![alt text](E6.21.png)
3. **Guardar temporalmente cambios no confirmados:**
![alt text](E6.30.png)
4. **Aplicar los cambios guardados:**
![alt text](E6.40.png)
5. **Revisar el historial y confirmar la correcta aplicación de los cambios:**
![alt text](E6.50.png)