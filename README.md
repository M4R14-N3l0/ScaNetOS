# ScaNetOS 1.0

<a href="https://sourceforge.net/projects/scanetos/">
  <img src="imagenes/logoSN.png" alt="Logo de ScaNetOS" width="200px">
</a>

**ScaNetOS** es una máquina virtual Linux (basada en Debian) diseñada para **auditorías web en entornos controlados y con permiso**.  
Incluye un panel en terminal llamado **ScaNet Panel** que centraliza las tareas típicas de un analista web: reconocimiento, análisis HTTP, pruebas de APIs y lanzamiento de herramientas GUI (Burp, ZAP, etc.).

> ⚠️ ScaNetOS está pensada únicamente para uso educativo y auditorías autorizadas.  
> El autor no se hace responsable del uso indebido de la herramienta.

---

## 📸 Preview

### ScaNet Panel
![ScaNet Panel Screenshot](imagenes/ScaNetOS.png)

--

## 🖥️ Requisitos

- VirtualBox / VMware (probado principalmente con VirtualBox)
- Al menos:
  - 2 CPU
  - 4 GB de RAM
  - 40 GB de disco
- Conexión a Internet (recomendada para actualizar paquetes y usar ciertas herramientas)

---

## 📦 Descarga

- **Imagen OVA**: `ScaNetOS-1.0.ova`  
  (Subida en: https://sourceforge.net/projects/scanetos/)

En VirtualBox:  
`Archivo → Importar servicio virtualizado → Selecciona ScaNetOS-1.0.ova`

---

## 🔐 Credenciales por defecto

- Usuario normal:
  - **Usuario:** `scanetuser`
  - **Contraseña:** `scanetuser`

---

## 🧭 ScaNet Panel

Al iniciar sesión con `scanetuser` abre una terminal. Inmediatamente se ejecuta el scanet-panel.
