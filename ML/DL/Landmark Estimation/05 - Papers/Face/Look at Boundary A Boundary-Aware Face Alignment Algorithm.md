**[Indice​](obsidian://open?vault=Obsidian%20Vault&file=ML%2FDL%2FLandmark%20Estimation%2F05%20-%20Papers%2FPapers%20Index)**
**Link code**: https://wywu.github.io/projects/LAB/LAB.html
**Autores**: Wayne Wu, Chen Qian, Shuo Yang, Quan Wang, Yici Cai, Qiang Zhou
**Año**: 2018
**Pages**: 10

---
## **""**

---
## Proceso

----
## Dataset 

| **300W** | 3,748 total  | Train: 3,148  <br>Test: 689 (common + challenging) |
| -------- | ------------ | -------------------------------------------------- |
| **COFW** | 1,852 total  | Train: 1,345  <br>Test: 507                        |
| **AFLW** | 24,386 total | AFLW-Full: 20k/4.3k  <br>AFLW-Frontal: 1,314       |
| **WFLW** | 10,000 total | Train: 7,500  <br>Test: 2,500                      |

---
## Parámetros 

- **Tamaño de entrada**: 256 × 256 pixels
- **Crop**: Según bounding boxes proporcionadas
- **Sin transformaciones espaciales** en test
- **Stacked Hourglass**: 4 módulos (2 para ablation study)
- **Framework**: Caffe
- **Hardware**: 4 Titan X GPUs

---
## Métricas de Evaluación

1. **Normalised Landmarks Mean Error** (%) - Error promedio normalizado
2. **CED Curve** - Curva de Distribución Acumulativa de Errores
3. **AUC** - Área bajo la curva CED
4. **Failure Rate** - Tasa de fallos (error > 0.1)


---
## Figuras 

![[Pasted image 20251123144524.png]]
**Figura 1:** La primera columna muestra imágenes de rostros de diferentes conjuntos de datos con distinto número de puntos de referencia. La segunda columna ilustra los límites faciales de definición universal estimados por nuestro método. Con la ayuda de la información de los límites, nuestro enfoque logra resultados de localización de alta precisión en múltiples conjuntos de datos y protocolos de anotación, como se muestra en la tercera columna.

![[Pasted image 20251123144602.png]]
**Figura 2:** Descripción general de nuestro framework de Alineamiento Facial Consciente de Límites. (a) **Estimador de mapas de calor de límites**, basado en la red Hourglass, se utiliza para estimar los mapas de calor de los límites. Se introducen capas de paso de mensajes para manejar la oclusión. (b) **Regresor de puntos de referencia consciente de límites** se utiliza para generar la predicción final de los puntos de referencia. Se introduce un esquema de fusión de mapas de calor de límites para incorporar la información de los límites en el aprendizaje de características del regresor. (c) **Discriminador de efectividad de límites**, que distingue los mapas de calor de límites "reales" de los "falsos", se utiliza para mejorar aún más la calidad de los mapas de calor de límites estimados.

![[Pasted image 20251123144642.png]]
**Figura 3:** Una ilustración del proceso de generación del mapa de calor de ground truth. Cada fila representa el proceso de un límite facial específico, es decir: contorno exterior facial, ceja izquierda, ceja derecha, puente nasal, límite nasal, párpado superior/inferior izquierdo/derecho y lado superior/inferior del labio superior/inferior.

![[Pasted image 20251123144745.png]]
**Figura 4:** Una ilustración del esquema de fusión de mapas de características. Las señales de límites y los mapas de características de entrada se fusionan para obtener una característica refinada con el uso de un módulo hourglass.

![[Pasted image 20251123144831.png]]
**Figura 5:** Una ilustración de la efectividad del paso de mensajes y el aprendizaje adversarial. Con la adición del paso de mensajes y el aprendizaje adversarial, la calidad del límite estimado mejora considerablemente, volviéndose cada vez más plausible y enfocado.
