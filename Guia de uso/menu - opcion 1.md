# Módulo [1]: Reconocimiento Web (Fingerprinting)

El objetivo de este módulo es realizar la "huella digital" (Fingerprinting) de la aplicación web, una fase crucial para entender la superficie de ataque antes de cualquier prueba activa.

## 🎯 Objetivo
Identificar las tecnologías que usa el servidor, desde el backend (Lenguajes de programación, CMS, Servidores Web) hasta el frontend (Librerías JavaScript, Frameworks).

## 🛠️ Herramientas Utilizadas
Este módulo ejecuta de forma consolidada las siguientes herramientas, enfocadas en la recopilación de datos pasiva y semi-activa:

Webanalyze: Enfocado en la detección de frameworks de JavaScript, librerías y tecnologías del lado del cliente.

WhatWeb: Especializado en la detección amplia de tecnologías, incluyendo servidores web (Apache, Nginx), sistemas operativos, versiones de PHP/Python y módulos específicos.

### Paso a Paso para el Módulo [1]:

Requisito: Debe haber definido el objetivo previamente con la opción [0].

Selección: Elige la opción [1] Reconocimiento web (Passive/Active) en el menú principal.

Ejecución: El panel comenzará a ejecutar Webanalyze seguido de WhatWeb en el TARGET_URL definido.

Visualización: El script mostrará un resumen conciso de las tecnologías más importantes encontradas (ej: "WordPress v6.4, Nginx/1.18, jQuery").

Guardado de Resultados: Todos los logs completos de Webanalyze (.json) y WhatWeb (.txt) se guardan automáticamente en la carpeta de resultados del objetivo para su análisis detallado posterior. La ruta completa de los resultados de reconocimiento es: ~/scanetos_workspaces/rootedcon.com/recon

<div align="center">
  <img src="imagenes/whatweb.png" alt="Salida de WhatWeb mostrando tecnologías y versiones" width="600px">
</div>

### 💡 Valor para el Auditor

La información de Fingerprinting es vital porque:

Define Prioridades: Si el sitio usa WordPress v5.0, el auditor sabe que debe enfocarse inmediatamente en buscar vulnerabilidades específicas de esa versión.

Reduce el Ruido: Si se detecta un Web Application Firewall (WAF), el auditor sabrá que las pruebas de inyección deben ser más sutiles o que deben usar técnicas de evasión.
