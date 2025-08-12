# Arquitectura Web Segura de 3 Capas en Azure

![Azure](https://img.shields.io/badge/azure-%230078D4.svg?style=for-the-badge&logo=microsoftazure&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)

Este repositorio contiene la infraestructura y documentación para desplegar una aplicación web siguiendo un patrón de **arquitectura de 3 capas** en Microsoft Azure. El objetivo es demostrar la implementación de una infraestructura segura, escalable y segmentada utilizando servicios nativos de la nube y contenedores Docker.

**[Ver la documentación técnica detallada del despliegue](DOCUMENTACION_DETALLADA.md)**

---

### 🚀 Arquitectura y Flujo de Tráfico

La infraestructura se despliega en una Red Virtual (VNet) personalizada y se divide en capas lógicas, cada una en una subred aislada para aplicar el principio de defensa en profundidad.



1.  **Capa de Presentación (Frontend):** Un **Azure Application Gateway** actúa como reverse proxy y único punto de entrada desde internet.
2.  **Capa de Lógica (Backend):** Una **Azure Container Instance (ACI)** ejecuta la aplicación web (DVWA) desde una imagen de Docker personalizada, sin exposición directa a internet.
3.  **Capa de Datos (Database):** Un servidor de **Azure Database for MySQL (Flexible Server)** almacena los datos en una subred completamente aislada.
4.  **Capa de Administración:** Una **Máquina Virtual (Jump Box)** en una subred separada sirve como punto de acceso seguro para tareas de mantenimiento.

![Diagrama de la Arquitectura de Red en Azure](images/topologi-vnet.png)
---

### 💡 Logros y Habilidades Demostradas

Como reclutador, esto es lo que un proyecto como este me demuestra sobre un candidato. Has demostrado experiencia práctica en el ciclo de vida completo de una aplicación en la nube.

* **Diseñé una arquitectura de aplicación segura de 3 capas**, aislando completamente la aplicación y la base de datos de la exposición directa a internet, mediante la implementación de un **Reverse Proxy (Azure Application Gateway)** y la **segmentación de la red** en subredes dedicadas.

* **Automaticé el entorno de ejecución de la aplicación**, garantizando un despliegiegue consistente y reproducible, a través de la escritura de un **`Dockerfile`** personalizado y su publicación en un **Azure Container Registry (ACR)**.

* **Configuré la conectividad de red privada entre servicios distribuidos**, permitiendo la resolución de nombres segura y el tráfico de base de datos únicamente desde subredes autorizadas, a través de la vinculación de **Zonas DNS Privadas** y la creación de reglas en **Grupos de Seguridad de Red (NSG)**.

* **Implementé una gestión segura de la configuración**, desacoplando los secretos de la base de datos del código fuente, mediante el uso de **variables de entorno** inyectadas en tiempo de ejecución en **Azure Container Instances (ACI)**.

* **Apliqué prácticas de gobernanza y gestión de recursos en la nube**, manteniendo una organización limpia y preparada para el control de costes, a través del uso consistente de **convenciones de nomenclatura y etiquetas** en todos los recursos desplegados.
