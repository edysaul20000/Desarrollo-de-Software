# B. Actividades de investigacion y aplicacion

## 1. Estudio de casos

Aqui presentare 3 casos que encontre que han migrado una parte de su infraestructura a la nube.

### 1.1. Banco Santander
**Motivaciones:** Quizo transformar digitalmente sus servicios bancarios para ogrecer una mejor experiencia y tambien agrego inteligencia artificial y blockchain en sus operaciones.

**Beneficios:** Reduccion de costos y mejora la eficiencia operativa, la migracion fue con el software Gravity.

**Desafios**: Uno de los grandes desafios que enfrenta la organizacion bancaria es garantizar la seguridad y privacidad de los datos de los clientes en la nube. Otro aspecto importante fue el cambio organizacional y la adaptacion de los empleados a las nuevas tecnologias.

### 1.2. Schwarz Group (Lidl y Kaufland)
Una empresa alemana que trabaja en venta, reciclaje y digitalizacion, posee marcas que se comercializan en supermercados, ya sean bebidas, dulces, helados, etc.

**Motivaciones:** La necesidad de la demandas del negocio requirio el uso del almacenamiento en la nube, les obligo a esta cambio ya que dependian tecnologicamente de proveedores estadounidenses.

**Beneficios:** Generaron mas ganacias (1.900 millones de euros en 2023), lo que atrajo las miradas de clientes importantes o marcas como Bayern de Munich debido al enfoque de seguridad y soberania de datos que tenian.

**Desafios:** Tuvieron una gran desventaja al inicio ya que competian con empresas que ya tenian este enfoce y uso de la nube establecidos. Otro desafio fue la de garantizar la seguridad y soberania de los datos ya que en ese momento se vivia en alemania un contexto geopolitico complejo.

### 1.3. Netflix
Netflix en este caso paso de servidores propios a AWS (Amazong Web Service) cloud.
 
 **Motivacion:** Despues de un fallo masivo en su centro de datos en 2008, la empresa decidio dejar su infraestructura *on-premise* y elegir la nube ya que necesitaba la escalabilidad de esta para soportar el crecimiento global y la alta demanda del contenido en streaming.

 **Bneficios:** Al moverse a la nube dejaron de mantener y tener servidores fisicos lo que les redujo los costos de estos. Ahora con la nube tienen mayor flexibilidad y rapidez para lanzar nuevos servicios en mas regiones.

 **Desafios:** La adaptacion de los equipos de ingenieria a un nuevo modelo basado en microservicios puede tomar tiempo ya que es otra tecnologia, otro desafio fue la implementacion de la seguridad de los datos de los usuarios en un entorno completamente distribuido.

 ## 2. Comparativa de modelos de servico

| **Aspecto**                        | **IaaS (Infraestructura como Servicio)** | **PaaS (Plataforma como Servicio)** | **SaaS (Software como Servicio)** |
|-------------------------------------|-----------------------------------------|-------------------------------------|-----------------------------------|
| **Responsable del Hardware**        | Proveedor                               | Proveedor                           | Proveedor                         |
| **Instalación del S.O.**            | Desarrollador/Equipo de Operaciones    | Proveedor                           | Proveedor                         |
| **Gestión de Red y Almacenamiento** | Proveedor                               | Proveedor                           | Proveedor                         |
| **Mantenimiento de Servidores**     | Proveedor                               | Proveedor                           | Proveedor                         |
| **Despliegue de Aplicaciones**      | Desarrollador                           | Desarrollador                       | Proveedor                         |
| **Escalado Automático**             | Desarrollador/Equipo de Operaciones    | Proveedor                           | Proveedor                         |
| **Parches de Seguridad del S.O.**   | Desarrollador/Equipo de Operaciones    | Proveedor                           | Proveedor                         |
| **Administración de Base de Datos** | Desarrollador/Equipo de Operaciones    | Proveedor                           | Proveedor                         |
| **Actualización de Software**       | Desarrollador                           | Proveedor                           | Proveedor                         |
| **Gestión de Usuarios y Accesos**   | Desarrollador/Equipo de Operaciones    | Desarrollador                       | Proveedor                         |

## 3. Armar una estrategia multi-cloud o hibrida

En una empresa mediana con infraestructura dividida entre un centro de datos propio y un proveedor de nube publica necesitamos la migración del 50% de las cargas de trabajo a un segundo proveedor de nube  y evitar la dependencia de un solo proveedor. Para esta estrategia necesitamos una distribucion adecuada y equilibrada de los recursos, tomando en cuenta tanto 1. la ubicacion de los datos como la 2. gestion de redes y tambien tener un plan de 3. contingencia en caso de fallas.

1. La base de datos se mantendra en el proveedor de la nube con mayor presencia actual y para garantizar la continuidad del servicio, se establece una replicacion en tiempo real hacia la segunda nube por si ocurren fallas se podra solucionar, los datos que requieran mas seguridad se conservaran en el centro de datos local con acceso restringido y las copias de seguridad seran distribuidas en ambas nubes.

2. Sobre la configuracion de la red, debe estar con conexiones seguras entre el centro de base de datos y ambos proveedores en la nube usando enlaces que reducen la latencia y mejora la conectividad. Tambien debe tener un sistema que gestiona el trafico de manera dinamica redirigiendo entre proveedores segun la disponibilidad. Asi se podra garantizar que los servicios continuen operando sin interrupciones aun incluso si una de las nubes empieza a tener problemas.

