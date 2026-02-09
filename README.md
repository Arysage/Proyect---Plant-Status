# Diagnóstico Inteligente de Salud Vegetal

Este proyecto implementa un sistema de visión artificial y **Deep Learning** para identificar especies de plantas y diagnosticar enfermedades mediante el análisis de imágenes de hojas. El objetivo es automatizar el diagnóstico agrícola para mejorar la gestión de cultivos en comunidades con recursos limitados.

> **Nota:** El proyecto puede presentar ligeros cambios en su estructura final debido a las optimizaciones realizadas durante el entrenamiento y las pruebas en tiempo real para el evento Ascendion 2025.

## Participantes
* **Antonio Rangel Hugo Manuel**
* **López Rosales Ivan Tonathiu**

---

## Descripción del Proyecto
PlantStatus utiliza redes neuronales convolucionales para transformar una cámara estándar en una herramienta de diagnóstico agrícola. El sistema aborda tres retos técnicos:
1.  **Clasificación Multiclase:** Identificación de especies y patologías específicas.
2.  **Detección en Tiempo Real:** Procesamiento de video en vivo con segmentación de hojas.
3.  **Resiliencia de Datos:** Manejo de un dataset masivo (+160k imágenes) con desbalanceo de clases.

### Dataset
El análisis se basa en el [PlantVillage Dataset (Kaggle)](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset/data), que incluye:
* Más de 160,000 imágenes de hojas.
* Diversas especies (Manzana, Uva, Durazno, etc.).
* Estados: Saludable y múltiples tipos de enfermedades (hongos, bacterias, etc.).

---

## Tecnologías y Librerías
* **Deep Learning:** `PyTorch`, `torchvision` (ResNet18)
* **Visión Artificial:** `OpenCV`, `PIL`
* **Manejo de Datos:** `NumPy`, `CuPy`, `Pandas`
* **Hardware:** Aceleración por GPU (NVIDIA RTX 3050 con CUDA 12.9)

---

## Metodología y Análisis

### 1. Preprocesamiento y Augmentation
* **Estandarización:** Redimensionamiento de imágenes a 224x224 píxeles para compatibilidad con ResNet.
* **Data Augmentation:** Aplicación de rotaciones, flips y ajustes de brillo para mejorar la generalización del modelo.
* **Balanceo Estratificado:** Uso de `WeightedRandomSampler` para compensar las clases minoritarias en el dataset.

### 2. Entrenamiento del Modelo (ResNet-18)
Implementamos una arquitectura de aprendizaje por transferencia (Transfer Learning):
* **Optimización:** AdamW con técnicas de `Early Stopping` para evitar el sobreajuste.
* **Resiliencia:** División de datos en 70% entrenamiento, 15% validación y 15% prueba.

**Resultados de Evaluación (Prueba):**
* **Accuracy:** > 90% en el conjunto de prueba.
* **Confianza:** Alta precisión en la detección de enfermedades en condiciones controladas.



### 3. Detección en Tiempo Real
El sistema integra la cámara mediante un pipeline de visión artificial:
* **Segmentación:** Uso de umbral adaptativo y detección de contornos para aislar la hoja.
* **Estabilización:** Filtro de color verde para minimizar el ruido del entorno y mejorar la captura.

### 4. Resiliencia Adaptativa (Solución de Problemas)
* **Hardware:** Migración de Google Colab a GPU local para eliminar cuellos de botella.
* **Procesamiento:** Optimización de *batch sizes* para evitar saturación de memoria en el redimensionamiento.
* **Entorno:** Ajuste de cajas delimitadoras (bounding boxes) para mejorar la lectura bajo luz variable.

---

## Conclusiones
PlantStatus demuestra ser una solución técnica y económicamente viable. La integración de ResNet18 permite un diagnóstico veloz que puede escalar a tecnologías de agricultura de precisión como drones o monitoreo autónomo.

---
🔗 **Recursos:** [Modelos Entrenados (.pth)](hhttps://drive.google.com/drive/folders/184BphjVmEfdL0npyJ3MqRbB9nwEDROdg?usp=sharing) | [Dataset](https://drive.google.com/drive/folders/1D72K9PJ6xgcV_2WoZheaJk1QSfJAc24B?usp=sharing)