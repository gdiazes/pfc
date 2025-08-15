
#### **Plantilla Detallada: Guía de Resolución de Problemas (Runbook)**


**RUNBOOK DE OPERACIONES: Nivel 1/2 - Red Wi-Fi Corporativa (WIFI-FUTURE)**

**ID del Documento:** RUN-WIFI-2024-001   **Versión:** 1.1   **Fecha:** 01/03/2024

**Problema #2: Múltiples usuarios en una zona reportan desconexiones intermitentes**

- **Síntomas:**
  - Varios usuarios en la misma sala de reuniones (ej. "Sala Pacífico") reportan que pierden la conexión por 10-30 segundos y luego se reconectan.
  - Los tickets se generan en un periodo corto de tiempo y desde la misma ubicación física.
- **Impacto:** Alto (interrumpe reuniones importantes).   **Urgencia:** Alta.

- **Pasos de Diagnóstico y Solución (Nivel 2):**
  1. **Identificar el Punto de Acceso Común:**
     - En la consola de gestión (Cisco DNA Center), ir a `Assurance > Network Health`.
     - Filtrar por la ubicación física "Planta 2 > Sala Pacífico".
     - Identificar el AP que sirve esa área (ej. AP-P2-08).
  2. **Revisar el Estado del AP:**
     - Hacer clic en el AP-P2-08. Verificar:
       - **Uso de CPU:** ¿Está por encima del 80%?
       - **Uso de Memoria:** ¿Está por encima del 85%?
       - **Tiempo de actividad (Uptime):** ¿Se ha reiniciado recientemente?
       - **Logs del AP:** Buscar mensajes de error, especialmente relacionados con el módulo de radio.
  3. **Analizar el Entorno de Radiofrecuencia (RF):**
     - En la pestaña de RF del AP-P2-08, revisar:
       - **Utilización del Canal:** ¿Está el canal (ej. Canal 44) constantemente por encima del 70% de utilización? Esto indica alta congestión o interferencia.
       - **Interferencias:** ¿Detecta el sistema alguna fuente de interferencia no-Wi-Fi (ej. microondas, cámaras inalámbricas antiguas, teléfonos DECT)? DNA Center lo marcará en rojo.
       - **Cambios de Canal (DCA):** ¿Ha cambiado el AP de canal de forma errática y frecuente en las últimas horas? Podría indicar un problema de radar en un canal DFS.
  4. **Acción de Contención Inmediata:**
     - Si se sospecha de un fallo de hardware del AP, **reiniciar el AP remotamente** desde la consola. Esto resuelve problemas transitorios en el 60% de los casos.
     - `Comando: config ap reset <AP-Name>`
  5. **Análisis Profundo (Si el reinicio no funciona):**
     - Revisar los clientes conectados al AP. ¿Hay algún cliente con drivers antiguos que esté causando problemas (mostrando tasas de reintentos > 30%)?
     - Si se detecta una interferencia persistente, ejecutar un **análisis de espectro en vivo** desde el AP (si el hardware lo soporta) para identificar la fuente.
- **Criterios de Escalación (Nivel 3 / Arquitectura):**
  - Si el AP se reinicia y el problema vuelve a ocurrir en menos de 24 horas.
  - Si el análisis de espectro muestra una interferencia externa severa que no puede ser mitigada.
  - Si el log del AP muestra un "kernel panic" o un fallo de hardware recurrente. Abrir un **caso TAC con Cisco** y adjuntar el bundle de logs del AP.
