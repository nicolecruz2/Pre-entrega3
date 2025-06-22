# 🌳 Proyecto de Machine Learning: Deforestación en Argentina (2001–2020)

**Grupo 12**  
**Integrantes:**  
- Cruz Nicole  
- Ulloa Melina  

---

## 1. 📘 Introducción

La deforestación representa una de las problemáticas ambientales más preocupantes en Argentina y el mundo. La pérdida de cobertura vegetal tiene consecuencias graves para la biodiversidad, el cambio climático y las comunidades locales.

En este trabajo aplicamos **aprendizaje automático supervisado** para analizar y predecir la deforestación en Argentina entre los años **2001 y 2020**, utilizando variables territoriales. 

El objetivo fue construir un **modelo de regresión** capaz de predecir la cantidad de hectáreas deforestadas a partir del **año y la provincia**.

> ✅ Con el fin de mejorar la calidad del análisis, unificamos dos datasets distintos para enriquecer la base de datos original, lo cual nos permitió lograr un modelo más completo y generalizable.

---

## 2. 📊 Datasets utilizados

### 2.1 Dataset 1: `Argentina_Deforestacion.csv`
- **Filas:** 2.381  
- **Columnas principales:**  
  `year`, `country`, `country_iso2`, `region`, `region_trase_id`, `parent_region`, `parent_region_trase_id`, `deforestation_hectares`

### 2.2 Dataset 2: `Dataset_Forest_ConservationAreas_Funding_inSouthAmerica_PAN2024.csv`
- **Filas originales:** 10.328  
- **Tras limpieza y filtrado:**  
  Se unificaron **11.417 observaciones** entre ambos datasets.

> Este segundo dataset aportó información territorial adicional, incluyendo regiones y años no contemplados en el primero. Su incorporación fue clave para ampliar la cobertura del análisis y mejorar la capacidad predictiva.

---

## 3. 🔄 Metodología aplicada

### 3.1 Carga y limpieza de datos
- Se importaron ambos datasets.
- Se estandarizaron nombres de columnas.
- Se seleccionaron solo las columnas clave:
  - `year`
  - `parent_region`
  - `deforestation_hectares`
- Se unificaron los dos datasets en una única base limpia.

### 3.2 Exploración y análisis visual
- Se utilizaron boxplots para visualizar la deforestación por año.
- Se identificaron:
  - Años con picos altos (2008–2012).
  - Outliers en los extremos de la serie.

### 3.3 Codificación de variables categóricas
- Se aplicó `LabelEncoder` a `parent_region` para convertirla en variable numérica (`parent_region_encoded`).

### 3.4 Preparación de variables para el modelo
- **X (features):** `year`, `parent_region_encoded`  
- **y (target):** `deforestation_hectares`

### 3.5 División del dataset
- División en entrenamiento (80%) y prueba (20%) utilizando `train_test_split`.

---

## 4. 🤖 Entrenamiento y evaluación de modelos

### 4.1 Modelo base: `RandomForestRegressor`
- Entrenado con hiperparámetros por defecto.

**Métricas del modelo base:**
- **MAE:** 658.06
- **MSE:** 8.625.511
- **R²:** 0.29

### 4.2 Optimización de hiperparámetros con `GridSearchCV`
- Parámetros evaluados:
  - `n_estimators`: 50, 100, 150
  - `max_depth`: 5, 10, None

**Mejores parámetros encontrados:**
- `max_depth`: 5
- `n_estimators`: 150

**Métricas tras optimización:**
- **MAE:** 684.51
- **MSE:** 8.568.047
- **R²:** 0.29

> 🧩 El modelo `Random Forest` fue elegido por su robustez frente a outliers, su capacidad para modelar relaciones no lineales y su facilidad de uso sin necesidad de normalización previa.

---

## 5. 🌐 Resultados generales

Aunque el rendimiento del modelo se mantuvo en un nivel moderado (R² = 0.29), logramos:

- **Mejorar la base de datos** con más casos y regiones.
- **Capturar tendencias temporales claras** (2008–2012).
- Generar una base sólida para futuras mejoras.

---

## 6. 📍 Hallazgos clave

- **Provincias del norte** como Chaco y Santiago del Estero presentan los niveles más altos de deforestación.
- **Período 2008–2012** mostró los picos más importantes de pérdida de cobertura vegetal.
- El modelo pudo **detectar tendencias temporales**, aunque aún tiene margen de mejora en su poder predictivo.

---

## 7. 🌱 Conclusiones y futuro

Este trabajo demuestra que el **Machine Learning supervisado** puede ser una herramienta útil para entender y anticipar procesos ambientales como la deforestación.

> 🔄 **La decisión de unificar dos datasets** fue clave para superar la limitación de datos insuficientes y generar un análisis más representativo del problema.

### Posibles mejoras futuras:
- Incluir variables **climáticas**, **económicas** o de **uso del suelo**.
- Incorporar datos satelitales (NDVI) para enriquecer la dimensión espacial.
- Probar modelos más complejos: `XGBoost`, `LightGBM`, redes neuronales.
- Aplicar **feature engineering** para crear nuevas variables explicativas.
