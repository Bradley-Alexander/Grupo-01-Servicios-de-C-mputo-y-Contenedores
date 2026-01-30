# Informe Técnico: Servicios de Cómputo y Contenedores

**Universidad Nacional de Loja** **Carrera:** Computación  
**Ciclo:** 6° "A"  
**Docente:** Ing. Cristian Narváez  
**Fecha:** 28 de enero del 2026

**Integrantes:**
* Bradley Alexander Poma Vera
* Christian Leonardo Robles Maza
* Esteban Hermel Leon Aguilar
* Gabriel Alejandro Espinoza Coronel

---

## 1. Introducción
El cómputo en la nube ha transformado la infraestructura de TI, permitiendo a las organizaciones acceder a recursos bajo demanda. Este informe analiza tres modelos principales de servicios de cómputo: infraestructura como servicio (**IaaS**) representada por Amazon EC2, y función como servicio (**FaaS**) representada por AWS Lambda y Azure Functions. Asimismo, se explora el rol crítico de la orquestación de contenedores, enfocándose en **Docker Swarm** como herramienta de gestión de clústeres.

## 2. Principales Servicios de Cómputo en la Nube

### 2.1. Amazon EC2 (Elastic Compute Cloud)
* **Definición:** Es un servicio web que proporciona capacidad informática redimensionable en la nube.
* **Modelo:** Pertenece al modelo IaaS (Infrastructure as a Service).
* **Características:** Ofrece control total sobre las instancias (máquinas virtuales), permitiendo elegir el sistema operativo, configurar el firewall y administrar el almacenamiento.
* **Funcionamiento:** El usuario alquila computadoras virtuales en las que ejecuta sus propias aplicaciones informáticas.

### 2.2. AWS Lambda
* **Definición:** Es un servicio de computación serverless (sin servidor) y orientado a eventos.
* **Características:** Ejecuta código en respuesta a eventos y gestiona automáticamente los recursos informáticos subyacentes.
* **Funcionamiento:** El usuario sube el código y Lambda se encarga de todo lo necesario para ejecutar y escalar con alta disponibilidad.

### 2.3. Azure Functions
* **Definición:** Es la solución serverless de Microsoft, diseñada para acelerar y simplificar el desarrollo de aplicaciones.
* **Características:** Permite ejecutar pequeños fragmentos de código sin preocuparse por la infraestructura y se integra con el ecosistema de Microsoft.
* **Funcionamiento:** Soporta disparadores (triggers) y enlaces (bindings) para conectar funciones a otros servicios de forma declarativa.

---

## 3. Estudio Comparativo de Servicios de Cómputo

| Métrica | Amazon EC2 (IaaS) | AWS Lambda (FaaS) | Azure Functions (FaaS) |
| :--- | :--- | :--- | :--- |
| **Escalabilidad** | Manual/Auto-scaling: Requiere configuración de grupos. El escalado tarda minutos. | Automática e Instantánea: Escala horizontalmente según el número de peticiones. | Automática: Similar a Lambda, escala según demanda. Ofrece planes "Premium". |
| **Tiempo de Provisión** | **Minutos:** Tiempo necesario para levantar la instancia y el SO. | **Milisegundos:** El código está listo para ejecutarse casi instantáneamente. | **Milisegundos:** Rápida ejecución, aunque puede presentar latencia inicial. |
| **Modelo de Costos** | **Por tiempo de uso:** Se paga por segundos u horas que la instancia esté encendida. | **Por ejecución:** Se paga por número de peticiones y duración del cómputo. | **Consumo:** Pago por ejecución y recursos. Opción de plan App Service. |
| **Gestión (Ops)** | **Alta:** El usuario administra parches de SO, redes y seguridad. | **Nula/Baja:** El proveedor gestiona toda la infraestructura (NoOps). | **Nula/Baja:** Gestión abstraída, enfoque en el código. |
| **Casos de Uso** | Aplicaciones monolíticas, bases de datos, migraciones "Lift & Shift". | Procesamiento de archivos, backends de APIs REST, tareas programadas. | Integraciones con Office 365, procesamiento de eventos en Azure. |

---

## 4. Orquestadores de Contenedores

* **Funciones Principales:**
    * Aprovisionamiento y despliegue (selección del host).
    * Escalado de instancias según la demanda.
    * Descubrimiento de servicios y balanceo de carga.
    * Monitoreo de salud (Health Checks) y reinicio automático.
* **Ventajas y Beneficios:**
    * **Alta Disponibilidad:** Garantiza que la aplicación permanezca en línea ante fallos de nodos.
    * **Eficiencia de Recursos:** Maximiza el uso del hardware mediante distribución inteligente.
    * **Portabilidad:** Abstrae la infraestructura permitiendo mover clústeres entre nubes.

## 5. Gestión con Docker Swarm

### 5.1. Gestión de Clústeres (Arquitectura)
* **Manager Nodes:** Mantienen el estado del clúster y programan servicios usando el algoritmo Raft.
* **Worker Nodes:** Ejecutan los contenedores (tareas) asignados por los Managers.
* **Comandos:** `docker swarm init` para inicializar y `docker swarm join-token` para unir nodos.

### 5.2. Administración de Servicios
* **Despliegue Declarativo:** Se define el estado deseado (ej. `docker service create --replicas 3`) y Swarm lo mantiene.
* **Actualizaciones (Rolling Updates):** Permite actualizar imágenes progresivamente sin tiempo de inactividad con `docker service update`.

---

## 6. Ejemplo de despliegues

### 6.1 Aplicación práctica en IaaS (Máquina Virtual en Azure)
Se realizó un despliegue real en una MV Linux, configurando manualmente el SO, red y Docker para una aplicación Django. Este escenario es equivalente al uso de Amazon EC2.
> **Referencia:** app service.pdf

### 6.2 Ejemplo de aplicación práctica en PaaS (Azure App Service)
Se utilizó Azure App Service con integración continua (CI) mediante GitHub. El proveedor abstrae la gestión del SO, permitiendo enfocarse únicamente en el código.
> **Referencia:** DespligueRASCUNL_AZURE.pdf

---

## 7. Conclusiones
1. Existe una clara tendencia hacia la abstracción; EC2 ofrece control, mientras que Lambda y Azure Functions ofrecen velocidad de desarrollo y eficiencia de costos.
2. La elección entre IaaS y FaaS depende de la arquitectura de la aplicación; los microservicios modernos se benefician de FaaS, mientras que aplicaciones legacy requieren IaaS.
3. Docker Swarm democratiza la orquestación por su baja curva de aprendizaje, siendo ideal para equipos que buscan simplicidad.

---

## 8. Referencias
* **[1]** P. Mell and T. Grance, "[The NIST Definition of Cloud Computing](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-145.pdf)," NIST, 2011.
* **[2]** C. Pahl, "Containerization and the PaaS Cloud," IEEE Cloud Computing, 2015.

**Material Adicional:**
* Diapositivas: Evolución_y_Orquestación_de_Infraestructura.pdf
* Video: Desmitificando_la_Nube.mp4
