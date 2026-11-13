#### 🚀 Mi Portafolio de Proyectos IT & Infraestructura

¡Hola! Soy **Manel Gisbert López**, técnico y especialista en infraestructura de TI. Bienvenido a mi repositorio central de portafolio. Aquí coordino y documento mis laboratorios prácticos, arquitecturas de hardware y gestión de sistemas. 

#### 📂 Índice de Proyectos

A continuación se detallan los proyectos y laboratorios técnicos que he desarrollado, ordenados por categorías. Cada enlace contiene la documentación técnica completa, metodologías y evidencias visuales. 

#### 🛠️ Hardware y Soporte Avanzado

* **[01_Optimización Térmica y Restauración de Rendimiento en Entorno Windows 10](./proyectos/mantenimiento-pc-w10/README.md)** 

  * **Descripción:** Auditoría técnica de rendimiento y mantenimiento correctivo/preventivo profundo sobre una arquitectura Intel/NVIDIA para mitigar problemas de degradación térmica (*thermal throttling*).
  * **Impacto Clave:** Reducción neta de **14°C** en la temperatura máxima de la CPU y eliminación de fallos por sobrecalentamiento bajo pruebas de estrés sintético (Cinebench).
  * **Core Stack:** HWiNFO64, Cinebench, FurMark, Instrumentación de precisión ESD.

  
* **[02_Reingeniería de Red Local, Fortificación de Perímetro y Despliegue de Arquitectura Zero Trust](./proyectos/reingeneria-red-local/README.md)**

  * **Descripción:** Reestructuración de topología de red doméstica mediante segmentación física en puente de Capa 2 y endurecimiento estricto basado en host (*host-based hardening*) en Capa 4 sobre un activo crítico (**Steam Machine bajo SteamOS / Arch Linux**).
  * **Impacto Clave:** Aislamiento local del 100% de dispositivos IoT/visitas, invisibilidad total (Stealth Mode) de sockets internos frente a escaneos y eliminación del Doble NAT mediante infraestructura Mesh en Modo AP.
  * **Core Stack:** `iptables` (Netfilter Kernel), `curl` síncrono, Sagemcom F@st 5657, TP-Link Deco M4R, tablas ARP (`ip neighbor`).
  
#### 🖥 Virtualización e Infraestructura de Servidores

* **[03_Despliegue de Servidor de Virtualización Bare-Metal con Proxmox VE e Integración en Red Segura](./proyectos/despliegue-servidor-virtual/README.md)**
    * **Descripción:** Reconversión de una torre de hardware dedicado en un hipervisor Tipo 1 (**Proxmox VE 9** sobre Debian 13 *Trixie*) integrado en el segmento cableado seguro (`192.168.45.0/24`), con separación física de almacenamiento híbrido (SSD + HDD por UUID), cortafuegos perimetral (`pve-firewall`) y protocolo de reversión (*rollback*) documentado.
    * **Impacto Clave:** Infraestructura base operativa para alojar máquinas virtuales y contenedores de laboratorio con aislamiento de red, canal comunitario actualizado y ~932 GiB de almacenamiento masivo persistente para backups e ISOs.
    * **Core Stack:** Proxmox VE 9 (KVM/LXC), Debian 13 (Trixie), Linux Bridge (`vmbr0` / `nic0`), `pve-firewall`, Ventoy Dual Multiboot, `parted` / `fstab` (UUID).


#### 🛠️ Tecnologías y Competencias Centrales

* **Hardware & Sistemas:** Diagnóstico avanzado de fallos de hardware, mantenimiento preventivo/correctivo, gestión térmica, ensamblaje y auditoría de componentes de servidores/PCs.
* **Herramientas de Diagnóstico:** HWiNFO64, Cinebench, FurMark, herramientas nativas de administración Windows (msinfo32, Administrador de Tareas).
* **Seguridad Operativa:** Protocolos de desenergización, mitigación de descargas electrostáticas (ESD) y manejo seguro de compuestos químicos (Alcohol isopropílico al 99.9%).

#### 📫 Contacto

* **LinkedIn:** [linkedin.com/in/manelgisbertlopez](https://www.linkedin.com/in/manelgisbertl%C3%B3pez/)
* **Email:** manelglcoder@gmail.com
