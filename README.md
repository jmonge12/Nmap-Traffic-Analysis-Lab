# Nmap-Traffic-Analysis-Lab
Laboratorio práctico de auditoría de red con Nmap y análisis de logs en tiempo real utilizando un servidor HTTP en Python.
# Análisis de Tráfico de Red e Interrogación de Servicios con Nmap

## Descripción del Proyecto
Este laboratorio práctico demuestra la interacción directa entre un auditor de seguridad (atacante) y un servidor web (víctima) en un entorno controlado. El objetivo es identificar puertos abiertos, analizar el impacto de la detección de versiones de software (`-sV`) y evaluar cómo un servidor web registra y detecta las huellas de un escaneo automatizado en sus logs de acceso.

## Herramientas Utilizadas
*   **Sistemas Operativos:** Kali Linux (Entorno de auditoría)
*   **Herramientas de Reconocimiento:** Nmap 7.98
*   **Servidores Web:** Python 3.13 (SimpleHTTPServer)
*   **Entorno Virtual:** VirtualBox

---

## Fases del Laboratorio

### 1. Despliegue del Servicio (Víctima)
Se levantó un servidor web básico en Python escuchando en el puerto 8000 para simular un servicio corporativo expuesto:

python3 -m http.server 8000

### 2. Escaneo Inicial vs. Detección Avanzada (Atacante)
*   **Escaneo Básico (`nmap -p 8000 localhost`):** Identifica que el puerto está abierto y asume de forma genérica el servicio por defecto (`http-alt`).
*   **Escaneo de Versiones (`nmap -sV -p 8000 localhost`):** Interroga directamente el banner del puerto abierto. Logra extraer con precisión quirúrgica el software y su versión exacta: `SimpleHTTPServer 0.6 (Python 3.13.12)`.

![Resultados de Escaneo Nmap](https://github.com/jmonge12/Nmap-Traffic-Analysis-Lab/blob/31915986bbcb7fa4a49d6338f92d2222a8fa5588/escaneo_nmap.png.png)
