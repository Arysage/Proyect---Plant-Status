# Proyect---Plant-Status

Este proyecto tiene como objetivo detectar el estado de salud de las plantas a partir de imágenes de sus hojas, permitiendo determinar si una planta se encuentra sana o presenta alguna enfermedad.

----------------------------------------------------------------------------------------

Se utilizó el dataset disponible en Kaggle: PlantVillage Dataset, que contiene imágenes de diversas especies de plantas en diferentes estados de salud, incluyendo tanto muestras patológicas como saludables. Algunas clases del dataset solo incluyen imágenes de plantas sanas; sin embargo, se decidieron conservar para mantener la diversidad de especies.

El dataset fue reorganizado para facilitar el procesamiento y la clasificación:
Se agruparon las imágenes por tipo de planta en carpetas con el nombre de cada especie.
Dentro de cada carpeta, las imágenes se clasificaron según su estado de salud.

----------------------------------------------------------------------------------------

Estructura de Datos
plantvillage-dataset_resized: Dataset redimensionado para facilitar el procesamiento.
plantvillage-dataset_augmented: Dataset aumentado con transformaciones de imágenes para mejorar el entrenamiento del modelo.
Para generar estos datasets es necesario volver a ejecutar las celdas correspondientes en el notebook: la celda de redimensionamiento (plantvillage-dataset_resized) y la celda de aumento de datos (plantvillage-dataset_augmented).

----------------------------------------------------------------------------------------

Funcionamiento
El proyecto incluye scripts para:
División del dataset aumentado en entrenamiento, validación y prueba, con balanceo estratificado por clases y posibilidad de muestreo de fracciones del dataset.
Entrenamiento del modelo: Se entrenó un modelo ResNet-18 con pesos preentrenados en ImageNet, aplicando técnicas de data augmentation y ponderación por clases.
Evaluación del modelo: Se calcula la precisión del modelo sobre el conjunto de prueba.
Detección en tiempo real: Sistema de captura de hojas mediante cámara, segmentación de hojas por contornos y clasificación en tiempo real, mostrando la probabilidad de la predicción y permitiendo guardar capturas de interés.

----------------------------------------------------------------------------------------

Evento

Este proyecto fue desarrollado principalmente para la Feria Estudiantil de Ciencias e Ingenierías - Ascendion Science Fair 2025, con el objetivo de promover la práctica científica y el desarrollo de proyectos ingenieriles en estudiantes del Tecnológico de Monterrey. La feria busca reunir proyectos innovadores y de alto impacto, facilitando la divulgación del conocimiento científico entre alumnos, profesores y empresarios.

----------------------------------------------------------------------------------------

Cómo Ejecutar
* Preparar los datasets (plantvillage-dataset_resized y plantvillage-dataset_augmented).
* Ejecutar el script de división de datasets para generar los CSV de entrenamiento, validación y prueba.
* Entrenar el modelo o cargar pesos preentrenados.
* Ejecutar el script de detección en tiempo real para evaluar hojas capturadas por la cámara.

----------------------------------------------------------------------------------------

Dataset
https://drive.google.com/drive/folders/1D72K9PJ6xgcV_2WoZheaJk1QSfJAc24B?usp=drive_link

----------------------------------------------------------------------------------------
Modelos Entrenados
Solamente aparecen los entrenados con augmente dataset, ya que son los finales, con las diferentes epocas y el modelo final.

🔗 Modelos entrenados: https://drive.google.com/drive/folders/184BphjVmEfdL0npyJ3MqRbB9nwEDROdg?usp=sharing
