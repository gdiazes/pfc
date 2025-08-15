### **Contexto: ¿Cuándo y por qué crear este documento?**

Imagina que estamos en la **Fase de Diseño** de nuestro proyecto "Wi-Fi del Futuro". Ya tenemos el diseño completo (LLD), pero el CFO está preocupado por la inversión y el Director de Marketing quiere una solución *ya* para su nuevo piso rediseñado, que es un espacio de "hot desking" y colaboración intensiva.

**Decisión:** Se acuerda lanzar un MVP. El objetivo es desplegar la nueva red Wi-Fi 6 únicamente en el **piso de Marketing** (que representa el 20% del proyecto) para validar la tecnología, la experiencia de usuario y demostrar el valor del proyecto antes de continuar con el despliegue completo.

---

### **El Entregable: Plan de Implementación y Aceptación del MVP**

Este documento es una versión acotada y enfocada de varios documentos de las fases de Diseño e Implementación, pero centrada exclusivamente en el alcance del MVP.

#### **Plantilla Detallada: Plan de Implementación y Aceptación del MVP**


**PLAN DE IMPLEMENTACIÓN Y ACEPTACIÓN DEL MVP: Proyecto "Wi-Fi del Futuro" - Piso de Marketing**

**ID del Documento:** MVP-WIFI-2024-001   **Versión:** 1.0   **Fecha:** 29/01/2024

**1. Resumen Ejecutivo del MVP**
   - **Propósito:** Implementar y validar la solución completa de Wi-Fi 6 en un entorno de producción controlado (el piso de Marketing, 3ª planta) para demostrar la viabilidad técnica y los beneficios de negocio antes de la aprobación del despliegue total.
   - **Alcance del MVP:**
     - **INCLUYE:** Instalación de 10 nuevos APs Wi-Fi 6, configuración del switch de acceso de la 3ª planta, habilitación de los SSIDs "OficinaCorp" y "OficinaCorp_Invitados" para los 50 empleados del departamento.
     - **EXCLUYE:** El resto de los pisos, la implementación del SSID "BYOD" y "Lab", y la integración con el sistema WIPS avanzado (se usará el básico).
   - **Duración del MVP:** La fase de prueba y evaluación durará 2 semanas (del 12/02/2024 al 23/02/2024).
   - **Criterio de Éxito Principal:** Si los criterios de aceptación de este documento se cumplen, el proyecto principal recibirá la luz verde para su implementación completa.

**2. Objetivos Medibles del MVP**
   - **Objetivo 1 (Validación Técnica):** Demostrar que la nueva infraestructura puede soportar 50 usuarios concurrentes en un entorno de alta densidad con un rendimiento superior a la red antigua.
   - **Objetivo 2 (Validación de Negocio):** Reducir a cero el número de tickets de soporte relacionados con Wi-Fi provenientes del piso de Marketing durante el periodo de prueba.
   - **Objetivo 3 (Recopilación de Feedback):** Obtener retroalimentación cualitativa positiva del equipo de Marketing sobre la experiencia de usuario (velocidad, estabilidad, roaming).

**3. Plan de Implementación del MVP (Mini-MOP)**
   - **Fecha de Implementación:** Viernes, 09/02/2024 (de 8 PM a 1 AM).
   - **Pasos Clave:**
     1. Pre-configurar el nuevo switch de acceso (SW-P3-01) con las VLANs 10, 20 y 99.
     2. Instalar físicamente los 10 APs (AP-P3-01 a AP-P3-10) según el LLD.
     3. Realizar el "cutover" (migración): Desconectar el antiguo switch y conectar el nuevo al núcleo de la red.
     4. Realizar pruebas de humo (smoke tests) por parte del equipo de TI para validar la conectividad básica.
   - **Plan de Rollback:** Si las pruebas de humo fallan a la 1 AM, se reconectará el switch antiguo. El tiempo máximo de interrupción permitido para el piso es de 15 minutos.

**4. Criterios de Aceptación del MVP**
   - Esta sección es la más importante. Define qué significa "éxito" para el MVP.
   - **Grupo de Usuarios Piloto:** Todo el departamento de Marketing (50 empleados).
   - **Proceso de Validación:**
     - **Validación Técnica (Realizada por TI):**
       | Criterio ID | Descripción de la Prueba                                    | Métrica de Éxito                                     | Estado (Pasa/Falla) |
       |-------------|-------------------------------------------------------------|------------------------------------------------------|---------------------|
       | MVP-T-01    | Prueba de velocidad desde 3 ubicaciones distintas del piso. | Promedio de descarga > 300 Mbps en Speedtest.net.     |                     |
       | MVP-T-02    | Prueba de roaming durante una llamada de Teams.             | La llamada no debe experimentar pérdida de audio > 1 seg. |                     |
       | MVP-T-03    | Prueba de capacidad con 10 usuarios simultáneos en video.   | Jitter promedio < 20ms y pérdida de paquetes < 0.5%. |                     |
     - **Validación de Negocio (Realizada por el Director de Marketing):**
       | Criterio ID | Descripción de la Prueba                                    | Métrica de Éxito                                     | Estado (Pasa/Falla) |
       |-------------|-------------------------------------------------------------|------------------------------------------------------|---------------------|
       | MVP-B-01    | Monitorización de tickets de soporte en ServiceNow.         | 0 tickets abiertos por "Wi-Fi lento/desconexión" para usuarios de la 3ª planta. |                     |
       | MVP-B-02    | Encuesta de satisfacción de usuarios.                       | Puntuación promedio de 8/10 o superior en la pregunta "¿Qué tan satisfecho está con la nueva red Wi-Fi?". |                     |

**5. Resultados y Recomendaciones**
   - *(Esta sección se completa al final del periodo de prueba del MVP)*.
   - **Resumen de Resultados:**
     - *Ej: Todos los criterios técnicos (MVP-T-01 a 03) fueron cumplidos. El criterio de negocio MVP-B-01 se cumplió (0 tickets). La encuesta (MVP-B-02) arrojó una puntuación de 9.2/10.*
   - **Lecciones Aprendidas:**
     - *Ej: Se descubrió que el portal cautivo para invitados era confuso para los visitantes. Se necesita simplificar el diseño de la interfaz antes del despliegue completo.*
   - **Recomendación Formal:**
     - *Ej: Basado en el éxito rotundo del MVP, se recomienda proceder con la implementación completa del proyecto "Wi-Fi del Futuro" según el plan original, incorporando las lecciones aprendidas.*

**Aprobación para Iniciar el MVP:**
- **Jefe de Proyecto:** _________________________
- **Director de Marketing (Stakeholder):** _________________________

**Aprobación Final del MVP (para continuar con el proyecto):**
- **Jefe de Proyecto:** _________________________
- **Director de Marketing (Stakeholder):** _________________________


