### **Fase 4: Implementar (Implement)**

#### **Plantilla Detallada: Documentación As-Built (Registro de Desviaciones)**


**DOCUMENTACIÓN AS-BUILT: Proyecto "Wi-Fi del Futuro"**

**ID del Documento:** ASB-WIFI-2023-001   **Versión:** 1.0   **Fecha:** 15/02/2024

**1. Referencia al Diseño Original**
   - Este documento actualiza y reemplaza el LLD (LLD-WIFI-2023-001, v1.0) para reflejar la infraestructura inalámbrica tal y como fue desplegada y validada en producción el 12/02/2024. Este es el documento de referencia para todas las futuras operaciones y troubleshooting.

**2. Registro de Desviaciones del Diseño (Change Log)**
| ID | Descripción en LLD                                     | Cambio Realizado en la Implementación                 | Justificación del Cambio                         | Fecha      | Responsable |
|----|--------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------|------------|-------------|
| 01 | AP-P2-11 planificado en el centro del pasillo, a 15m del AP-P2-10 | AP-P2-11 fue movido 3 metros al oeste, a 12m del AP-P2-10 | Durante la instalación, se descubrió una viga estructural de acero que causaba una atenuación de -10dBm en la señal, creando una sombra de RF. La nueva ubicación evita la obstrucción. | 10/02/2024 | Ing. Pérez  |
| 02 | Puerto de uplink para SW-P2-01 era Gi1/0/48 conectado a Core-SW1-Po1 | Se utilizó el puerto Gi1/0/47 conectado a Core-SW1-Po2 | El transceptor SFP en el puerto Gi1/0/48 del switch resultó estar defectuoso (DOA - Dead On Arrival). Se movió la conexión al siguiente puerto disponible del Port-channel para mantener la redundancia. | 10/02/2024 | Ing. Pérez  |
| 03 | La VLAN de IoT era la VLAN 30, con subred 10.10.30.0/24   | Se utilizó la VLAN 35, con subred 10.10.35.0/24       | Durante la integración, se detectó que la VLAN 30 ya estaba en uso en el núcleo para el sistema de control de climatización (BMS), lo cual no estaba documentado. Se eligió la siguiente VLAN disponible para evitar un conflicto. | 11/02/2024 | Ing. García |
| 04 | Potencia de transmisión máxima configurada a 17 dBm en LLD. | Se ajustó la potencia máxima a 14 dBm en el perfil RF de la Planta 1. | El post-deployment site survey reveló que 17 dBm causaba una superposición excesiva de celdas (CCI) en las oficinas más pequeñas, llevando a problemas de "sticky client". Reducir la potencia optimizó el roaming. | 12/02/2024 | Ing. García |

**3. Diagramas y Configuraciones Finales Adjuntos**
   - **Anexo A:** Diagramas de red de Visio actualizados (versión "As-Built").
   - **Anexo B:** Archivos de texto con las configuraciones finales extraídas de cada switch y del controlador WLAN.
   - **Anexo C:** Informe del post-deployment site survey de Ekahau, mostrando los mapas de calor finales para RSSI, SNR y CCI.
