
**[Indice​](obsidian://open?vault=Obsidian%20Vault&file=ML%2FDL%2FLandmark%20Estimation%2F05%20-%20Papers%2FPapers%20Index)**
Link code : 
**Autores**: Miroslav Purkrabek and Jiri Matas
**Año**: Agost 1, 2025
**Pages**: 18

---
## **"Human pose estimation methods work well on isolated people but struggle with multiple-bodies-in-proximity scenarios"**

# Proceso

Imagen I
    ↓
Detección → Enmascara instancias → MaskPose → Keypoints → SAM2
    ↑                                                                                                         ↓
    ←←←←←←← Máscaras refinadas ←←←←←←←←←←←←←←←←

---
## Dataset 

- 2D human pose 
	- COCO
	- MPII
	- AIC 
- Multibody problems such as occlusion and sel-occlusion
	- OCHuman 
	- CrowdPose

---
## Parámetros 

---
## Métricas de Evaluación 

- PCKh
	- is used for MPII
- OKS
	- For COCO and related datsets

---
## Figuras 

![[Pasted image 20251019030456.png]]
Figura 1. El método BBox-Máscara-Pose (BMP). Los pasos (A) a (D) se repiten hasta que no se detecten nuevas detecciones en el paso (A). En este caso, el jugador de fondo no se detecta en el paso (A1). BMP se ajusta correctamente a la pose del jugador de primer plano (B1), lo que conlleva la corrección de su segmentación y bbox (C1). Tras enmascarar al jugador de primer plano (D1), se detecta al jugador de fondo (A2), se segmenta correctamente su cuerpo y se estima su pose. Derecha: salida de BMP. Nota: el bucle puede comenzar con un cuadro delimitador (A), una pose (B) o una máscara de segmentación (C).

![[Pasted image 20251019042459.png]]
(a) Una instancia omitida que se detecta en la segunda iteración de BMP. Izquierda:  TMDet + MaskPose, derecha: BMP.

![[Pasted image 20251019042616.png]]
(b) Dos casos en una detección se resuelven refinando las máscaras de segmentación con SAM, según la pose detectada. Izquierda: RTMDet, derecha: BMP. Obsérvese que la  detección de la mujer ha mejorado, pero su pierna derecha sigue estando mal segmentada.

![[Pasted image 20251019042647.png]]
(c) Colapso de las estimaciones de pose para dos instancias con bboxes superpuestos detectados correctamente en un cuerpo. Izquierda: ViTPose-B condicionada por cuadro delimitador, derecha: MaskPose-b condicionada por máscaras.

Figura 2. BMP resuelve errores de detección (arriba y en el centro) y errores de pose (abajo) en OCHuman. Resultados cuantitativos en la Tabla 3.

![[Pasted image 20251019043321.png]]
(a) El número de puntos clave. Demasiados puntos dificultan el rendimiento.
Izquierda: 6 indicaciones para puntos clave; derecha: 13 indicaciones correctas.

![[Pasted image 20251019043329.png]]
(b) Indicación con y sin cuadro delimitador. La indicación con cuadro delimitador impide que SAM corrija las máscaras corporales fuera del cuadro delimitador.
Izquierda: RTMDet, centro: SAM con cuadro delimitador, derecha: SAM sin cuadro delimitador.

Figura 3. SAM: influencia de los parámetros de estímulo.