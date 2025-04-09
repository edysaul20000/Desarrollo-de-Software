# **Actividad 5:** Explorando diferentes formas de fusionar en Git

Hay 3 metodos para fusionar ramas y  son: Fast-Forward, no Fast-Forward y squash.

#### **1. Fast-forward: Mantener un historial limpio y lineal**
Es la opcion predeterminada y mas simple cuando no se han realizado commits en la rama principal desde su creacion. El historial de commits permanece lineal. Es ideal 	para proyectos pequeños donde no se realizan multiples contribuciones paralelas. 


#### **2. No-fast-forward: Preservar el contexto de los cambios**
A diferencia del anterior, este crea un commit de fusion que preserva explicitamente  el momento y el contexto en el que se integraron las ramas. 
Es mas util en proyecto grandes donde los desarrolladores trabajan simultaneamente.
Al realizar un commit de fusion no-fast-forward se tiene 2 parents commit, uno es la rama origen y el otro la rama destino, con este enfoque se puede revisar los historiales de manera eficiente, para saber cuando y porque se unieron a la rama principal.
El continuo uso de esta fusion puede desordenar el historial lo que dificulta la lectura, solo deben realizarse en fusiones importantes.


#### **3. Squash: Condensar cambios para una rama principal limpia**
Este metodo esta orientado en mantener el historial limpio al integrar las rama, esta tecnica agarra todos los commits de la rama principal y los aplasta en un solo commit antes de fusionarlos con la rama principal. Es ideal en proyecto donde se prioriza la simplicidad y claridad del codigo.
Este metodo es comun en metodologias agiles, CI/CD y DevOps, donde se busca integrar  frecuentemente en ciclos cortos.
La desventaja esque al aplastar los commits se pierde los detalles del historial, como los cambios realizados en las ramas, esto dificulta mucho si se quiere entender 	el cambio del codigo en un futuro.

#

### **Ejemplos**

#### **1. Fusión Fast-forward (git merge --ff)**
###### Crear un nuevo repositorio
![alt text](E10.png)

###### Crear y cambiar a una nueva rama 'add-description'
![alt text](E11.png)
###### Ver el historial lineal
![alt text](E12.png)

#

#### **2. Fusión No-fast-forward (git merge --no-ff)**

###### Crear un nuevo repositorio
![alt text](E20.png)

###### Agregar un archivo inicial en la rama principal (main)
![alt text](E21.png)

###### Crear y cambiar a una nueva rama 'add-feature' y hacer cambios en la nueva rama y comitearlos
![alt text](E22.png)

###### Cambiar de vuelta a la rama 'main' y realizar una fusión no-fast-forward
![alt text](E23.png)

###### Ver el historial
![alt text](E24.png)

#

#### **3. Fusión squash (git merge --squash)**

###### Crear un nuevo repositorio
![alt text](E30.png)
###### Agregar un archivo inicial en la rama principal (main)
![alt text](E31.png)
###### Crear y cambiar a una nueva rama 'add-basic-files'
![alt text](E32.png)
###### Hacer algunos cambios y comitearlos
![alt text](E33.png)
###### Cambiar de vuelta a la rama 'main' y realizar la fusión squash
![alt text](E34.png)
###### Para completar la fusión squash, realiza un commit:
![alt text](E35.png)

#

### **Ejercicios**

### 1. Clona un repositorio Git con múltiples ramas.
Identifica dos ramas que puedas fusionar utilizando **git merge --ff**.
Haz el proceso de fusión utilizando **git merge --ff**. 
Verifica el historial con git log --graph --oneline.

![alt text](I10.png)

**Pregunta: ¿En qué situaciones recomendarías evitar el uso de git merge --ff? Reflexiona sobre las desventajas de este método.**

Evita **--ff** cuando quieras preservar el historial de que hubo una rama separada ya que es util en equipos o para identificar que feature se desarrolló por separado.


### 2. Simula un flujo de trabajo de equipo.

Trabaja en dos ramas independientes, creando diferentes cambios en cada una.
Fusiona ambas ramas con **git merge --no-ff** para ver cómo se crean los commits de fusión.
Observa el historial utilizando git log --graph --oneline.

