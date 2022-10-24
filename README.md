# Segementación de Instancia en células neuronales

Los trastornos neurológicos (enfermedades degenerativas como el Alzheimer y los tumores cerebrales) son una de las principales causas de muerte y discapacidad y es difícil cuantificar el éxito de los tratamientos.
Con la ayuda de la visión por ordenador podríamos conseguirlo. ¿Cómo? Segmentando células neuronales que observamos gracias a la microscopía de contraste de fase.
La microscopía de contraste de fase es una técnica de microscopía de campo claro desarrollada por Frits Zernike (ganó el Premio Nobel de física en 1953) que hace que las estructuras transparentes sean más visibles y funcione sin problemas con diferentes sustratos, especialmente en plásticos que son altamente birrefringentes.
Las imágenes de microscopía de contraste de fase son difíciles de segmentar mediante métodos convencionales de visión artificial.
Esta tarea es todavía un desafío dada la poca precisión que se puede obtener hoy. Por ejemplo, la precisión conseguida con modelos de segmentación de instancias para la célula *SH-SY5Y* es más baja que otros tipos de células cancerosas (esto puede deberse a que las células neuronales tienen una morfología cóncava, irregular y única).

**El objetivo es conseguir detectar y delinear células neuronales** (normalmente usadas en trastornos neurológicos) en imágenes de microscopio de contraste de fase con el algoritmo de Aprendizaje Profundo *Mask R-CNN*.
Si se consiguieran buenos resultados resultaría mucho más fácil medir los efectos de las enfermedades y las condiciones de tratamientos en las células neuronales, además de que nuevos fármacos se podrían crear para tratar a millones de personas con estos trastornos.

*Evaluación*

Se utilizará la precisión media en diferentes umbrales de la función de intersección sobre la unión (*IoU*). Esta métrica, se considera que para este proyecto sería exitosa si está por encima de 0.5.

*Descripción de los datos*

Las imágenes son 2D (en formato png), hay otros datos como el identificador único por objeto, las anotaciones de la máscara (en píxeles codificados para cada célula), la dimensión de la imagen (ancho y alto), el tipo de célula, el momento de creación de la placa, la fecha de creación de la muestra, el identificador de la muestra y el tiempo pasado desde que se tomó la primera imagen.

*Retos del problema*
1. Predecir con una precisión mayor al 0.5 de media en nuestras células.
2. La forma de la célula *SH-SY5Y* es muy distintiva. Puede ser complicado predecir
exitosamente las formas geométricas.
3. Las imágenes están degradadas, tienen cierto deterioro de definición y/o luminosidad.
4. La segmentación de instancia en pequeños objetos es un problema real en la industria.
