# 🐴 Modelo Predictivo para Supervivencia Equina con PyTorch

![Python](https://img.shields.io/badge/Python-3.9-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

---

### 📖 Resumen del Proyecto

Este proyecto aborda un problema de **clasificación binaria** del mundo real: predecir si un caballo sobrevivirá basándose en un conjunto de datos clínicos. El notebook demuestra un flujo de trabajo completo de ciencia de datos, incluyendo una **limpieza de datos intensiva**, **selección de características** basada en correlación y la construcción de un **modelo de red neuronal (DNN)** utilizando PyTorch.

El principal desafío de este dataset es la gran cantidad de valores faltantes, lo que hace que el preprocesamiento de datos sea una fase crítica y un punto central de este análisis.

---

### 🎯 Objetivo

El objetivo es construir un modelo de machine learning que pueda clasificar con la mayor precisión posible el resultado final de un caso clínico equino (`Vivo` vs. `Muerto/Eutanasiado`), sirviendo como una herramienta potencial de apoyo para la toma de decisiones veterinarias.

---

### 📊 Dataset

Se utilizó el dataset "Horse Survival" disponible en Kaggle. Contiene 299 registros y 28 columnas con una mezcla de variables numéricas y categóricas que describen el estado clínico de cada caballo.

* **Variable Objetivo:** `outcome` (Vivo, Muerto, Eutanasiado).
* **Características:** Pulso, temperatura rectal, resultados de exámenes de laboratorio, etc.

---

### 🛠️ Metodología

El proyecto se estructura en los siguientes pasos clave:

1.  **Limpieza de Datos:**
    * Se transformó la variable objetivo en un formato binario (1 para 'vivo', 0 para los demás).
    * Se eliminaron estratégicamente las columnas y filas con más de un 50% de datos faltantes para mantener la integridad del dataset.
    * Los valores nulos restantes se imputaron utilizando la **moda** de cada columna, una técnica robusta para datos mixtos.

2.  **Selección de Características:**
    * Se analizaron las correlaciones entre todas las variables y la variable objetivo `outcome`.
    * Se seleccionó un subconjunto de características con una correlación absoluta mayor a `0.15` para construir un modelo más enfocado y eficiente.

3.  **Modelado y Entrenamiento:**
    * Se construyó una **Red Neuronal Densa (DNN)** en PyTorch con una capa oculta de 5 neuronas y una función de activación Tanh.
    * Se utilizó la función de pérdida `BCELoss` y el optimizador `Adam` con regularización `weight_decay` para evitar el sobreajuste.
    * El modelo fue entrenado durante 13,000 iteraciones para asegurar la convergencia.

---

### 📈 Resultados

El modelo final logró un rendimiento significativamente superior al de una clasificación aleatoria:

* **Precisión en el conjunto de entrenamiento:** **92.54%**
* **Precisión en el conjunto de prueba:** **75.86%**

La matriz de confusión del conjunto de prueba demuestra la capacidad del modelo para generalizar y hacer predicciones correctas en datos no vistos, validando el proceso de limpieza y modelado.

---

### 🚀 Cómo Ejecutar este Proyecto

1.  Clonar el repositorio:
    ```bash
    git clone [https://github.com/tu_usuario/tu_repositorio.git](https://github.com/tu_usuario/tu_repositorio.git)
    ```
2.  Asegurarse de tener las librerías necesarias (Pandas, PyTorch, Scikit-learn, etc.).
3.  Abrir el notebook `.ipynb` en un entorno como Google Colab o Jupyter Notebook y ejecutar las celdas en orden. El dataset se carga directamente desde su URL pública, por lo que no se requiere descarga manual.
