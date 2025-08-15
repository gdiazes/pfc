¡Entendido! Vamos a detallar cada plantilla con un nivel de especificidad mucho mayor. Rellenaré cada sección con el tipo de información técnica y de negocio que se esperaría en un proyecto real y complejo. El objetivo es que estas plantillas sirvan como un ejemplo robusto y casi listo para usar.

---

### **Fase 1: Preparar (Prepare)**

#### **Plantilla Detallada: Caso de Negocio (Business Case)**

```
________________________________________________________________________________

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
________________________________________________________________________________
```

---

### **Fase 2: Planificar (Plan)**

#### **Plantilla Detallada: Documento de Requisitos (Requirements Document)**

```
________________________________________________________________________________

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
________________________________________________________________________________
```

---

### **Fase 3: Diseñar (Design)**

#### **Plantilla Detallada: Diseño de Bajo Nivel (LLD) - Extracto**

```
________________________________________________________________________________

**DISEÑO DE BAJO NIVEL (LLD): Proyecto "Wi-Fi del Futuro"**

**ID del Documento:** LLD-WIFI-2023-001   **Versión:** 1.0   **Fecha:** 22/01/2024

**... [Secciones 1 y 2 como antes] ...**

**3. Plan de Direccionamiento IP y VLANs (Detallado)**
| VLAN ID | Nombre de VLAN      | Subred          | Gateway       | Servidor DHCP | Notas de Seguridad                                                                |
|---------|---------------------|-----------------|---------------|---------------|-----------------------------------------------------------------------------------|
| 10      | Corp_Usuarios       | 10.10.10.0/23   | 10.10.10.1    | 10.1.1.5      | ACLs aplicadas para acceso a servidores de producción.                            |
| 11      | Corp_Voz_IP         | 10.10.12.0/24   | 10.10.12.1    | 10.1.1.5      | VLAN específica para teléfonos VoWiFi, marcada con CoS 5.                         |
| 20      | Invitados           | 10.10.20.0/24   | 10.10.20.1    | 10.1.1.5      | Aislamiento de cliente forzado. Tráfico enrutado directamente a Internet vía firewall. |
| 25      | BYOD                | 10.10.25.0/24   | 10.10.25.1    | 10.1.1.5      | Acceso limitado a Internet y servicios en la DMZ (ej. Office 365).                |
| 40      | Lab_Investigacion   | 10.10.40.0/24   | 10.10.40.1    | 10.1.1.5      | VLAN altamente restringida, sin acceso a la red corporativa.                      |
| 99      | Gestion_Red_WLAN    | 10.10.99.0/24   | 10.10.99.1    | N/A (Estático)| VLAN nativa para tráfico de gestión entre APs y controlador.                      |

**4. Diseño de Radiofrecuencia (RF)**
   - **Plan de Canales (5 GHz):** Se utilizarán únicamente canales no superpuestos (36, 40, 44, 48, 52, 56, 60, 64, 100, ...). La asignación de canales será dinámica (Cisco RRM), pero se excluirán los canales DFS en áreas críticas para evitar interrupciones.
   - **Ancho de Canal:** 40 MHz para áreas de densidad media; 20 MHz para áreas de alta densidad (aulas, salas de conferencias) para maximizar el número de canales disponibles.
   - **Potencia de Transmisión (TPC):** Se configurará un mínimo de 5 dBm y un máximo de 17 dBm para fomentar que los clientes se conecten al AP más cercano y reducir la interferencia co-canal.

**5. Configuración de Switch de Acceso (Ejemplo Detallado)**
   ```
   ! Plantilla para puerto de AP en SW-P1-01
   interface GigabitEthernet1/0/5
    description *** Conexión a AP-P1-05 (Zona Marketing) ***
    switchport mode trunk
    switchport trunk native vlan 99
    switchport trunk allowed vlan 10,11,20,25,40,99
    spanning-tree portfast trunk
    spanning-tree bpduguard enable
    power inline auto max 30
    ip dhcp snooping trust
    auto qos voip cisco-phone ! Confía en el marcado CoS del AP para el tráfico de voz
   ```

**6. Plan de Pruebas de Unidad (Unit Test Plan)**
   - **Prueba 1 (Conectividad SSID Corp):**
     - *Pasos:* Usar un portátil corporativo, conectar al SSID "OficinaCorp".
     - *Validación:* Verificar la obtención de una IP en el rango 10.10.10.0/23, poder hacer ping a 8.8.8.8 y al servidor de archivos interno 10.1.2.10.
   - **Prueba 2 (Roaming):**
     - *Pasos:* Iniciar una llamada de Teams en un smartphone, caminar desde el ala norte al ala sur.
     - *Validación:* Usar la app de análisis Wi-Fi para verificar que el cliente cambia de AP sin que la llamada se interrumpa. El BSSID debe cambiar.
   - **Prueba 3 (Seguridad Invitados):**
     - *Pasos:* Conectar un dispositivo al SSID "OficinaCorp_Invitados".
     - *Validación:* Verificar que se obtiene una IP en 10.10.20.0/24. Intentar hacer ping a 10.10.10.1. El ping debe fallar.

**Revisado por Arquitecto Principal:** _________  **Fecha:** _________
________________________________________________________________________________
```

*(Las plantillas para las fases 4, 5 y 6 seguirían este mismo nivel de detalle, especificando los cambios exactos, los comandos de troubleshooting, los umbrales de monitoreo, y los datos numéricos que justifican una optimización)*.
