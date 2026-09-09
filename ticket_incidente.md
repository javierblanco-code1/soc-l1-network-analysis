# [TICKET #SOC-2026-089] Detección de Escaneo de Puertos y Exfiltración HTTP

**Fecha de Reporte:** 2026-09-08  
**Analista Responsable:** Javier Blanco (SOC L1)  
**Estado:** Escalado a L2 / Mitigación Pendiente  
**Severidad:** Media / Alta  

---

### 1. Resumen Ejecutivo
Durante la revisión de capturas de tráfico de red (`trafico_sospechoso.pcap`), se identificó comportamiento anómalo proveniente de la IP interna `192.168.1.105` dirigido hacia múltiples direcciones de la red local e infraestructura web externa.

### 2. Detalle Técnico de los Hallazgos
- **Vector 1 (Escaneo de Puertos):** Se registraron más de 1,200 intentos de conexión con la bandera `TCP SYN` activa hacia el rango `192.168.1.0/24` en un intervalo de 10 segundos, característico de una herramienta de reconocimiento automático (Nmap).
- **Vector 2 (Tráfico Inseguro):** Se interceptó una petición `HTTP POST` hacia el puerto 80 sin cifrado SSL/TLS enviando datos de autenticación en texto claro.

### 3. Indicadores de Compromiso (IoCs)
- **IP Origen:** `192.168.1.105` (Equipo interno sospechoso)
- **IP Destino:** `45.33.32.156` (Servidor HTTP externo)
- **Puertos de Interés:** 80 (HTTP), 445 (SMB), 22 (SSH)

### 4. Acciones Inmediatas Tomadas (L1)
1. Aislamiento preventivo de la interfaz de red del host `192.168.1.105`.
2. Exportación de la traza de red reducida con el tráfico malicioso filtrado para su archivo.

### 5. Recomendaciones y Escalado a L2
- Notificar al equipo de SysAdmin para ejecutar un análisis de Malware en el host de origen.
- Bloquear la comunicación saliente hacia la IP externa `45.33.32.156` en el Firewall perimetral.