3. Ahora hablaremos sobre el plan de contingencia con un enfoque en el que las aplicaciones se ejecuten de manera simultanea en ambas nubes, para eso utilizaremos contenedores y al orquestador **Kubernetes** para tener una migracios de cargas de trabajo agil sin que el funcionamiento dependa de un solo proveedor, ya que en caso de falla se va a dirigir automaticamente a la nube secundaria y la base de datos va a replicar su informacion, asegurando que no haya perdida de datos a los usuarios finales.

Este enfoque multi-cloud nos va a permitir distribuir la carga de trabajo de manera eficiente, reduciendo los costos y garantizando una solidez operativa. Ademas, la diversidad de proveedores ayuda a la capacidad de respuesta ante fallos y reduce los riesgos asociados al depender de un solo servicio.

## 4. Debate sobre costos
En esta parte vamos a hacer un analisis teorico y comparativo de los tipos de nube desde la perspecitva de costos, escalabilidad, cumplimiento normativo y la facilidad de migracion entre proveedores.

### 4.1. Nube publica
* **Pros:** La nube publica se basa en modelo de costos operativos (OPEX), lo que significa que las empresas pagan por los recursos que consumen, esto es muy beneficioso para los **startups**.

* **Contras:** La desventaja esque tiene responsabilidad compratida y un descuido en la seguridad podria poner en riesgo datos sensibles.

### 4.2. Nube privada
* **Pros:** Este tipo de nuve tiene mayores costos iniciales (CAPEX), ya que necesita infraestructura propia junto con equipos tecnicos para su mantenimiento pero la ventaja es que ofrece mayor control y personalizacion, lo que es favorable para organizaciones que manejan mucha informacion confidencial.

* **Contras:** En cuanto a la flexibilidad, su escalabilidad es limitada por los recursos fisicos disponibles. Cambiar de tecnologia o proveedor en una nube privada puede ser mas controlado pero tiene altos costos de migracion y actualizacion.

### 4.2. Nube Hibrida
* **Pros:** Esta nube combina lo mejor de las 2 nubes anteriores ya que permite mantener los datos sensibles en una nube privada y aprovechan la escalabilidad de la nube publica y en la parte financiera se manejan costos CAPEX y PEX

* **Contras:** No todo es positivo en esta nube ya que a largo plazo requiere gestion compleja en la integracion, redes y seguridad.

### 4.2. Multi-Cloud
* **Pros:** Aqui se usa multiples nubes publicas ya que esta orientada a no depender de un solo proveedor, con multi-cloud nos permite seleccionar el mejor servicio de cada proveedor.

* **Contras:** Los costos operativos pueden aumentar debido a la necesidad de gestionar diferentes entornos y la duplicacion de servicios en distintas plataformas


#

# C. Ejercicio de presentacion de "mini-proyecto"


### 1. Objetivo del sistema: 
El sistema tratara de una plataforma que permita a los usuarios comprar y reservar entradas para eventos deportivos, cines, conciertos y conferencias, todo sera en tiempo real y ofrecera gestion de disponibilidad, procesamiento de pagos y descripcion del evento.

### 2. Seleccion de Modelo de Servicio:
Utilizaremos un modelo PaaS (Plataforma como Servicio), ya que nos permite enfocarnos mas en el desarrollo sin preocuparnos por la administracion de servidores. PaaS tambien nos proporciona herramientas para desplegar la aplicacion con bases de datos y escalabilidad automatica. Una ventaja de utilizar este modelo de servicio en la nube es que reducira los costos operativos al evitar la administracion de infraestructura.

### 3. Tipo de nube:
Implementaremos la nube publica para aprovechar los costos bajos ya que pagaremos solo por el uso y la flexibilidad del escalado automatico, pero necesitaremos controles de seguridad avanzados y tendremos mas gastos en la transferencia de datos.

### 4. Esquema de Escalabilidad:
Para manejar los picos de demanda de la compra de boletos usaremos **autoscaling**, replicando instancias de la aplicacion segun el trafico. Tambien se usara un balanceador de carga que distribuira solicitudes entre servidores en multiple zonas de disponiblidad. 

La base de datos se configurara con replicacion y sharding para garantizar el alto rendimiento, Tambien se empleara **Redis** o **Memcached** para mejorar la velocidad de respuesta.

### 5. Costos y Riesgos:
Los costos principales seran el uso de instancias en la nube para la aplicacion y la base de datos, los costos de almacenamiento en la nube para lso registros de usuarios y transacciones y por ultimo los gastos en la transferencia de datos si hay un alto trafico de usuarios.

Los riesgos seran la dependencia de un solo proveedor en la nube en terminos de disponibilidad, la necesidad de un plan en caso se necesiten recuperar datos ante un caso de fallos en el servicio y el cumplimiento normativo en el manejo de datos de pago y usuarios (dni, tarjetas de credito o debito, codigo de las entradas, etc.).

### 6. Presentacion Final:

Se adjuntara el diagrama en el github con nombre: **Actividad 3 Diagrama**

## Referencias:
* https://elpais.com/tecnologia/branded/especial-innovacion/2025-03-28/como-construir-en-20-anos-una-red-avanzada-de-servicios-digitales-bancarios.html

* https://www.gestionar-facil.com/migracion-a-la-nube/

* https://elpais.com/tecnologia/2024-10-29/el-inesperado-proveedor-de-servicios-en-la-nube-lidl.html

* https://www.ibm.com/think/topics/public-cloud-vs-private-cloud-vs-hybrid-cloud

* https://www.nutanix.com/en_gb/info/multi-cloud-environment

