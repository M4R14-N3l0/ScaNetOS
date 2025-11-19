# Módulo: Reconocimiento Web (Fingerprinting)

## [1] Webanalyze/WhatWeb (Fingerprint) <--- ¡CONSOLIDADO!

El objetivo de este módulo es realizar la "huella digital" (Fingerprinting) de la aplicación web, una fase crucial para entender la superficie de ataque antes de cualquier prueba activa.

### 🎯 Objetivo
Identificar las tecnologías que usa el servidor, desde el backend (Lenguajes de programación, CMS, Servidores Web) hasta el frontend (Librerías JavaScript, Frameworks).

### 🛠️ Herramientas Utilizadas
Este módulo ejecuta de forma consolidada las siguientes herramientas, enfocadas en la recopilación de datos pasiva y semi-activa:

Webanalyze: Enfocado en la detección de frameworks de JavaScript, librerías y tecnologías del lado del cliente.

WhatWeb: Especializado en la detección amplia de tecnologías, incluyendo servidores web (Apache, Nginx), sistemas operativos, versiones de PHP/Python y módulos específicos.

### Paso a Paso para el Módulo [1]:

Requisito: Debe haber definido el objetivo previamente con la opción [0].

Selección: Elige la opción [1] Reconocimiento web (Passive/Active) en el menú principal.

Ejecución: El panel comenzará a ejecutar Webanalyze seguido de WhatWeb en el TARGET_URL definido.

Visualización: El script mostrará un resumen conciso de las tecnologías más importantes encontradas (ej: "WordPress v6.4, Nginx/1.18, jQuery").

Guardado de Resultados: Todos los logs completos de Webanalyze (.json) y WhatWeb (.txt) se guardan automáticamente en la carpeta de resultados del objetivo para su análisis detallado posterior. La ruta completa de los resultados de reconocimiento es: ~/scanetos_workspaces/url del sitio/recon

<div align="center">
  <img src="../imagenes/whatweb.png" alt="Salida de WhatWeb mostrando tecnologías y versiones" width="600px">
</div>

### 💡 Valor para el Auditor

La información de Fingerprinting es vital porque:

Define Prioridades: Si el sitio usa WordPress v5.0, el auditor sabe que debe enfocarse inmediatamente en buscar vulnerabilidades específicas de esa versión.

Reduce el Ruido: Si se detecta un Web Application Firewall (WAF), el auditor sabrá que las pruebas de inyección deben ser más sutiles o que deben usar técnicas de evasión.

## [2] Nmap (Fast Scan)

Este módulo se enfoca en el escaneo de red fundamental para determinar la conectividad, los puertos abiertos y los servicios básicos del objetivo, utilizando la herramienta estándar de la industria, Nmap.

🎯 Objetivo
Identificar la topología de red, los puertos TCP y UDP accesibles, y las versiones de los servicios que se ejecutan en esos puertos. Esto es crucial para saber dónde enfocar los ataques de la siguiente fase.

🛠️ Herramienta Utilizada
Nmap (Network Mapper): Ejecutado en modo de escaneo rápido (-F o --top-ports), enfocándose solo en los puertos más comunes (HTTP, HTTPS, SSH, FTP, etc.) para reducir el tiempo de ejecución.

Flujo Paso a Paso del Módulo [2]:

Selección: Elige la opción [2] Nmap (Fast Scan) en el menú principal.

Ejecución: El script ejecutará Nmap contra la IP o el dominio del objetivo que definiste en el Paso [0].

Visualización en Vivo: El panel mostrará la salida de Nmap directamente en la terminal, indicando los puertos que están open (abiertos) y la versión del servicio detectado (ej: 80/tcp open http Apache httpd 2.4.41).

Guardado de Resultados: Se genera un log de Nmap en formato nmap o xml para el análisis y reporte final.

Ruta de Resultados: La salida detallada para este módulo se guarda en: ~/scanetos_workspaces/url del sitio/recon con el nombre de nmap_full.txt
💡 Valor para el Auditor
Un escaneo rápido de puertos es el mapa del sitio web. Permite:

Descubrir Servicios Inesperados: Identificar un puerto 3306 (MySQL) o 21 (FTP) abierto en un servidor web, lo cual indica un posible fallo de configuración grave.

Ahorrar Tiempo: Al ser un escaneo rápido, proporciona la información necesaria para el siguiente paso sin ejecutar un barrido de 65.535 puertos, lo que puede tardar horas.

<div align="center">
  <img src="../imagenes/nmap-fast.png" alt="Salida de NMAP fast" width="600px">
</div>

## [3] Fuzzing de Directorios (ffuf/GoBuster)



