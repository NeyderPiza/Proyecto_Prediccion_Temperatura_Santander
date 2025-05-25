# PREDICCIÓN DE TEMPERATURA PARA EL DEPARTAMENTO DE SANTANDER

![Banner_proyecto](https://github.com/user-attachments/assets/6def4232-7fb2-49bf-910f-84432e954ad3)


##  Autores
 - Neider Alirio Piza Basto - 2225613,
 - Leider Joanny Esteban Lozano - 2215003 
 - Milton Andres Monsalve Ayala - 2204004


##  Descripción del Proyecto
Este proyecto tiene como objetivo predecir la temperatura para el departamento de Santander, Colombia, utilizando datos meteorológicos históricos. La predicción de temperatura es crucial para diversos sectores como la agricultura, el turismo y la salud pública.

El análisis se enfoca en información hidrometeorológica proveniente de estaciones del IDEAM, midiendo la temperatura del aire a 2 metros en diferentes municipios.

##  Dataset

- **Fuente:** IDEAM - Instituto de Hidrología, Meteorología y Estudios Ambientales de Colombia](https://www.datos.gov.co/browse?q=IDEAM&sortBy=relevance
- **Archivo Utilizado:** `Datos_Hidrometeorol_gicos_Crudos_-_Red_de_Estaciones_IDEAM___Temperatura_20250310 (1).csv`

**Características Principales del Dataset Limpio:**
- **Número de registros:** 37,378
- **Número de columnas:** 10
- **Variable Objetivo:** `ValorObservado` (Temperatura del aire en °C a 2m).
- **Características Relevantes Usadas:** `Latitud`, `Longitud`, `Día`, `Mes`, `Año` (extraídas de `FechaObservacion`).
- **Ubicación:** Departamento de Santander, Colombia, con datos de varios municipios.

**Preprocesamiento Realizado:**
*   Conversión de la columna `FechaObservacion` a formato datetime.
*   Extracción de características temporales (`Día`, `Mes`, `Año`) de `FechaObservacion`.
*   Eliminación de valores nulos en columnas críticas (`FechaObservacion`, `ValorObservado`).
*   Filtrado para incluir solo datos de "TEMPERATURA DEL AIRE A 2 m".
*   Eliminación de columnas consideradas irrelevantes para el modelado (`CodigoSensor`, `UnidadMedida` después de la verificación).
*   Escalado de características (`StandardScaler`) para preparar los datos para las redes neuronales.

##  Modelos y Técnicas Utilizadas
Se implementaron y evaluaron diversos modelos y técnicas, incluyendo:

1.  **Modelos de Regresión para la Predicción de Temperatura:**
    *   Decision Tree Regressor (Árbol de Decisión para Regresión)
    *   Random Forest Regressor (Bosque Aleatorio para Regresión)
    *   Support Vector Regressor (SVR - Máquina de Vectores de Soporte para Regresión)
    *   Redes Neuronales (con tres configuraciones diferentes: 3, 6 y 10 capas ocultas, utilizando optimizador Adam y función de pérdida MSE).

2.  **Análisis Exploratorio de Datos (EDA) y Evaluación de Modelos:**
    *   Visualizaciones como histogramas, gráficos de series temporales, gráficos de temperatura promedio por estación y municipio.
    *   Generación de curvas de aprendizaje y aplicación de validación cruzada (k-folds) para evaluar la robustez de los modelos y optimizar hiperparámetros para SVR, y configuraciones de capas/neuronas para Redes Neuronales.
    *   Métricas de evaluación como RMSE (Root Mean Squared Error), R² Score y MAE (Mean Absolute Error).

3.  **Técnicas Adicionales de Análisis de Datos:**
    *   **Reducción de Dimensionalidad con PCA (Principal Component Analysis):** Aplicada a los datos escalados para reducir la dimensionalidad a 2 componentes principales, facilitando la visualización y el clustering.
    *   **Algoritmos de Clustering:**
        *   K-Means: Aplicado a los datos transformados por PCA para identificar agrupaciones (clusters).
        *   DBSCAN: Aplicado a los datos transformados por PCA para identificar clusters basados en densidad.


Se realizaron análisis exploratorios de datos (EDA) con visualizaciones como histogramas y gráficos de series temporales, así como gráficos de temperatura promedio por estación y municipio. También se generaron curvas de aprendizaje y se aplicó validación cruzada (k-folds) para evaluar la robustez de los modelos y optimizar hiperparámetros como `max_depth` (para Decision Tree) y `n_estimators` (para Random Forest), y el tipo de `kernel` (para SVR).


##  Enlaces Relevantes
- **Código Fuente (Notebook):** https://colab.research.google.com/drive/1r91XzIEdN9o14r5s3xDfvmdt1EJznSUj?usp=sharing
- **Video de Presentación:** [Presentación del Proyecto en Video](URL_DEL_VIDEO_AQUI)
- **Diapositivas:** [Diapositivas de la Presentación](URL_DE_LAS_DIAPOSITIVAS_AQUI)
- **Repositorio Proyecto:** https://github.com/NeyderPiza/Proyecto_Prediccion_Temperatura_Santander
<!--
**Dependencias Principales:**
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
  -->
