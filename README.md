# Skyview: Clasificación de Paisajes mediante Imágenes Aéreas
# Proyecto de Visión por Computadora con Deep Learning

## Resumen del Proyecto
Este proyecto desarrolla un modelo de clasificación automática de terrenos basado en imágenes aéreas. Utilizando redes neuronales convolucionales (CNN), el sistema es capaz de distinguir entre diferentes categorías de paisajes (como bosques, desiertos o zonas urbanas), permitiendo el análisis de datos geoespaciales a gran escala.

## Dataset
Se utilizó el dataset de **Skyview / Aerial Landscapes**. 
* **Origen:** Imágenes capturadas desde perspectivas aéreas (cenitales).
* **Procesamiento:** Normalización de píxeles, redimensionamiento de imágenes para la entrada de la red y técnicas de *Data Augmentation* para prevenir el sobreajuste.

## Stack Tecnológico
* **Lenguaje:** Python 3.x.
* **Librerías:** TensorFlow, Keras, NumPy, Matplotlib.
* **Entorno:** Google Colab con soporte de GPU para aceleración del entrenamiento.

## Resultados y Métricas
* **Precisión reportada:** 100% (Entrenamiento y Validación).
* **Análisis técnico:** Se identificó un escenario de sobreajuste (overfitting) debido a la alta similitud entre los conjuntos de datos. 
* **Desafío actual:** El modelo presenta dificultades en la generalización con imágenes del mundo real (fuera del dataset de Skyland).
* **Próximos pasos:** Implementar técnicas de *Dropout* más agresivas, aumentar el dataset con imágenes externas y aplicar *Cross-Validation* para asegurar la robustez del modelo.
  
* ## Optimización y Resolución de Problemas
Durante el desarrollo, se identificó y corrigió un problema de **Data Leakage** y **Sesgo de Clase**.
* **Problema**: El modelo presentaba un Accuracy ficticio de 100% y clasificaba todo como "Airport".
* **Solución**: Se reestructuraron los generadores de datos con un split real de 80/20, se aplicó *Data Augmentation* y se ajustó la capa de salida a 15 neuronas con activación Softmax.
* **Resultado Final**: Precisión estable de ~75% en validación, demostrando una capacidad real de clasificación de paisajes aéreos.

* ## Análisis de tus Nuevos resultados  
* **Curvas Saludables** : La precisión de entrenamiento (línea azul) sube gradualmente hasta superar el 80%, mientras que la de validación (línea naranja) la sigue de cerca del 75%. Esto indica que el modelo ahora sí tiene capacidad de generalizar a paisajes que no ha visto antes.

* **Pérdida (Loss) en Descenso** : Ambas curvas de pérdida están bajando de forma constante, lo que confirma que el optimizador está encontrando los pesos correctos para identificar los paisajes de Skyview.

* **Sin Overfitting Extremo** : A diferencia de la línea recta en 1.0 que tenía antes, estas curvas muestran un comportamiento real de una red neuronal profunda.

## Contenido del Repositorio
* `notebooks/`: Archivo .ipynb con el flujo de entrenamiento y validación.
* `reports/`: Informe final del sistema inteligente y presentación de resultados.
