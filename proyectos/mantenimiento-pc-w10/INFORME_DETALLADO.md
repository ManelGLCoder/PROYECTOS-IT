# Informe Detallado: Optimización Térmica y Restauración de Rendimiento en Entorno Windows 10

## 📝 1. Introducción y Objetivos del Proyecto

Este proyecto documenta el proceso de auditoría de rendimiento, mantenimiento de hardware y análisis comparativo de una torre de ordenador con sistema operativo Windows 10. 

El objetivo principal es demostrar habilidades técnicas en: 

* **Diagnóstico de sistemas:** Captura de métricas base estandarizadas.
* **Mantenimiento preventivo y correctivo:** Desmontaje seguro, limpieza de componentes críticos y sustitución de la interfaz térmica (pasta térmica).
* **Análisis de datos de rendimiento:** Metodología de pruebas A/B para verificar el impacto real del mantenimiento sobre las frecuencias de reloj y las temperaturas operativas.

## 🛠️ 2. Ficha Técnica del Hardware (Inventario del Sistema) y Estado Inicial

Los siguientes datos fueron extraídos de forma nativa a través de msinfo32 y el *Administrador de tareas* de Windows 10, complementados con la inspección visual del chasis durante la apertura: 

* **Procesador (CPU):** Intel Core i7-6700
* **Placa Base (Motherboard):** MSI B150 GAMING M3(MS-7978) (Versión de BIOS: American Megatrends Inc. B.70 24/07/2016)
* **Memoria RAM:** 16 GB DDR4 a 2133 MHz a (Configuración: 2x8GB - Dual Channel)
* **Tarjeta Gráfica (GPU Dedicated):** NVIDIA GeForce GTX 1060  (6GB GDDR5 )
* **Almacenamiento (Unidad C:):** SSD Crucial_CT275MX300SSD1  de 256 GB
* **Almacenamiento (Unidad D:):** HDD WDC WD10EZEX-08WN4A0  de 932 GB
* **Fuente de Alimentación:** Nox Urano VX 650 (primera versión)
* **Chasis / Caja:** Nox Hummer MC

### 🔍 2.1. Vista Exterior Inicial De La Torre
<div>
	<img src="./recursos/Torre_Sucia_Vista_2.jpg" width="360" alt="Torre_Sucia_Vista_2">
	<img src="./recursos/Torre_Sucia_Vista_4.jpg" width="260" alt="Torre_Sucia_Vista_4">
	<img src="./recursos/Torre_Sucia_Vista_5.jpg" width="230" alt="Torre_Sucia_Vista_5">
	<img src="./recursos/Torre_Sucia_Vista_1.jpg" width="340" alt="Torre_Sucia_Vista_1">
	<img src="./recursos/Torre_Sucia_Vista_3.jpg" width="340" alt="Torre_Sucia_Vista_3">
	<img src="./recursos/Torre_Sucia_Vista_6.jpg" width="380" alt="Torre_Sucia_Vista_6">
	
</div>

### 🔍 2.2. Vista Interior Inicial De La Torre
<div>
	<img src="./recursos/Torre_Sucia_Interior_5.jpg" width="340" alt="Torre_Sucia_Interior_5">
	<img src="./recursos/Torre_Sucia_Interior_3.jpg" width="340" alt="Torre_Sucia_Interior_3">
	<img src="./recursos/Torre_Sucia_Interior_2.jpg" width="340" alt="Torre_Sucia_Interior_2">
	<img src="./recursos/Torre_Sucia_Interior_4.jpg" width="340" alt="Torre_Sucia_Interior_4">
	<img src="./recursos/Torre_Sucia_Interior_1.jpg" width="340" alt="Torre_Sucia_Interior_1">
</div> 
 

## 📈 3. Metodología de Pruebas y Herramientas Utilizadas

Para garantizar la fiabilidad del estudio, se aislaron los procesos en segundo plano y se utilizaron tres herramientas de software de diagnóstico: 

