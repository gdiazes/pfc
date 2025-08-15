#### **Plantilla Detallada: Documento de Requisitos (Requirements Document)**

**DOCUMENTO DE REQUISITOS: Proyecto "Wi-Fi del Futuro"**

**ID del Documento:** REQ-WIFI-2023-001   **Versión:** 1.0   **Fecha:** 15/12/2023

**1. Introducción**
   - Este documento define los criterios de éxito funcionales y no funcionales para la nueva red WLAN. Todos los requisitos deben ser medibles y verificables.

**2. Requisitos de Negocio (Mapeados a Objetivos)**
   - **RB-01 (Objetivo: Productividad):** La red debe soportar, sin degradación perceptible (jitter < 30ms, pérdida de paquetes < 1%), hasta 200 sesiones simultáneas de Microsoft Teams con video HD.
   - **RB-02 (Objetivo: Experiencia de Usuario):** El proceso de roaming entre APs para un dispositivo en una llamada de voz sobre Wi-Fi (VoWiFi) debe completarse en menos de 50 milisegundos para evitar cortes audibles.
   - **RB-03 (Objetivo: Seguridad Corporativa):** La red debe impedir que los dispositivos de la red de invitados puedan acceder a cualquier recurso interno (servidores de archivos, impresoras), validado mediante pruebas de penetración.

**3. Requisitos Técnicos (Detallados)**
   - **Rendimiento y Cobertura:**
     - **RT-01 (Cobertura Primaria):** El 95% de las áreas de trabajo designadas deben tener una intensidad de señal recibida (RSSI) de -67 dBm o superior.
     - **RT-02 (Cobertura Secundaria):** El 100% de las áreas comunes (pasillos, cafetería) deben tener una RSSI de -70 dBm o superior.
     - **RT-03 (SNR):** La relación señal/ruido (SNR) debe ser de 25 dB o superior en todas las áreas de trabajo.
   - **Disponibilidad (SLA):**
     - **RT-04:** La disponibilidad del servicio Wi-Fi será del 99.9%, excluyendo ventanas de mantenimiento planificadas. Esto equivale a un tiempo de inactividad máximo de 8.76 horas al año.
   - **Escalabilidad:**
     - **RT-05:** Cada punto de acceso debe ser capaz de manejar un mínimo de 60 clientes asociados simultáneamente sin degradación del rendimiento.
     - **RT-06:** La arquitectura del controlador debe soportar un crecimiento del 50% en el número de APs (hasta 75 APs) sin requerir un reemplazo de hardware.
   - **Seguridad:**
     - **RT-07 (Autenticación):** Se implementará 802.1X EAP-TLS, utilizando certificados de máquina emitidos por nuestra PKI interna para los dispositivos corporativos.
     - **RT-08 (Segmentación):** Se crearán 4 zonas de seguridad (SSIDs) mapeadas a VLANs distintas: Corporativa, Invitados, BYOD y Laboratorio de I+D. El tráfico entre estas VLANs será inspeccionado por el firewall de próxima generación (Palo Alto).
     - **RT-09 (Detección de Intrusos):** La solución debe incluir un Sistema de Prevención de Intrusiones Inalámbricas (WIPS) para detectar y mitigar APs no autorizados (rogue APs) y ataques comunes de Wi-Fi (ej. de-autenticación).
   - **Gestionabilidad:**
     - **RT-10 (Monitorización):** La plataforma de gestión debe proporcionar visibilidad histórica de 30 días sobre el rendimiento por cliente, incluyendo RSSI, SNR y tasa de reintentos.
     - **RT-11 (Alertas):** Se deben configurar alertas proactivas por correo electrónico para el equipo de operaciones en caso de que un AP se desconecte o el uso de CPU de un controlador supere el 80%.

**4. Criterios de Aceptación**
   - El proyecto será aceptado por el negocio una vez que el "Informe de Resultados de Pruebas de Aceptación del Usuario (UAT)" confirme que todos los requisitos aquí listados han sido cumplidos y validados.

**Aprobado por: [Jefe de Infraestructura]**   **Firma:** _______________   **Fecha:** __________
