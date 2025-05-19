# 🌦️ PREDICCIÓN DE TEMPERATURA PARA EL DEPARTAMENTO DE SANTANDER

<!-- Opcional: Banner del proyecto -->
<!-- ![Banner del Proyecto](URL_DEL_BANNER_AQUI) -->

## 🧑‍💻 Autores
<!-- - Nombre Completo - ID/Usuario -->
<!-- - Nombre Completo - ID/Usuario -->
<!-- - Nombre Completo - ID/Usuario -->
<!-- Por favor, añade los nombres de los autores aquí -->

## 🎯 Descripción del Proyecto
Este proyecto tiene como objetivo predecir la temperatura para el departamento de Santander, Colombia, utilizando datos meteorológicos históricos. La predicción de temperatura es crucial para diversos sectores como la agricultura, el turismo y la salud pública.

El análisis se enfoca en información hidrometeorológica proveniente de estaciones del IDEAM, midiendo la temperatura del aire a 2 metros en diferentes municipios.

## 📊 Dataset

**Fuente:** [IDEAM - Instituto de Hidrología, Meteorología y Estudios Ambientales de Colombia](https://www.datos.gov.co/browse?q=IDEAM&sortBy=relevance) (o el enlace específico si se conoce).
**Archivo Utilizado:** `Datos_Hidrometeorol_gicos_Crudos_-_Red_de_Estaciones_IDEAM___Temperatura_20250310 (1).csv`

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

## 🧠 Modelos y Técnicas Utilizadas
Se implementaron y evaluaron los siguientes modelos de regresión para la predicción de temperatura:

1.  **Decision Tree Regressor (Árbol de Decisión para Regresión)**
2.  **Random Forest Regressor (Bosque Aleatorio para Regresión)**
3.  **Support Vector Regressor (SVR - Máquina de Vectores de Soporte para Regresión)**

Se realizaron análisis exploratorios de datos (EDA) con visualizaciones como histogramas y gráficos de series temporales, así como gráficos de temperatura promedio por estación y municipio. También se generaron curvas de aprendizaje y se aplicó validación cruzada (k-folds) para evaluar la robustez de los modelos y optimizar hiperparámetros como `max_depth` (para Decision Tree) y `n_estimators` (para Random Forest), y el tipo de `kernel` (para SVR).

## 📈 Resultados y Evaluación
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

## 🔗 Enlaces Relevantes
- **Código Fuente:** [Notebook del Proyecto](URL_AL_NOTEBOOK_AQUI) <!-- Reemplazar con el enlace real al notebook .ipynb en GitHub o Colab -->
<!-- - **Video de Presentación:** [Presentación del Proyecto en Video](URL_DEL_VIDEO_AQUI) -->
<!-- - **Diapositivas:** [Diapositivas de la Presentación](URL_DE_LAS_DIAPOSITIVAS_AQUI) -->

---

<!-- Opcional: Cómo ejecutar el código -->
<!--
## 🚀 Cómo Empezar
1. Clona este repositorio.
2. Asegúrate de tener el archivo CSV del dataset (`Datos_Hidrometeorol_gicos_Crudos_-_Red_de_Estaciones_IDEAM___Temperatura_20250310 (1).csv`) en la ruta especificada en el notebook (por defecto, en la carpeta "Proyecto-IA" de Google Drive, o ajústalo según sea necesario).
3. Abre el notebook (`Proyecto.ipynb`) en un entorno compatible con Jupyter (como Google Colab, Jupyter Lab, VS Code).
4. Ejecuta las celdas en orden.

**Dependencias Principales:**
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
-->