1. **HWiNFO64:** Utilizado en modo *Sensors Only* para monitorizar los picos mínimos en reposo y máximos bajo carga de temperatura de los núcleos (Core Temperature).
2. **Cinebench (2026):** Prueba sintética de renderizado para estresar la CPU al 100% durante un ciclo continuo de 10 minutos.
3. **FurMark:** Test de estrés para la GPU (resolución nativa del monitor) durante 10 minutos para evaluar la estabilidad de los fotogramas y la disipación del silicio gráfico.
4. **Herramientas de Hardware utilizadas:** 
	  * Kit Reparaciones STREBITO
	  * Pulsera Anti-estática
	  * Pasta Técnica ARTIC MX-4
	  * Soplador Eléctrico
	  * Casquillos Magnéticos
	  * Alcohol Isopropílico 99,9% EQM - ECO_301
	  * Trapo y bastoncillos de algodón
	  ![Herramientas.jpg](./recursos/Herramientas.jpg)

 

## 🔧 4. Diario de Intervención Técnica (Hardware)

El proceso físico de restauración se llevó a cabo siguiendo estrictos protocolos de seguridad electrostática e informática: 

1. **Desergetización del Sistema:** Apagado total, desconexión de la red eléctrica y descarga de condensadores residuales manteniendo el botón de encendido presionado durante 10 segundos.
2. **Desmontaje Seguro:** Extracción secuencial de las tapas laterales, desconexión y retirada de la tarjeta gráfica (liberando el anclaje físico PCIe) y remoción del disipador de la CPU aplicando torsión lateral leve para romper el "efecto ventosa" de la pasta reseca.
	<div>
		<img src="./recursos/Desmontaje_1.jpg" width="340" alt="Desmontaje_1">
		<img src="./recursos/Desmontaje_3.jpg" width="340" alt="Desmontaje_3">
		<img src="./recursos/Desmontaje_2.jpg" width="380" alt="Desmontaje_2">
	</div> 
3. **Higienización:** Limpieza profunda de los bloques de aletas de aluminio y ventiladores mediante aire comprimido (bloqueando las aspas manualmente para evitar corrientes inversas inducidas), para el polvo más denso uso de bastoncillos y/o trapo con alcohol isopropílico al 99%.
	* 💨 **Componentes Sucios**:
		<div>
			<img src="./recursos/Disipador_Sucio.jpg" width="320" alt="Disipador_Sucio">
			<img src="./recursos/GPU_Sucia.jpg" width="360" alt="GPU_Sucia">
			<img src="./recursos/Ventilador_Trasero_Sucio_1.jpg" width="350" alt="Ventilador_Trasero_Sucio_1">
			<img src="./recursos/Ventilador_Trasero_Sucio_2.jpg" width="320" alt="Ventilador_Trasero_Sucio_2">
			<img src="./recursos/Placa_Base_Sucia.jpg" width="380" alt="Placa_Base_Sucia">
		</div> 
	* ✨ **Componentes Limpios**:
		<div>
			<img src="./recursos/Limpieza_1.jpg" width="360" alt="Limpieza_1">
			<img src="./recursos/Limpieza_6.jpg" width="320" alt="Limpieza_6">
			<img src="./recursos/Limpieza_2.jpg" width="325" alt="Limpieza_2">
			<img src="./recursos/Limpieza_3.jpg" width="355" alt="Limpieza_3">
			<img src="./recursos/Limpieza_4.jpg" width="330" alt="Limpieza_4">
			<img src="./recursos/Limpieza_5.jpg" width="350" alt="Limpieza_5">
			<img src="./recursos/Limpieza_7.jpg" width="340" alt="Limpieza_7">
		</div>
		
4. **Sustitución de Interfaz Térmica:** Limpieza absoluta del silicio de la CPU y la base del disipador con alcohol isopropílico al 99%. Aplicación de una nueva capa de compuesto térmico **Arctic MX-4** mediante el método de gota central.
    ![Pasta_Aplicada.jpg](./recursos/Pasta_Aplicada.jpg)
5. **Montaje y Cable Management:** Reensamblado de componentes aplicando presión en cruz simétrica en los tornillos del disipador para una distribución uniforme del compuesto.
	<div>
		<img src="./recursos/Torre_Limpia_1.jpg" width="380" alt="Torre_Limpia_1">
		<img src="./recursos/Torre_Limpia_2.jpg" width="300" alt="Torre_Limpia_2">
		<img src="./recursos/Torre_Limpia_3.jpg" width="380" alt="Torre_Limpia_3">
	</div> 

