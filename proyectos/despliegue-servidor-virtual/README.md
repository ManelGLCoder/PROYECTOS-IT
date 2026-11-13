# Caso de Estudio: Despliegue de Servidor de Virtualización Bare-Metal con Proxmox VE e Integración en Red Segura

Este proyecto documenta la reconversión de una torre de escritorio recuperada y optimizada térmicamente (**Proyecto 01**) en un **Hipervisor Bare-Metal Tipo 1** utilizando **Proxmox VE 9** (basado en Debian 13 *Trixie*). El servidor se integra de forma cableada dentro del segmento seguro (`192.168.45.0/24`) definido en el **Proyecto 02**, separando físicamente el almacenamiento por rendimiento (SSD + HDD) y aplicando políticas de filtrado perimetral.

📝 **Nota de Documentación:** Para examinar el informe con todo el desglose técnico paso a paso, comandos y capturas de verificación, consulta el **[📖 Informe Técnico](INFORME_TECNICO.md)**.

## 🛠 Ficha Técnica del Hardware

* **Host de Virtualización (Servidor PVE):** Torre dedicada (Intel Core i7-6700, 16 GB RAM DDR4 @ 2133 MHz Dual Channel, placa base MSI B150 GAMING M3 con BIOS AMI B.70).
* **Almacenamiento del Sistema Base:** SSD Crucial MX300 de 256 GB (`/dev/sda`, dedicado al sistema operativo y pool rápido `LVM-Thin` para VMs).
* **Almacenamiento de Datos y Backups:** HDD Western Digital Blue de 1 TB (`/dev/sdb`, ~932 GiB útiles, montado por `UUID` como `HDD_Data` para copias `Backup`, ISOs y plantillas).
* **Interfaz y Enlace de Red:** Tarjeta Gigabit Ethernet (`nic0`) conectada mediante latiguillo Cat 6 al Nodo Satélite 3 TP-Link Deco M4R (Modo AP) con IP estática `192.168.45.30/24` sobre el puente `vmbr0`.
* **Kit de Medios Extraíbles (Dual Ventoy GPT/UEFI):** Unidad principal **`VENTOY_PROD`** (Samsung BAR Plus 128 GB) y unidad de contingencia **`VENTOY_BKUP`** (Kingston DataTraveler SE9 Gen 3 64 GB).

## 📈 Metodología de Despliegue y Competencias Técnicas

Para consolidar una infraestructura de virtualización estable, segura y reversible, la implementación se articuló sobre cuatro pilares técnicos:

1. **Continuidad Operativa y Rollback:** Extracción previa de la clave de licencia OEM desde PowerShell hacia `VENTOY_BKUP`, estableciendo un protocolo de reversión mediante `diskpart` (`clean`) para restaurar Windows 10 en caso necesario.
2. **Preparación de Firmware y Virtualización:** Habilitación en BIOS de las extensiones `Intel VT-x`, `Intel VT-d` (IOMMU), modo `AHCI` y arranque `UEFI` mediante Ventoy en modo `GRUB2`.
3. **Administración Linux y Repositorios DEB822:** Migración de las fuentes empresariales al canal comunitario `pve-no-subscription` en formato `.sources` para Debian 13 (*Trixie*), actualización del kernel y montaje persistente del disco secundario en `/etc/fstab` mediante `UUID` con directiva `nofail`.
4. **Arquitectura de Red L2 y Cortafuegos Zero Trust:** Enlace de la tarjeta física `nic0` al switch virtual `vmbr0` y activación de `pve-firewall` a nivel de Datacenter con política de entrada restrictiva (`DROP`) y lista blanca exclusiva para `192.168.45.0/24` (puertos `8006,22`).

## ✅ Resultados del Despliegue y Estado Operativo

Hitos completados y verificados tras la puesta en marcha del hipervisor:

1. **Actualización y Canal Comunitario:** Repositorio `pve-no-subscription` configurado correctamente sobre Debian *Trixie*, con el sistema y el kernel actualizados a la última versión estable sin paquetes pendientes.
2. **Conmutación Virtual Capa 2 (`vmbr0`):** Interfaz física `nic0` vinculada como *uplink* al puente `vmbr0` (`192.168.45.30/24`), manteniendo el aislamiento respecto a la red Wi-Fi de invitados (`Casa_Invitados_IoT`).
3. **Securización Perimetral:** Cortafuegos `pve-firewall` activo a nivel de Datacenter con política `Input: DROP` y acceso administrativo restringido al segmento cableado seguro.
4. **Almacenamiento Híbrido Persistente:** Disco secundario `/dev/sdb1` formateado en `ext4`, montado automáticamente en `/mnt/hdd_datos` mediante su `UUID` y vinculado en Proxmox como `HDD_Data` exclusivamente para `Backup`, `ISO image` y `Container template`.

## 💡 Conclusiones

El proyecto valida la transición de un equipo doméstico reutilizado hacia un servidor de virtualización Bare-Metal listo para alojar entornos de laboratorio aislados:

* **Optimización de Recursos:** La separación entre el SSD Crucial (`local-lvm`) y el HDD mecánico (`HDD_Data`) garantiza velocidad en la ejecución de futuras máquinas virtuales sin sacrificar capacidad de respaldo.
* **Seguridad por Diseño:** La combinación del aislamiento físico de red heredado del **Proyecto 02** con las reglas restrictivas de `pve-firewall` protege la consola de gestión desde el primer arranque.
* **Adaptación a Entornos Modernos:** La resolución de particularidades propias de Debian 13 (*Trixie*), como el formato de repositorios `.sources` y la nomenclatura de interfaces `nic0`, consolida una base documentada y replicable.

[↩ Volver al Portafolio Principal](../../README.md)
