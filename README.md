# Informe Técnico: Servicios de Cómputo y Contenedores

[cite_start]**Universidad Nacional de Loja** [cite: 4]  
[cite_start]**Carrera:** Computación [cite: 5]  
[cite_start]**Ciclo:** $6^{\circ}A^{"}$ [cite: 13, 14]  
**Docente:** Ing. [cite_start]Cristian Narváez [cite: 15, 16]  
[cite_start]**Fecha:** 28 de enero del 2026 [cite: 19, 20]

[cite_start]**Integrantes:** [cite: 8]
* [cite_start]Bradley Alexander Poma Vera [cite: 9]
* [cite_start]Christian Leonardo Robles Maza [cite: 10]
* [cite_start]Esteban Hermel Leon Aguilar [cite: 11]
* [cite_start]Gabriel Alejandro Espinoza Coronel [cite: 12]

---

## 1. Introducción
[cite_start]El cómputo en la nube ha transformado la infraestructura de TI, permitiendo a las organizaciones acceder a recursos bajo demanda[cite: 21, 22]. [cite_start]Este informe analiza tres modelos principales de servicios de cómputo: infraestructura como servicio (**IaaS**) representada por Amazon EC2, y función como servicio (**FaaS**) representada por AWS Lambda y Azure Functions[cite: 23]. [cite_start]Asimismo, se explora el rol crítico de la orquestación de contenedores, enfocándose en **Docker Swarm** como herramienta de gestión de clústeres[cite: 24].

## [cite_start]2. Principales Servicios de Cómputo en la Nube [cite: 25]

### 2.1. [cite_start]Amazon EC2 (Elastic Compute Cloud) [cite: 26]
* [cite_start]**Definición:** Es un servicio web que proporciona capacidad informática redimensionable en la nube[cite: 27].
* [cite_start]**Modelo:** Pertenece al modelo IaaS (Infrastructure as a Service)[cite: 28].
* [cite_start]**Características:** Ofrece control total sobre las instancias (máquinas virtuales), permitiendo elegir el sistema operativo, configurar el firewall y administrar el almacenamiento[cite: 29].
* [cite_start]**Funcionamiento:** El usuario alquila computadoras virtuales en las que ejecuta sus propias aplicaciones informáticas[cite: 30].

### 2.2. [cite_start]AWS Lambda [cite: 31]
* [cite_start]**Definición:** Es un servicio de computación serverless (sin servidor) y orientado a eventos[cite: 32].
* [cite_start]**Características:** Ejecuta código en respuesta a eventos y gestiona automáticamente los recursos informáticos subyacentes[cite: 34].
* [cite_start]**Funcionamiento:** El usuario sube el código y Lambda se encarga de todo lo necesario para ejecutar y escalar con alta disponibilidad[cite: 35].

### 2.3. [cite_start]Azure Functions [cite: 36]
* [cite_start]**Definición:** Es la solución serverless de Microsoft, diseñada para acelerar y simplificar el desarrollo de aplicaciones[cite: 37].
* [cite_start]**Características:** Permite ejecutar pequeños fragmentos de código sin preocuparse por la infraestructura y se integra con el ecosistema de Microsoft[cite: 39, 40].
* [cite_start]**Funcionamiento:** Soporta disparadores (triggers) y enlaces (bindings) para conectar funciones a otros servicios de forma declarativa[cite: 41].

---

## [cite_start]3. Estudio Comparativo de Servicios de Cómputo [cite: 42]

| Métrica | Amazon EC2 (IaaS) | AWS Lambda (FaaS) | Azure Functions (FaaS) |
| :--- | :--- | :--- | :--- |
| **Escalabilidad** | Manual/Auto-scaling: Requiere configuración de grupos. [cite_start]El escalado tarda minutos[cite: 44]. | [cite_start]Automática e Instantánea: Escala horizontalmente según el número de peticiones[cite: 44]. | Automática: Similar a Lambda, escala según demanda. [cite_start]Ofrece planes "Premium"[cite: 44]. |
| **Tiempo de Provisión** | [cite_start]**Minutos:** Tiempo necesario para levantar la instancia y el SO[cite: 44]. | [cite_start]**Milisegundos:** El código está listo para ejecutarse casi instantáneamente[cite: 44]. | [cite_start]**Milisegundos:** Rápida ejecución, aunque puede presentar latencia inicial[cite: 44]. |
| **Modelo de Costos** | [cite_start]**Por tiempo de uso:** Se paga por segundos u horas que la instancia esté encendida[cite: 44]. | [cite_start]**Por ejecución:** Se paga por número de peticiones y duración del cómputo[cite: 44]. | **Consumo:** Pago por ejecución y recursos. [cite_start]Opción de plan App Service[cite: 44]. |
| **Gestión (Ops)** | [cite_start]**Alta:** El usuario administra parches de SO, redes y seguridad[cite: 44]. | [cite_start]**Nula/Baja:** El proveedor gestiona toda la infraestructura (NoOps)[cite: 44]. | [cite_start]**Nula/Baja:** Gestión abstraída, enfoque en el código[cite: 44]. |
| **Casos de Uso** | [cite_start]Aplicaciones monolíticas, bases de datos, migraciones "Lift & Shift"[cite: 44]. | [cite_start]Procesamiento de archivos, backends de APIs REST, tareas programadas[cite: 44]. | [cite_start]Integraciones con Office 365, procesamiento de eventos en Azure[cite: 44]. |

---

## [cite_start]4. Orquestadores de Contenedores [cite: 45, 46]

* [cite_start]**Funciones Principales:** [cite: 47]
    * [cite_start]Aprovisionamiento y despliegue (selección del host)[cite: 48].
    * [cite_start]Escalado de instancias según la demanda[cite: 49].
    * [cite_start]Descubrimiento de servicios y balanceo de carga[cite: 49, 50].
    * [cite_start]Monitoreo de salud (Health Checks) y reinicio automático[cite: 51].
* [cite_start]**Ventajas y Beneficios:** [cite: 52]
    * [cite_start]**Alta Disponibilidad:** Garantiza que la aplicación permanezca en línea ante fallos de nodos[cite: 54].
    * [cite_start]**Eficiencia de Recursos:** Maximiza el uso del hardware mediante distribución inteligente[cite: 55].
    * [cite_start]**Portabilidad:** Abstrae la infraestructura permitiendo mover clústeres entre nubes[cite: 56].

## [cite_start]5. Gestión con Docker Swarm [cite: 57, 58]

### 5.1. [cite_start]Gestión de Clústeres (Arquitectura) [cite: 59]
* [cite_start]**Manager Nodes:** Mantienen el estado del clúster y programan servicios usando el algoritmo Raft[cite: 61, 62].
* [cite_start]**Worker Nodes:** Ejecutan los contenedores (tareas) asignados por los Managers[cite: 63].
* [cite_start]**Comandos:** `docker swarm init` para inicializar y `docker swarm join-token` para unir nodos[cite: 64, 65].

### 5.2. [cite_start]Administración de Servicios [cite: 66]
* [cite_start]**Despliegue Declarativo:** Se define el estado deseado (ej. `docker service create --replicas 3`) y Swarm lo mantiene[cite: 68, 69].
* [cite_start]**Actualizaciones (Rolling Updates):** Permite actualizar imágenes progresivamente sin tiempo de inactividad con `docker service update`[cite: 70].

---

## [cite_start]6. Ejemplo de despliegues [cite: 71]

### [cite_start]6.1 Aplicación práctica en IaaS (Máquina Virtual en Azure) [cite: 72]
[cite_start]Se realizó un despliegue real en una MV Linux, configurando manualmente el SO, red y Docker para una aplicación Django[cite: 73]. [cite_start]Este escenario es equivalente al uso de Amazon EC2[cite: 74].
> [cite_start]**Referencia:** app service.pdf [cite: 75]

### [cite_start]6.2 Ejemplo de aplicación práctica en PaaS (Azure App Service) [cite: 76]
[cite_start]Se utilizó Azure App Service con integración continua (CI) mediante GitHub[cite: 77]. [cite_start]El proveedor abstrae la gestión del SO, permitiendo enfocarse únicamente en el código[cite: 78].
> [cite_start]**Referencia:** DespligueRASCUNL_AZURE.pdf [cite: 79, 81]

---

## [cite_start]7. Conclusiones [cite: 80]
1. Existe una clara tendencia hacia la abstracción; [cite_start]EC2 ofrece control, mientras que Lambda y Azure Functions ofrecen velocidad y eficiencia de costos[cite: 82].
2. [cite_start]La elección depende de la arquitectura: microservicios modernos (FaaS) vs. aplicaciones legacy (IaaS)[cite: 83, 84].
3. [cite_start]Docker Swarm democratiza la orquestación por su baja curva de aprendizaje, ideal para equipos que buscan simplicidad[cite: 85].

---

## [cite_start]8. Referencias [cite: 90]
* [cite_start]**[1]** P. Mell and T. Grance, "[The NIST Definition of Cloud Computing](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-145.pdf)," NIST, 2011[cite: 91, 92].
* [cite_start]**[2]** C. Pahl, "Containerization and the PaaS Cloud," IEEE Cloud Computing, 2015[cite: 93, 94].

**Material Adicional:**
* [cite_start]Diapositivas: Evolución_y_Orquestación_de_Infraestructura.pdf [cite: 86, 87]
* [cite_start]Video: Desmitificando_la_Nube.mp4 [cite: 88, 89]
