# Caso de Estudio: Reingeniería de Red Local, Fortificación de Perímetro y Despliegue de Arquitectura Zero Trust

Este proyecto documenta la auditoría técnica de infraestructura doméstica, segmentación lógica perimetral y endurecimiento de host en un endpoint crítico (Steam Machine bajo SteamOS / Arch Linux) para mitigar vectores de intrusión y movimientos laterales.

📝 **Nota de Documentación:** Para examinar el informe con todo el desglose paso a paso y capturas de resultados, consulta el **[📖 Informe Técnico](./INFORME_TECNICO.md)**. 

## 🛠 Ficha Técnica del Hardware

* **Pasarela Perimetral (Gateway L3):** Sagemcom F@st 5657
* **Infraestructura de Red Inalámbrica (Malla L2):** TP-Link Deco M4R (Modo AP)
* **Host Crítico (Endpoint Linux):** Steam Machine (SteamOS / Arch Linux)
* **Estación de Auditoría Externa:** Portátil MSI Pulse 15 B13V (Windows 11)

## 📈 Metodología de Pruebas y Competencias Técnicas

Para verificar el aislamiento de los entornos bajo una filosofía **Zero Trust** y demostrar las competencias en seguridad perimetral, las pruebas se ejecutaron desde un segmento Wi-Fi aislado utilizando las siguientes tecnologías:

1. **Arquitectura de Seguridad y Segmentación:** Configuración del sistema Mesh en puente L2 anulando el Doble NAT, combinada con la inhabilitación del acceso local en la red de invitados para aislar por completo amenazas potenciales.
2. **Reestructuración de Redes (Capa 3):** Migración manual del direccionamiento IP residencial por defecto a la subred personalizada `192.168.45.0/24` y desactivación de vulnerabilidades perimetrales como UPnP y WPS.
3. **Hardening de Host con Netfilter (iptables):** Despliegue de políticas restrictivas basadas en estado (`conntrack`) en el kernel de Linux, forzando un filtrado estricto en modo sigilo (`INPUT DROP`).
4. **Auditoría de Sockets y Análisis ARP:** Diagnóstico de puertos a bajo nivel con la herramienta síncrona `curl` e inspección del estado físico de comunicación local monitorizando la tabla de vecinos (`ip neighbor`).

## 📊 Resumen Ejecutivo del Protocolo de Verificación

Resultados obtenidos durante la auditoría de caja negra:

1. **Test 1 (Prueba ICMP):** `ping 192.168.45.10` con **100% de pérdida de paquetes** (host opaco al diagnóstico).
2. **Test 2 (Escaneo de Sockets):** `curl --connect-timeout 2 -v http://192.168.45.10:22` abortado por timeout estricto a los 2001 ms (Modo Sigilo).
3. **Test 3 (Línea Base de Red):** `ping 192.168.45.1` con respuestas estables (4ms), validando salida WAN y bloqueo granular.
4. **Test 4 (Tabla de Vecinos):** `ip neighbor show` registrando el equipo en estado `STALE` (canal local cortado).

## 💡 Conclusiones

El proyecto valida experimentalmente la efectividad de aplicar un modelo de seguridad restrictivo combinado con una segmentación física y lógica de la infraestructura de red:

* **Estabilización Lógica:** Implementación de políticas de filtrado estrictas en el kernel de Linux y aislamiento de los dispositivos inalámbricos vulnerables en redes de invitados para eliminar riesgos de salto interno.
* **Invisibilidad Perimetral:** El uso del modo sigilo (*drop*) destruye paquetes sospechosos en origen y oculta los puertos abiertos ante escaneos de reconocimiento sin alterar el tráfico saliente legítimo.
* **Eficiencia en el Enrutamiento:** La configuración del sistema Mesh en Modo AP erradica las latencias provocadas por el Doble NAT, resolviendo los problemas de cobertura sin comprometer la seguridad implementada.

[↩️ Volver al Portafolio Principal](../../README.md)
