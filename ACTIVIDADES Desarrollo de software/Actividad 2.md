
# Evaluacion Teorica


## 1. Importancia de la IaC, Contenedores,  ubernetes, Observabilidad y CI/CD en la Entrega Agil y Confiable de Software

Estas tecnologias nos permiten automatizar de manera eficiente, reduciendo errores y mejorando la escalabilidad de los sistemas.

* **Infraestructura como Codigo (IaC):** Automatiza la infraestructura, lo que ayuda a no estar haciendo configuraciones manuales que muchas veces consumen tiempo.

* **Contenedores:** Su funcion es empaquetar aplicaciones y tambien sus dependencias en entornos aislados, lo que ayuda mucho en entornos de desarrollo, testeo y produccion.

* **Observabilidad:** Aqui nos permite monitorear y depurar sistemas usando logs, metricas y trazas, su aplicacion es importante en la detencion rapida de problemas o para optimizar el rendimiento de un sistema.

* **CI/CD:** Aqui es donde se automatiza la integracion y entrega de software, lo que reduce el tiempo de despliegue, ya que automatiza pruebas. (Los depliegues son controlados)



## Riesgos y Desafios

Como hemos visto esas herramientas son muy utiles pero tambien vienen con riesgos, aqui mencionaremos algunos:

* **Sobrecarga Cognitiva:** La variedad de herramientas puede ser un poco pesada o abrumadora para los equipos de desarrollo lo que les va consumir tiempo y esfuerzo hasta que consigan acostumbrarse a su uso.

* **Capacitacion:** Para adoptar estas tecnicas no son solo ver tutoriales, como hemos visto DevOps no es una herramienta o un conjunto de estas, es una *cultura* la cual de debe implementar en todo los equipos para que funcionen como tal, este es un gran desafio para muchas organizaciones.

* **Configuracion de Seguridad:** Al automatizar y usar el despliegue continuo podemos crear codigo con vulnerabilidades si no se aplican las buenas practicas de seguridad desde el inicio, por eso es importate configurar el control de acceso y monitoriarlos por si hay alguna amenaza.

#

# 2. Discusion de Grupo

## Ejemplos de Empresas:
Empresas como Google, Amazong y Netflix usan las herramientas ya mencionadas para manejar sus volumenes altos de datos y tambien para sus cambios o actualizaciones, sin afectar su aplicacion. Netflix por ejemplo usa Kubernetes y CI/CD para desplegar cambios diarios sin que afecte a sus usuarios. Google por su lado usa IaC para administrar sus infraestructuras.

#

# 3. Trabajo colaborativo

## Flujo teorico:

1. **Commit y Control de versiones:** Un desarrollador realiza un commit en un repositorio como Git

2. **Infraestructura como Codigo:** Usamos Terraform o AWS (Amazong Web Service) para desplegar los recursos en la nube, luego se configura los permisos y seguridad con herramientas como AWS IAM o HashiCorp Vault.

3. **Construccion y Despliegue de Contenedores:** CI/CD construye una imagen en Doker y la sube a un registro de contenedores, y se actualiza el manifiesto de kubernetes con a nueva version.

4. **Orquestacion con Kubernetes:** Kubernetes despliega los contenedores en un cluster

5. **Monitoreo con Prometheus y Grafana:** Prometheus recoge metricas del cluster y las aplicaciones para luego visualizarla en dashboard de Grafana en tiempo real.

## Diagrama

![alt text](Diagrama-1.png)