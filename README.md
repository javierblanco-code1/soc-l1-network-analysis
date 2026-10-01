# SOC L1 Network Analysis — Wireshark / TShark

Proyecto de análisis de tráfico orientado a **Network Security Monitoring (NSM)** y al triaje inicial de incidentes.

> **Contexto:** laboratorio / portfolio. Las capturas utilizadas deben ser propias, de laboratorio o estar expresamente autorizadas para análisis.

## Objetivo

Transformar una captura PCAP en hallazgos documentables:

`PCAP → Filtering → Traffic Analysis → IOC extraction → Finding → Triage → Ticket`

## Casos investigados

- TCP SYN / port scanning.
- HTTP POST y tráfico no cifrado.
- Anomalías DNS.
- Conexiones hacia destinos de baja reputación.

Estos patrones son señales de investigación; el contexto adicional determina si corresponde cierre, investigación o escalamiento.

## Herramientas

- Wireshark
- TShark
- Display Filters
- PCAP
- Markdown
- Git / GitHub

## Workflow SOC L1

1. Preservar la captura y documentar su origen.
2. Crear filtros para reducir ruido.
3. Identificar hosts, puertos y protocolos relevantes.
4. Construir timeline.
5. Extraer indicadores observables.
6. Correlacionar con otros datos disponibles.
7. Documentar hallazgos y criterios de escalamiento.

## Filtros de referencia

Ejemplos de filtros útiles:

```
tcp.flags.syn == 1 && tcp.flags.ack == 0
http.request.method == "POST"
dns
```

Los filtros deben adaptarse al objetivo de la investigación y no interpretarse aislados.

## Artefactos

- `ticket_incidente.md` — ticket técnico.
- `filtros_wireshark.txt` — filtros de análisis.
- PCAP / capturas — solo cuando su distribución esté autorizada.

## Próximo Case Study

La siguiente evolución del proyecto será un caso formal de **network investigation** con:

- timeline;
- IPs y puertos;
- evidencia visual;
- filtros utilizados;
- hallazgos;
- IoCs;
- decisión de triaje;
- criterios de escalamiento.

## Data Handling

No publicar:

- tráfico de terceros;
- credenciales;
- PII;
- tokens;
- capturas de producción;
- archivos sensibles.

Preferir datasets sintéticos, malware-analysis datasets autorizados o laboratorio propio.

## Portfolio

Este repositorio demuestra **network traffic analysis, Wireshark/TShark, IOC extraction, incident documentation y SOC L1 triage**.
