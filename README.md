# Skyview: Clasificación de Paisajes mediante Imágenes Aéreas
# Proyecto de Visión por Computadora con Deep Learning

## Resumen del Proyecto
Este proyecto desarrolla un modelo de clasificación automática de terrenos basado en imágenes aéreas de alta resolución. Utilizando **Redes Neuronales Convolucionales (CNN)**, el sistema es capaz de distinguir entre 15 categorías distintas de paisajes (como puertos, bosques, glaciares y zonas urbanas), permitiendo el análisis automatizado de datos geoespaciales.

## Dataset
Se utilizó el dataset **Skyview / Aerial Landscapes** obtenido de Kaggle.
* **Tamaño:** +25,000 imágenes organizadas en 15 clases competitivas.
* **Pre-procesamiento:** Normalización de píxeles (0-1) y redimensionamiento dinámico a 256x256.
* **Ingeniería de Datos:** Implementación de *Data Augmentation* (rotación, giros horizontales y ajuste de brillo) para fortalecer la robustez del modelo frente a variaciones de captura.

## Stack Tecnológico
* **Lenguaje:** Python 3.12
* **Framework principal:** TensorFlow / Keras
* **Procesamiento de Datos:** NumPy, Pandas
* **Visualización:** Matplotlib, Seaborn
* **Entorno:** Google Colab con aceleración por GPU (T4)

## Resultados y Optimización Técnica
A diferencia de implementaciones convencionales, este proyecto atravesó una fase crítica de optimización tras detectar un escenario de **sobreajuste (overfitting)** y **fuga de datos (data leakage)**.

### Evolución del Modelo:
1. **Detección del Problema:** El modelo inicial reportaba un Accuracy ficticio de 1.0 (100%) pero clasificaba erróneamente todas las muestras como "Airport".
2. **Acción Correctiva:** Se reconfiguraron los generadores de datos para asegurar un *split* real (80% Train / 20% Validation) y se activó el mezclado aleatorio (*shuffle*).
3. **Mejora de Arquitectura:** Se integraron capas de **Dropout (0.5)** y una capa densa de 512 neuronas antes de la salida Softmax de 15 clases.

### Métricas Finales:
* **Precisión de Validación:** 76%
* **Precisión de Entrenamiento:** 85%
* **Comportamiento:** Las curvas de pérdida muestran una convergencia saludable, demostrando una capacidad de generalización real en entornos de producción.



## Estructura del Repositorio
* `notebooks/`: Cuaderno de Google Colab con el flujo completo de entrenamiento.
* `reports/`: Gráficas de rendimiento y Matriz de Confusión final.
* `src/`: Scripts auxiliares para la carga de datos.

---
**Desarrollado por [Carolina Montanares]** *Estudiante de Ingeniería en Informática - Universidad Bernardo Ohiggins*
