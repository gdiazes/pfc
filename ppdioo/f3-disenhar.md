#### **Plantilla Detallada: Diseño de Bajo Nivel (LLD) - Extracto**

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
