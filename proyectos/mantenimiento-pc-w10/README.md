#### Caso de Estudio: Optimización Térmica y Restauración de Rendimiento en Entorno Windows 10

Este proyecto documenta de extremo a extremo el proceso de auditoría de rendimiento, mantenimiento físico de hardware y análisis comparativo de una torre de ordenador con sistema operativo Windows 10. 

📝 **Nota de Documentación:** Para examinar el informe con todo el desglose fotográfico paso a paso (imágenes de componentes iniciales, limpieza y aplicación de pasta térmica) mire el **[📖 Informe Detallado de Intervención](./INFORME_DETALLADO.md)**. 

#### 🛠️ Ficha Técnica del Hardware (Inventario del Sistema)

Datos extraídos de forma nativa a través de herramientas administrativas (msinfo32) y validados mediante inspección visual: 

* **Procesador (CPU):** Intel Core i7-6700
* **Placa Base (Motherboard):** MSI B150 GAMING M3 (MS-7978) (BIOS Ver: American Megatrends Inc. B.70)
* **Memoria RAM:** 16 GB DDR4 a 2133 MHz (Configuración: 2x8GB - Dual Channel)
* **Tarjeta Gráfica (GPU):** NVIDIA GeForce GTX 1060 (6GB GDDR5)
* **Almacenamiento:** SSD Crucial 256 GB (Unidad C:) + HDD WDC 932 GB (Unidad D:)
* **Fuente de Alimentación:** Nox Urano VX 650 (V1)
* **Chasis / Caja:** Nox Hummer MC

#### 📈 Metodología de Pruebas y Herramientas

Para aislar variables y garantizar la fidelidad de los datos, las pruebas de software se realizaron a una temperatura ambiente controlada de ~25°C utilizando el siguiente software de diagnóstico: 

1. **HWiNFO64:** Monitorización en modo *Sensors Only* de picos mínimos (Idle) y máximos (Load) de las temperaturas de los núcleos.
2. **Cinebench:** Prueba sintética de renderizado para estresar la CPU al 100% durante ciclos continuos de 10 minutos.
3. **FurMark:** Test de estrés continuo de 10 minutos para evaluar la estabilidad de fotogramas y la disipación del silicio gráfico.

#### 📊 Resultados Comparativos (Métricas A/B)

#### Rendimiento Térmico y Físico

*Nota: En la fase previa ("A"), el sobrecalentamiento inicial del procesador provocó la activación de protecciones térmicas del sistema, interrumpiendo la salida de video HDMI y obligando a un reinicio forzado para repetir el test de estrés.* 

 | Componente / Métrica | Línea Base "A" (Sucio / Pasta Vieja) | Línea Base "B" (Limpio / Pasta Nueva) | Impacto Neto / Diferencia |
| :--- | :--- | :--- | :--- |
| **CPU Temp (Reposo / Idle)** | 23 °C (24°C amb.) | 22 °C (25°C amb.) | - 3 °C |
| **CPU Temp Máxima (Carga)** | 79 °C (25°C amb.) | 65 °C (25°C amb.) | - 14 °C |
| **CPU Thermal Throttling** | SI - Repetida prueba | No | Mejora |
| **GPU Temp (Reposo / Idle)** | 31,3 °C | 31,3 °C | 0 °C |
| **GPU Temp Máxima (Carga)** | 71,4 °C (25°C amb.) | 76,8 °C (25°C amb.) | + 5,4 °C |

**Nota de ingeniería:* El incremento térmico controlado en la GPU tras la limpieza se debe a la eliminación del estrangulamiento por software; al recuperar la fluidez eléctrica y del flujo de aire, el componente rinde a su máxima capacidad real, consumiendo más energía de forma segura. 

#### Rendimiento Sintético (Benchmarks)
| Prueba Realizada | Puntuación Línea Base "A" | Puntuación Línea Base "B" | Incremento de Rendimiento (%) |
| :--- | :--- | :--- | :--- |
| **Cinebench CPU (Multi-Core)** | 1238 pts | 1234 pts | - 0,32 % |
| **FurMark GPU (FPS Medios)** | 61 FPS | 64 FPS | + 4,68 % |

#### 💡 Conclusiones

El proyecto valida experimentalmente la correlación directa entre el mantenimiento físico preventivo y la eficiencia del software: 

* **Estabilización de Componentes:** El equipo pasó de sufrir micro-congelamientos y apagones de pantalla bajo carga a mantener una estabilidad absoluta bajo estrés prolongado.
* **Eficiencia Operativa:** Al eliminar las barreras de polvo, se evita que los componentes limiten su potencia de forma automática (*thermal throttling*) para autoprotegerse, asegurando un ciclo de vida prolongado para el hardware.

[↩️ Volver al Portafolio Principal](../../README.md)
