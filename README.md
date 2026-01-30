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
| **Casos de Uso** | Aplicaciones monolíticas, bases de datos, migraciones "Lift & Shift". | Procesamiento de archivos, backends de APIs REST, tareas programadas. | Integraciones con Office 365, procesamiento de eventos en
