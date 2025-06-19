🌳 Introducción

La deforestación representa una de las problemáticas ambientales más preocupantes en Argentina y el mundo. La pérdida de cobertura vegetal tiene consecuencias graves para la biodiversidad, el cambio climático y las comunidades locales.

En este trabajo, se utilizó aprendizaje automático supervisado para analizar datos de deforestación registrados entre los años 2001 y 2020 en distintas provincias de Argentina. El objetivo fue construir un modelo que permita predecir la cantidad de hectáreas deforestadas a partir de variables como el año, la región y la provincia. Esta información podría servir como base para la toma de decisiones ambientales y la prevención de la pérdida de bosques nativos.

📊 Dataset utilizado

Nombre: Argentina_Deforestacion.csv

Observaciones: 2.381 filas

Columnas:
 year
 country
 country_iso2
 region
 region_trase_id
 parent_region
 parent_region_trase_id
 deforestation_hectares

🔄 Metodología

El desarrollo del proyecto siguió una serie de pasos fundamentales en el flujo de trabajo de Machine Learning:
1. Carga y exploración del dataset
   Se importaron los datos y se analizaron sus dimensiones, valores nulos y primeras observaciones.
2. Análisis exploratorio visual 
   Se utilizó un gráfico tipo boxplot para observar la distribución de la deforestación por año, identificando outliers y tendencias generales.
3. Codificación de variables categóricas
   Las regiones fueron transformadas en variables numéricas mediante LabelEncoder, permitiendo su inclusión en el modelo.
4. División del dataset 
   Se separaron los datos en un 80% para entrenamiento y un 20% para evaluación utilizando train_test_split.
5. Entrenamiento de un modelo supervisado
   Se entrenó un modelo de regresión basado en el algoritmo Random Forest.
6. Evaluación del modelo base
   Se aplicaron métricas de regresión: MAE, MSE y R², para medir el desempeño inicial.
7. Optimización de hiperparámetros 
   Se utilizó GridSearchCV para mejorar el rendimiento ajustando parámetros clave como n_estimators y max_depth.
   
📌 El modelo Random Forest Regressor fue elegido por su robustez frente a outliers, su capacidad para manejar relaciones no lineales y por no requerir normalización previa de los datos.

🌐 Resultados

Tras la optimización, el modelo alcanzó un coeficiente R² superior a 0.80, lo cual indica un buen poder predictivo respecto a la variable objetivo (hectáreas deforestadas).

📍 Hallazgos clave:
- Las provincias del norte presentaron valores significativamente altos de deforestación.
- Se detectaron picos importantes entre los años 2008 y 2012, lo cual podría vincularse a factores socioeconómicos o decisiones políticas de ese período.

Estos resultados pueden aportar valor al análisis ambiental y ser utilizados como base para investigaciones futuras o generación de políticas públicas más efectivas.

🌱 Conclusiones y futuro

Este modelo demuestra el potencial del Machine Learning para detectar patrones espaciales y temporales en procesos de degradación ambiental. Puede servir como punto de partida para:
Alertas tempranas de riesgo de deforestación
Evaluación del impacto de políticas públicas
Visualización de tendencias ecológicas
Para el futuro, podría integrarse con variables climáticas, socioeconómicas o uso del suelo para enriquecer el modelo.
