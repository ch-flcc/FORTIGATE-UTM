# Implementación de Seguridad Perimetral y Conectividad con Fortinet

Este proyecto presenta una solución integral de ciberseguridad para **Mixercon**, una empresa del sector construcción con múltiples sedes. El objetivo es centralizar la gestión de amenazas, asegurar la interconexión de locales mediante una arquitectura **Hub-and-Spoke** y habilitar el acceso remoto seguro.

## 🚀 Descripción del Proyecto

La solución se basa en el despliegue de firewalls de próxima generación (NGFW) **FortiGate** para mitigar riesgos de ataques dirigidos, fuga de datos y garantizar la continuidad operativa. Se diseñó un entorno simulado en **GNS3** que replica la infraestructura de red real de la compañía.

### Características Principales:
* **Arquitectura Hub-and-Spoke:** Centralización del tráfico de internet y políticas de seguridad en un nodo principal.
* **Gestión Unificada de Amenazas (UTM):** Implementación de filtrado web, control de aplicaciones y antivirus perimetral.
* **VPN SSL:** Acceso remoto cifrado para colaboradores externos con políticas de segmentación.
* **Inspección de Tráfico:** Configuración de modos *Proxy* y *Flow* según la necesidad de rendimiento o profundidad de análisis.

## 🛠️ Tecnologías Utilizadas
* **FortiOS 7.x** (FortiGate VM)
* **GNS3** (Entorno de simulación de red)
* **Cisco Switch L2** (Simulación de WAN/LAN)
* **Docker Container** (WebTerm para pruebas de navegación)

## 📂 Estructura de Configuración

### 1. Conectividad y NAT
Se configuró el acceso a Internet centralizado. Solo el **Hub** posee salida directa, gestionando el tráfico de los **Spokes** para asegurar que todo el flujo de datos sea inspeccionado por los motores de seguridad.

### 2. Perfiles de Seguridad (UTM)
* **Web Filter:** Bloqueo de categorías de alto riesgo y redes sociales para optimizar el ancho de banda.
* **Application Control:** Restricción de software P2P y aplicaciones no autorizadas.
* **SSL Inspection:** Inspección de certificados para detectar amenazas ocultas en tráfico HTTPS.

### 3. VPN SSL
Configuración de un portal cautivo con **Split Tunneling**, permitiendo que solo el tráfico corporativo pase por el túnel, mejorando la latencia del usuario.

## 📈 Resultados
* **Visibilidad:** Control total sobre las aplicaciones y sitios web utilizados en la red.
* **Seguridad:** Reducción de la superficie de ataque mediante el cierre de puertos innecesarios y uso de VPN.
* **Escalabilidad:** El diseño permite añadir nuevos locales (Spokes) de manera rápida y estandarizada.

---
*Nota: Este proyecto fue desarrollado con fines de diseño de arquitectura y validación de seguridad en entornos controlados.*