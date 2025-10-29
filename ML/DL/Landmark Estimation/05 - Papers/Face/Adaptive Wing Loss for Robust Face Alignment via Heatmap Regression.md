
**[Indice​](obsidian://open?vault=Obsidian%20Vault&file=ML%2FDL%2FLandmark%20Estimation%2F05%20-%20Papers%2FPapers%20Index)**
**Link code**: at https://github.com/ZhenglinZhou/STAR
**Autores**: Zhenglin Zhou, Huaxia Li, Hong Liu, Nanyang Wang, Gang Yu, Rongrong Ji
**Año**: Jun 5, 2023
**Pages**: 14

---
## **""**

---
## Proceso

----
## Dataset 

- COFW
	-  1345 training imafges and 507 testing images with 29 landmarks
- 300W
	- 3148 training images and 689 test images with 68 landmarks
- 300VW
	-  To make a cross-dataset validation
- WFLW
	- 7500 training images and 2500 test images with 98 landmarks

---
## Parámetros 

- Data augmentation
	- Crop and resize: 256x256
	- Random rotation: $18^\circ$
	- Random scaling: $\pm10\%$
	- Random crop: $\pm5\%$
	- Random gray: $20\%$
	- Random blur: $30\%$
	- Random occlusion: $40\%$
	- Random horizontal flip: $50\%$
- Model
	- four-stacked hourglass as the backbone
		- module output a $64x64$ feature map
		- recursive step in HG is set to 3
	- Optimizer: Adam
	- Initial rate: $1\times10^{-3}$
		- Reduce the learning rate by 10 at epoch 200, 350 and 450
	- 500 epochs
- GPUs
	- 4
		- 32 GB NVIDIA Tesla V100
	- Batch size: 16

---
## Métricas de Evaluación 
- Normalized Mean Error (NME)
	- inter-ocular 
		- 300W y WFLW datasets
	- inter-pupils
		- COFW dataset
- Faiture Rate (FR)
	- set the threshold by $10\%$
		- WFLW
- Area Under Curve (AUC)
	- set the treshold by $10\%$

---
## Figuras 

![[Pasted image 20251019160257.png]]
Figura 1. El impacto de la ambigüedad semántica. Visualizamos los resultados de cinco modelos entrenados con la misma arquitectura en el mismo entorno experimental. (1) La primera fila muestra los puntos de referencia faciales predichos para el Sr. Tony Stark, marcados como puntos rojos. El punto verde se refiere al valor medio correspondiente. (2) La segunda fila muestra los resultados de la distribución de probabilidad predicha (es decir, el mapa de calor) de uno de los modelos entrenados.

![[Pasted image 20251019160525.png]]
Figura 2. Resumen de nuestro marco. Utilizamos una red de cuatro relojes de arena (HG) apilados. Para mitigar el impacto de la ambigüedad semántica, se aplica la pérdida STAR a cada módulo HG. (Mejor vista en color)

![[Pasted image 20251019163247.png]]
Figura 3. Visualización de los resultados del PCA. Las flechas amarilla y azul indican el primer y segundo componente principal de la distribución discreta predicha, respectivamente. La longitud de la flecha corresponde a los valores propios correspondientes. Utilizamos (λ1 /λ2) para formular la ambigüedad, que se representa mediante el sombreado de la elipse azul. (Mejor visualización en color).

![[Pasted image 20251019173258.png]]
Figura 5. Resultados cualitativos de diferentes funciones de distancia con pérdida de STAR en el conjunto de datos WFLW. Los puntos verdes y rojos representan los puntos predichos y de referencia, respectivamente. Los círculos amarillos indican las fallas evidentes, que se solucionan con la pérdida de STAR. (Se visualiza mejor en color y con zoom).

![[Pasted image 20251019173403.png]]
Figura 6. Distribución de la varianza. Visualizamos el estadístico de varianza de cinco modelos entrenados en el mismo entorno experimental, con y sin pérdida de STAR. Las líneas roja y azul indican el valor medio correspondiente de la función de distancia l2 con y sin pérdida de STAR, respectivamente.