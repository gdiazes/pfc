#### **Plantilla Detallada: Caso de Negocio (Business Case)**

**CASO DE NEGOCIO: Proyecto "Wi-Fi del Futuro" para la Oficina Híbrida**

**ID del Documento:** BC-WIFI-2023-001   **Versión:** 1.2   **Fecha:** 28/11/2023

**1. Resumen Ejecutivo**
   - **Problema:** Nuestra infraestructura Wi-Fi actual (basada en el estándar 802.11n, instalada en 2015) es técnicamente obsoleta y no puede soportar la densidad de dispositivos ni las demandas de ancho de banda de las aplicaciones de colaboración modernas (Microsoft Teams, Zoom, Miro). Esto resulta en una tasa de incidencias relacionadas con la red del 35% del total de tickets de soporte, y quejas verbales directas de directores de departamento. El Net Promoter Score (NPS) interno de TI ha caído 15 puntos en el último trimestre, citando "problemas de conectividad" como la razón principal.
   - **Solución Propuesta:** Realizar una actualización completa a una arquitectura inalámbrica basada en el estándar Wi-Fi 6 (802.11ax), gestionada de forma centralizada. Esto incluye el reemplazo de 30 puntos de acceso antiguos por 50 nuevos APs de alta densidad, la actualización de los switches de acceso para soportar PoE+, y la implementación de una plataforma de gestión de red con capacidades de analítica y aseguramiento de servicio.
   - **Beneficios Clave:**
     1. **Reducción de tickets de soporte en un 80%** (de ~40/mes a <8/mes) relacionados con Wi-Fi.
     2. **Aumento de la productividad medible:** Se estima una recuperación de 10 minutos por empleado al día, que actualmente se pierden en reconexiones y llamadas fallidas.
     3. **Habilitación de la estrategia de negocio "Oficina Colaborativa 2024"**.
   - **Coste Estimado y ROI:** Inversión total de 82,500€ (CAPEX). Se proyecta un Retorno de Inversión (ROI) en 18 meses, basado en el ahorro de horas de soporte y la recuperación de productividad del empleado (valorada en 55,000€ anuales).

**2. Descripción del Problema / Oportunidad de Negocio**
   - **Impacto Actual:**
     - **Operativo:** Las videollamadas con clientes se interrumpen, dañando la imagen profesional de la empresa.
     - **Financiero:** El equipo de soporte de TI dedica aproximadamente 60 horas/mes a resolver problemas de Wi-Fi, un coste operativo de ~3,000€/mes.
     - **Estratégico:** La mala calidad de la red es un obstáculo directo para atraer y retener talento que valora un entorno de trabajo tecnológico avanzado.

**3. Opciones Consideradas**
   - **Opción A (Recomendada): Actualización completa a Wi-Fi 6.**
     - *Pros:* Solución a largo plazo, escalable, mejora drásticamente el rendimiento y la seguridad, habilita analíticas avanzadas.
     - *Cons:* Mayor inversión inicial (CAPEX).
   - **Opción B: Parcheo de la red actual (Añadir 10 APs 802.11ac).**
     - *Pros:* Menor coste inicial (~25,000€).
     - *Cons:* Solución temporal que no resuelve el problema de la densidad y la obsolescencia tecnológica. Se proyecta que necesitaría ser reemplazada en 2-3 años.
   - **Opción C: No hacer nada (Status Quo).**
     - *Pros:* Cero inversión inmediata.
     - *Cons:* Riesgo inaceptable para la continuidad del negocio. Se espera un aumento de la insatisfacción y una posible pérdida de empleados clave.

**4. Análisis de Costos y Beneficios (Detallado para Opción A)**
   - **Costos (CAPEX):**
     - 50x Puntos de Acceso Wi-Fi 6 (Cisco C9120AXI): 45,000€
     - 2x Switches PoE+ de 48 puertos (Cisco C9200-48P): 15,000€
     - Licencias de gestión (Cisco DNA Advantage, 5 años): 17,500€
     - Instalación y consultoría externa: 5,000€
     - **TOTAL CAPEX: 82,500€**
   - **Costos (OPEX Anual):**
     - Contrato de soporte SmartNet: 4,000€

**5. Riesgos y Mitigaciones**
   - **Riesgo 1:** Interrupción del servicio durante la migración afectando la productividad.
     - **Mitigación:** La implementación se realizará en fases, fuera del horario laboral (viernes de 10 PM a domingo 6 PM), con un plan de rollback detallado.
   - **Riesgo 2:** La solución es más cara de lo presupuestado debido a problemas imprevistos de cableado.
     - **Mitigación:** Se ha incluido una contingencia del 10% (8,250€) en el presupuesto del proyecto. Se realizará una inspección de cableado en la fase de Planificación.

**6. Recomendación y Próximos Pasos**
   - Se recomienda formalmente la aprobación de la Opción A con un presupuesto total de 90,750€ (incluyendo contingencia).
   - Se solicita la asignación de un Jefe de Proyecto y un Arquitecto de Red para iniciar la fase de Planificación el 04/12/2023.

**Aprobado por: [Nombre del CIO/CFO]**   **Firma:** _________________   **Fecha:** __________
