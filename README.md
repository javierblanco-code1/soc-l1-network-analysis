# SOC L1: Network Traffic Analysis & Incident Reporting with Wireshark

## 📌 Descripción
Proyecto de análisis de red focalizado en la inspección profunda de paquetes (*Deep Packet Inspection*) para un Analista SOC L1. Incluye el análisis de capturas `.pcap`, aislamiento de comportamientos anómalos y la redacción estándar de un ticket de incidente informático.

## 🛠️ Herramientas Utilizadas
- **Wireshark / TShark:** Filtrado y análisis de protocolos de red (TCP, HTTP, DNS).
- **Markdown:** Estructuración del Ticket de Incidente SOC.

## 🔍 Hallazgos Principales
1. **Reconocimiento:** Identificación de un escaneo masivo de puertos TCP SYN originado por una IP interna.
2. **Exfiltración / Inseguridad:** Detección de tráfico no cifrado enviando peticiones `HTTP POST` sensibles hacia servidores externos.

## 📂 Contenido del Repositorio
- `ticket_incidente.md`: Informe técnico estructurado para el escalado de la amenaza hacia L2.
- `filtros_wireshark.txt`: Colección de filtros de visualización aplicados durante la investigación.