![alt text](I11.png)
![alt text](I12.png)

**Pregunta: ¿Cuáles son las principales ventajas de utilizar git merge --no-ff en un proyecto en equipo? ¿Qué problemas podrían surgir al depender excesivamente de commits de fusión?**

Unas de las ventajas principales es que preserva la historia y contexto de cada feature lo que es util en trabajo colaborativo, ademas permite hacer revert más fácilmente de un conjunto de cambios.
Pero una desventaja si se usa continuamente es que el historial se pone muy ramificado y lleno de merges innecesarios.

### 3. Crea múltiples commits en una rama.
Haz varios cambios y commits en una rama feature.
Fusiona la rama con **git merge --squash** para aplanar todos los commits en uno solo.
Verifica el historial de commits antes y después de la fusión para ver la diferencia.

![alt text](I13.png)
![alt text](I14.png)

**Pregunta: ¿Cuándo es recomendable utilizar una fusión squash? ¿Qué ventajas ofrece para proyectos grandes en comparación con fusiones estándar?**

Es recomendable usar cuando quieres limpiar el historial y no necesitas mantener cada paso de desarrollo. Ideal para PullRequest con muchos commits de prueba o debugging.
Para proyectos grande la ventaja seria evita un historial largo con muchos commits irrelevantes.

#

### Resolver conflictos en una fusión non-fast-forward
 1. **Inicializa un nuevo repositorio:**
![alt text](O10.png)


 2. **Crea un archivo index.html y realiza un commit en la rama main:**
![alt text](O11.png)


 3. **Crea y cambia a una nueva rama feature-update:**
![alt text](O12.png)
 4. **Edita el archivo y realiza un commit en la rama feature-update:**
![alt text](O13.png)

 
 5. **Regresa a la rama main y realiza una edición en el mismo archivo:**
![alt text](O14.png)
 6. **Fusiona la rama feature-update con --no-ff y observa el conflicto:**
![alt text](O15.png)


 7. **Git detectará un conflicto en index.html. Abre el archivo y resuelve el conflicto. Elimina las líneas de conflicto generadas por Git (<<<<<<<, =======, >>>>>>>) y crea la versión final del archivo con ambos cambios:**
![alt text](O16.png)
![alt text](O17.png)
![alt text](O18.png)
 8. **Agrega el archivo corregido y completa la fusión:**
![alt text](O19.png)
![alt text](O20.png)

 9. **Verifica el historial para confirmar la fusión y el commit de resolución de conflicto:**
![alt text](O21.png)

#### Preguntas:

* **¿Qué pasos adicionales tuviste que tomar para resolver el conflicto?**

    Solo tuve que borrar manualmente los signos (<<<<<,======, >>>>)


* **¿Qué estrategias podrías emplear para evitar conflictos en futuros desarrollos colaborativos?**
    La comunicacion es muy importante ya que podemos estar editando el mismo documento y revisar y probar antes de hacer merge.

#

### **Ejercicio:** Comparar los historiales con git log después de diferentes fusiones

1. **Crea un nuevo repositorio y realiza varios commits en dos ramas:**
![alt text](U10.png)
![alt text](U11.png)
![alt text](U12.png)

2. **Fusiona feature-1 usando fast-forward:**
![alt text](U13.png)

3. **Fusiona feature-2 usando non-fast-forward:**
![alt text](U14.png)
![alt text](U15.png)
![alt text](U16.png)
![alt text](U17.png)
4. **Realiza una nueva rama feature-3 con múltiples commits y fusiónala con squash:**
![alt text](U18.png)

5. **Compara el historial de Git:**
* Historial Fast-forward:
![alt text](U19.png)
* Historial Non-fast-forward:
![alt text](U20.png)

* Historial con Squash:
![alt text](U21.png)
![alt text](U22.png)
### **Preguntas:**

