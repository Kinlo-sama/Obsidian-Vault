
# **Pendiente - **

**[Indice​](obsidian://open?vault=Obsidian%20Vault&file=ML%2FDL%2FLandmark%20Estimation%2F05%20-%20Papers%2FPapers%20Index)**
**Link code** : https://github.com/IDEA-Research/X-Pose
Basado en MMPose
## **"Tranfer learning""**

# Proceso

**ViTPose aplica transfer learning fine-tuneando un ViT preentrenado con MAE para estimar poses humanas mediante un decodificador minimalista.**

## Dataset 

MS COCO

## Parámetros 

#### **Configuración Base:**

- **Input resolution**: 256 × 192 pixels
- **Optimizer**: AdamW
- **Learning rate base**: 5e-4 (COCO only) / 1e-3 (multi-dataset)
- **Epochs**: 210 total
- **LR decay**: ×0.1 en epoch 170 y 200
- **Batch Size:**
	- **COCO only**: 512
	- **Multi-dataset**: 1024 (más datos → batch más grande)

## Métricas de Evaluación 

 - **Average Precision (AP) - Métrica Principal**
 - **Average Recall (AR)**
 - **Eficiencia Computacional**
	 - **Params**
	 - **GFLOPs**
	 - **Memory**
	 - **Speed**
 - #### **Métricas de Transferencia**
	- **Transferabilidad**
	- **Data Efficiency**

## Figuras 

![[Pasted image 20251123154148.png]]
**Figura 1:** La comparación de ViTPose y los métodos State-of-the-Art (SOTA) en el conjunto de validación de MS COCO respecto al tamaño del modelo, throughput y precisión. El tamaño de cada burbuja representa el número de parámetros del modelo.

![[Pasted image 20251123154255.png]]
**Figura 2:** (a) El framework de ViTPose. (b) El bloque transformer. (c) El decodificador clásico. (d) El decodificador simple. (e) Los decodificadores para múltiples datasets.

![[Pasted image 20251123154352.png]]
**Figura 3:** Resultados visuales de estimación de pose de ViTPose en algunas imágenes de prueba del dataset MS COCO.

![[Pasted image 20251123154435.png]]
**Figura 4:** Resultados visuales de estimación de pose de ViTPose en algunas imágenes de prueba del conjunto de datos AI Challenger.


![[Pasted image 20251123154456.png]]
**Figura 6:** Resultados visuales de estimación de pose de ViTPose en algunas imágenes de prueba del dataset MPII.