## 📊 5. Resultados Comparativos (Métricas A/B)

A continuación se detallan los datos brutos recolectados antes del mantenimiento (**Línea Base A**) y después del mantenimiento (**Línea Base B**): 

### Tabla 1: Rendimiento Térmico y Físico

*Debido a que la primera prueba de estrés de la CPU mientras estaba sucio se produjo sobrecalentamiento apagando la salida HDMI, teniendo que apagar el ordenador y encenderlo de nuevo para repetir la prueba, lo que afecta a los resultados al ya estar a una temperatura superior a la normal.* 


| Componente / Métrica | Línea Base "A" (Sucio / Pasta Vieja) | Línea Base "B" (Limpio / Pasta Nueva) | Impacto Neto / Diferencia |
| :--- | :--- | :--- | :--- |
| **CPU Temp (Reposo / Idle)** | 23 °C (24°C amb.) | 22 °C (25°C amb.) | - 3 °C |
| **CPU Temp Máxima (Carga)** | 79 °C (25°C amb.) | 65 °C (25°C amb.) | - 14 °C |
| **CPU Thermal Throttling** | SI - Repetida prueba | No | Mejora |
| **GPU Temp (Reposo / Idle)** | 31,3 °C | 31,3 °C | 0 °C |
| **GPU Temp Máxima (Carga)** | 71,4 °C (25°C amb.) | 76,8 °C (25°C amb.) | + 5,4 °C |

### Tabla 2: Rendimiento Sintético (Benchmarks)

| Prueba Realizada | Puntuación Línea Base "A" | Puntuación Línea Base "B" | Incremento de Rendimiento (%) |
| :--- | :--- | :--- | :--- |
| **Cinebench CPU (Multi-Core)** | 1238 pts | 1234 pts | - 0,32 % |
| **FurMark GPU (FPS Medios)** | 61 FPS | 64 FPS | + 4,68 % |

### Capturas Pruebas Realizadas

* **IDLE (Sucio)**
    ![IDLE_BEFORE.PNG](./recursos/IDLE_BEFORE.PNG)
* **IDLE (Limpio)**
    ![IDLE_AFTER.PNG](./recursos/IDLE_AFTER.PNG)
* **Estrés CPU con Cinebench (Sucio)**
    ![Estress_CPU_BEFORE.PNG](./recursos/Estress_CPU_BEFORE.PNG)
* **Estrés CPU con Cinebench (Limpio)**
    ![Estress_CPU_AFTER.PNG](./recursos/Estress_CPU_AFTER.PNG)
* **Estrés GPU con FurMark (Sucio)**
    ![Estress_GPU_BEFORE.PNG](./recursos/Estress_GPU_BEFORE.PNG)
* **Estrés GPU con FurMark (Limpio)**
    ![Estress_GPU_AFTER.PNG](./recursos/Estress_GPU_AFTER.PNG)

## 💡 6. Conclusiones del Proyecto

El mantenimiento preventivo físico arrojó conclusiones críticas sobre el rendimiento del sistema: 

* **Eficiencia Térmica:** La sustitución de la pasta térmica y la eliminación de obstrucciones en el flujo de aire redujeron la temperatura operativa máxima de la CPU en **14°C** y de la GPU se incremento en **5,4°C**.
* **Recuperación de Rendimiento:** De tener un equipo inestable que sufría micro-congelamientos, caídas drásticas de FPS en juegos a los pocos minutos de empezar, y apagones de pantalla provocados por el estrangulamiento térmico, a una **torre fresca**, **más rápida en procesador**, **con más potencia gráfica en la GPU** y capaz de soportar horas de trabajo pesado sin inmutarse.
* El sistema al estar libre de polvo, **consume más energía y rinde más**. Cuando la torre estaba sucia, los componentes se autoprotegían limitando su potencia para no quemarse.

Este caso práctico demuestra la correlación directa entre la salud física del hardware y la eficiencia del software, validando el mantenimiento técnico periódico como una alternativa coste-efectiva frente a la actualización prematura de componentes. 

[↩️ Volver al Caso de Estudio](./README.md) | [🏠 Volver al Portafolio Principal](../../README.md)