* **¿Cómo se ve el historial en cada tipo de fusión?**
    * **A. Fast-Forward Merge (--ff):**
    El historial se ve lineal como si los commits de feature-1 siempre hubiera estado en el master(main).
    * **B. Non-Fast-Forward Merge (--no-ff):**
    Aqui se preserva el historial de la rama original y muestra el historial como una fusion.
    * **C. Squash Merge (--squash):**
    Este combina todos los commits de la rama en uno solo, como si el el trabajo de la rama feature-3 se hubiese hecho en un solo commit.
    

* **¿Qué método prefieres en diferentes escenarios y por qué?**

| **Tipo de Fusion** | **Uso** |
|----------|----------|
| Fast-Forward | Cuando trabajo solo en una rama pequeña que no se entrecruza con otras.  |
| Non-Fast-Forward    |En trabajo colaborativo o cuando quiero dejar registro claro de cada feature. |
| Squash Merge    | Cuando quiero limpiar commits de pruebas o unir muchos cambios pequeños en uno solo. |


#

### **Ejercicio:** Usando fusiones automáticas y revertir fusiones

1. **Inicializa un nuevo repositorio y realiza dos commits en main:**

![alt text](U23.png)

2. **Crea una nueva rama auto-merge y realiza otro commit en file.txt:**
![alt text](W11.png)


3. **Vuelve a main y realiza cambios no conflictivos en otra parte del archivo:**
![alt text](W12.png)


4. **Fusiona la rama auto-merge con main:**
![alt text](W13.png)
![alt text](W14.png)

5. **Git debería fusionar los cambios automáticamente sin conflictos.**

6. **Revertir la fusión: Si decides que la fusión fue un error, puedes revertirla:**
![alt text](W15.png)
![alt text](W17.png)

7. **Verifica el historial:**
![alt text](W16.png)


### **Preguntas:**
* **¿Cuándo usarías un comando como git revert para deshacer una fusión?**

    Cuando ya realice un merge y lo confirme y necesito revertir los cambios sin borrar el historial.
* **¿Qué tan útil es la función de fusión automática en Git?**

    Nos permite combinar ramas rapidamente sin conflictos cuando los cambios no se sobreponen, es mas rapido lo que nos ahorra tiempo y es mas sencillo el trabajo.

    #

    ### **Ejercicio:** Fusión remota en un repositorio colaborativo

1. **Clona un repositorio remoto desde GitHub o crea uno nuevo:**
![alt text](X10.png)


2. **Crea una nueva rama colaboracion y haz algunos cambios:**

![alt text](X11.png)

3. **Empuja los cambios a la rama remota:**
![alt text](X12.png)


4. **Simula una fusión desde la rama colaboracion en la rama main de otro colaborador. (Puedes usar la interfaz de GitHub para crear un Pull Request y realizar la fusión).**

![alt text](X13.png)

![alt text](X14.png)

![alt text](X15.png)


### **Preguntas:**

* **¿Cómo cambia la estrategia de fusión cuando colaboras con otras personas en un repositorio remoto?**

    Se usan pull requests para revisión y es común actualizar con git pull --rebase para evitar conflictos y mantener un historial limpio.


* **¿Qué problemas comunes pueden surgir al integrar ramas remotas?**

    * Conflictos de código por cambios en las mismas líneas de los diferentes colaboradores.

    * Commits duplicados si se mezclan merge y rebase.

    * Historial enredado o dificil de entender si no se sigue una estrategia clara de fusión.

# 
### **Ejercicio final:** flujo de trabajo completo

Configuraremos un proyecto simulado:

* **Creamos un proyecto con tres ramas: main, feature1, y feature2 y realiza varios cambios en feature1 y feature2 y simula colaboraciones paralelas.**
![alt text](Y10.png)
![alt text](Y11.png)
* **Realiza fusiones utilizando diferentes métodos:**

    * Fusiona feature1 con main utilizando **git merge --ff.** Y  Fusiona feature2 con main utilizando **git merge --no-ff.**
![alt text](Y12.png)

    * Haz una rama adicional llamada feature3 y aplasta sus commits utilizando **git merge --squash.**
![alt text](Y13.png)
![alt text](Y14.png)

**Analizis de los commits:**

![alt text](Y15.png)

