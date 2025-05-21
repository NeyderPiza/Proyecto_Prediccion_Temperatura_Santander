# 🌦️ PREDICCIÓN DE TEMPERATURA PARA EL DEPARTAMENTO DE SANTANDER

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
- Conversión de la columna `FechaObservacion` a formato datetime.
- Extracción de características temporales (Día, Mes, Año).
- Eliminación de valores nulos en columnas críticas (`FechaObservacion`, `ValorObservado`).
- Filtrado para incluir solo datos de "TEMPERATURA DEL AIRE A 2 m".
- Eliminación de columnas consideradas irrelevantes para el modelado (`CodigoSensor`, `UnidadMedida` después de la verificación).

##  Modelos y Técnicas Utilizadas
Se implementaron y evaluaron los siguientes modelos de regresión para la predicción de temperatura:

1.  **Decision Tree Regressor (Árbol de Decisión para Regresión)**
2.  **Random Forest Regressor (Bosque Aleatorio para Regresión)**
3.  **Support Vector Regressor (SVR - Máquina de Vectores de Soporte para Regresión)**

Se realizaron análisis exploratorios de datos (EDA) con visualizaciones como histogramas y gráficos de series temporales, así como gráficos de temperatura promedio por estación y municipio. También se generaron curvas de aprendizaje y se aplicó validación cruzada (k-folds) para evaluar la robustez de los modelos y optimizar hiperparámetros como `max_depth` (para Decision Tree) y `n_estimators` (para Random Forest), y el tipo de `kernel` (para SVR).

##  Resultados y Evaluación
Los modelos fueron evaluados utilizando las siguientes métricas:
- Error Cuadrático Medio (RMSE)
- Coeficiente de Determinación (R²)
- Error Absoluto Medio (MAE)

**Resultados Destacados (con `test_size=0.2`, `random_state=42` sobre el dataset completo):**
- **Decision Tree:**
    - RMSE: ~3.55 °C
    - R²: ~0.69
    - MAE: ~2.99 °C
- **Random Forest:**
    - RMSE: ~3.55 °C
    - R²: ~0.69
    - MAE: ~2.99 °C
- **Support Vector Machine (SVR):**
    - RMSE: ~6.42 °C
    - R²: ~-0.01 (indica un rendimiento pobre)
    - MAE: ~5.01 °C

*Los modelos de Árbol de Decisión y Bosque Aleatorio mostraron un rendimiento similar y significativamente mejor que SVR para este conjunto de datos y características.*

**Validación Cruzada (ejemplo con Decision Tree y k=5):**
- MAE promedio: ~3.04 °C
- Desviación estándar del MAE: ~0.06 °C

##  Enlaces Relevantes
- **Código Fuente:** (https://colab.research.google.com/drive/1r91XzIEdN9o14r5s3xDfvmdt1EJznSUj?usp=sharing)
- **Video de Presentación:** [Presentación del Proyecto en Video](URL_DEL_VIDEO_AQUI)
- **Diapositivas:** [Diapositivas de la Presentación](URL_DE_LAS_DIAPOSITIVAS_AQUI)
- **Repositorio Proyecto:** Enlace a GitHub

**Dependencias Principales:**
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
  
