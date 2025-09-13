# Plan de Estudio Intensivo para Analista SOC (Blue Team)

Este repositorio documenta un plan de estudio intensivo de 4 semanas diseñado para construir y consolidar las habilidades fundamentales requeridas para un rol de Analista de Ciberseguridad en un Centro de Operaciones de Seguridad (SOC).

El objetivo principal es pasar de los conceptos teóricos a la aplicación práctica, cubriendo desde los fundamentos de redes y sistemas hasta el análisis de logs, uso de herramientas SIEM/EDR y la respuesta a incidentes en entornos IT y OT.

---

## 📅 Temario del Plan de Estudio

El plan está estructurado en cuatro semanas temáticas, cada una con un objetivo específico.

### **Semana 1 – Fundamentos de SOC e Infraestructura**
*Objetivo: Refrescar las bases de IT/OT y empezar con el monitoreo de sistemas.*

*   **Día 1:** Repaso de conceptos SOC → Detección, análisis, respuesta y escalamiento. Estudio de ejemplos de triaje de alertas (CrowdStrike, SentinelOne).
*   **Día 2:** Windows Server & Active Directory → Revisión de logs de autenticación, eventos de privilegios y creación de usuarios.
*   **Día 3:** Linux → Comandos de monitoreo (`top`, `ps`, `who`, `last`) y análisis de logs (`/var/log/auth.log`).
*   **Día 4:** Redes básicas → Repaso de TCP/IP, firewalls, IDS/IPS. Práctica con Wireshark analizando tráfico normal vs. sospechoso.
*   **Día 5:** OT Overview → Protocolos industriales (Modbus, OPC UA, DNP3) y diferencias clave entre redes IT y OT.

### **Semana 2 – SIEM, Logs y Detección**
*Objetivo: Ganar práctica con herramientas SIEM y el análisis de eventos de seguridad.*

*   **Día 1:** Introducción a SIEM (Splunk / Wazuh). Creación de consultas básicas (failed logins, brute force attempts).
*   **Día 2:** Análisis de logs de Windows (Event IDs comunes: 4624, 4625, 4672).
*   **Día 3:** Análisis de logs de Linux (Intentos de conexión SSH, escalamiento de privilegios con `sudo`).
*   **Día 4:** Casos prácticos de correlación → Combinación de eventos de distintas fuentes para detectar un ataque.
*   **Día 5:** Repaso y práctica en un laboratorio personal con Wazuh o Splunk Free.

### **Semana 3 – EDR y Análisis de Malware**
*Objetivo: Familiarizarse con la lógica de detección en endpoints y las tácticas de ataques reales.*

*   **Día 1:** Conceptos de EDR (CrowdStrike, SentinelOne, Defender for Endpoint). ¿Qué detectan y qué logs generan?
*   **Día 2:** Técnicas de malware → Persistencia, escalada de privilegios y movimiento lateral.
*   **Día 3:** Análisis de sandbox con VirusTotal y Any.Run (análisis estático y dinámico básico).
*   **Día 4:** Revisión de la matriz MITRE ATT&CK y mapeo de técnicas a ejemplos de ataques.
*   **Día 5:** Caso práctico → Simulación de un ataque en el laboratorio (ej. `nmap`, `hydra`) y detección de la actividad en los logs.

### **Semana 4 – Respuesta a Incidentes y Seguridad OT**
*Objetivo: Unir todos los conocimientos y practicar el ciclo completo de gestión de incidentes.*

*   **Día 1:** El ciclo de vida de la respuesta a incidentes → Detección, contención, erradicación y recuperación.
*   **Día 2:** Hardening en entornos OT/ICS → Buenas prácticas (segmentación de red, mínimo privilegio, backups).
*   **Día 3:** Revisión de casos de estudio reales de ciberataques en OT (ej. Stuxnet, Colonial Pipeline).
*   **Día 4:** Mini-simulacro → Documentación del plan de respuesta para un incidente ficticio (ej. tráfico sospechoso + logins fallidos en AD).
*   **Día 5:** Repaso general y práctica final en el laboratorio.

---

## 🛠️ Recursos Clave y Herramientas

Para apoyar este plan de estudio, se utilizarán los siguientes recursos (gratuitos o con versiones gratuitas):

*   **TryHackMe:** Rutas de aprendizaje [Blue Team Fundamentals](https://tryhackme.com/path/outline/blueteam) y [SOC Level 1](https://tryhackme.com/path/outline/soclevel1).
*   **Wazuh:** SIEM y XDR de código abierto, ideal para montar un laboratorio personal.
*   **MITRE ATT&CK:** Base de conocimiento global sobre tácticas y técnicas de adversarios.
*   **Wireshark Sample Captures:** Repositorio de capturas de paquetes para practicar análisis de red.
*   **SANS Blue Team Cheat Sheets:** Hojas de referencia y pósteres con comandos y conceptos útiles.

---

## 📂 Estructura de este Repositorio

El progreso y las notas de estudio se documentarán en este repositorio siguiendo una estructura de carpetas por semana. Cada día de estudio tendrá su propio archivo Markdown (`.md`) con notas, comandos, capturas de pantalla y resúmenes.

```
/
|-- Semana1-Fundamentos_SOC/
|   |-- Dia1-Conceptos_SOC.md
|   |-- Dia2-Windows_AD.md
|   `-- ...
|-- Semana2-SIEM_Logs/
|-- Semana3-EDR_Malware/
|-- Semana4-Respuesta_Incidentes/
`-- README.md
```
