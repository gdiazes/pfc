
#### **Plantilla Detallada: Propuesta de Mejora (Improvement Proposal)**


**PROPUESTA DE MEJORA: Implementación de QoS Adaptativo para Aplicaciones Críticas**

**ID del Documento:** IMP-WIFI-2024-001   **Versión:** 1.0   **Fecha:** 15/05/2024

**1. Resumen Ejecutivo**
   - **Observación:** El análisis de los datos de Cisco DNA Center Assurance de los últimos 90 días muestra que, aunque el rendimiento general de la red es excelente (95% de salud), el 5% de las sesiones de Microsoft Teams experimentan una calidad "Pobre" (calificada por jitter y pérdida de paquetes) durante las horas de máxima congestión (10-11 AM y 2-3 PM).
   - **Propuesta:** Evolucionar de nuestra actual política de QoS estática a una política de QoS adaptativa, utilizando la integración de Cisco DNA Center con Microsoft 365. Esto permite a la red identificar y priorizar dinámicamente el tráfico de Teams basándose en las APIs de Microsoft, en lugar de depender solo de puertos y direcciones IP estáticas.
   - **Beneficio Esperado:** Reducir la tasa de llamadas de Teams de calidad "Pobre" del 5% al <1%, garantizando una experiencia de colaboración óptima incluso en momentos de alta carga en la red. Esto se alinea directamente con el objetivo de negocio RB-01.

**2. Análisis de Datos y Justificación**
   - **Dato 1 (Gráfico):** [Adjuntar un gráfico de DNA Center mostrando el "Health de la Aplicación Microsoft Teams" a lo largo del tiempo, con caídas notables en las horas pico].
   - **Dato 2 (Análisis Causa-Raíz):** El análisis de flujo de paquetes (NetFlow) revela que la degradación coincide con picos de tráfico no crítico pero de gran ancho de banda, como actualizaciones de Windows (WSUS) y sincronizaciones de backups en la nube (OneDrive, Dropbox) que compiten por la prioridad en la cola de salida de la WAN. Nuestra QoS actual marca ambos tipos de tráfico (Teams y Office 365 general) con el mismo valor DSCP (AF41), lo que causa el conflicto.

**3. Mejora Propuesta Detallada**
   - **Paso 1 (Integración):** Configurar la integración API entre nuestro tenant de Cisco DNA Center y nuestro tenant de Microsoft 365.
   - **Paso 2 (Política):** Crear una nueva política de aplicación en DNA Center que utilice la información de la API de Microsoft para identificar específicamente los flujos de audio y video de Teams en tiempo real.
   - **Paso 3 (Remarcado de Tráfico):** Asignar a estos flujos identificados el valor DSCP más alto (EF - Expedited Forwarding), diferenciándolos del resto del tráfico de Office 365.
   - **Paso 4 (Despliegue):** Empujar la nueva política de QoS a todos los switches de acceso y al enrutador de borde de la WAN.

**4. Impacto y Riesgos**
   - **Impacto:** Altamente positivo para las aplicaciones de colaboración. El tráfico menos crítico (como las actualizaciones de fondo) experimentará una latencia ligeramente mayor durante los picos de congestión, lo cual es un comportamiento deseable y aceptable.
   - **Riesgo:** Bajo. Existe un pequeño riesgo de que una configuración incorrecta de la API pueda causar un fallo en la clasificación del tráfico.
   - **Mitigación del Riesgo:** La implementación se realizará primero en un grupo piloto de usuarios (el departamento de TI) durante 48 horas para validar el comportamiento antes del despliegue general.

**5. Plan de Acción Sugerido (Mini-Proyecto PPDIOO)**
   1. **Preparar/Planificar (1 día):** Formalizar el mini-proyecto y asignar recursos.
   2. **Diseñar (2 días):** Documentar los pasos exactos de la configuración y el plan de rollback (desactivar la política).
   3. **Implementar (1 día):** Realizar la integración y el despliegue en el grupo piloto.
   4. **Operar/Validar (2 días):** Monitorear el rendimiento del grupo piloto y recopilar feedback.
   5. **Implementación Final (1 día):** Desplegar la política a toda la organización.
   6. **Optimizar:** Revisar los resultados después de 30 días para confirmar el éxito de la mejora.

**Solicitado por: [Arquitecto de Red Principal]**   **Fecha:** 15/05/2024
