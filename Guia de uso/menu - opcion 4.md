# Módulo [4] Herramientas GUI (ZAP, Burp)

[1] Burp Suite Community/Pro

Este módulo se centra en la configuración de Burp Suite para interceptar el tráfico HTTP/S entre el navegador y la aplicación web objetivo. Su función principal dentro de ScaNetOS es capturar peticiones complejas (como POST) que serán auditadas en otros módulos  (especialmente SQLMap).

🎯 Objetivo:

Captura Precisa: Obtener el cuerpo exacto de las peticiones POST de formularios y APIs.

Generación de Archivo: Crear un archivo de texto (.txt) con la petición HTTP cruda para alimentar a herramientas automáticas como SQLMap.

🛠️ Herramientas Utilizadas:

Burp Suite (Community/Professional): El proxy de intercepción estándar de la industria.

⚙️ Flujo Paso a Paso en ScaNetOS: 

Este módulo asume que Burp Suite está instalado y que el usuario puede configurarlo. El panel de ScaNetOS facilita el proceso indicando los pasos y la ruta de guardado.

1. 🚀 Preparación del Entorno:
   
Inicio del Proxy: El panel te indicará que inicies Burp Suite y te asegures de que el módulo Proxy está activo y escuchando (generalmente en 127.0.0.1:8080).

2. 📝 Captura de la Petición Crítica:
   
Localización: Navega en el navegador (usando el proxy de Burp) a la página que contiene el formulario o la API a auditar (ej: la página de login de OWASP Juice Shop).

Intercepción: En la pestaña Proxy -> Intercept de Burp, asegúrate de que la intercepción esté activada.

Envío de Datos: Introduce datos de prueba en los campos (ej: usuario y password) y presiona "Login". Burp pausará el tráfico.
