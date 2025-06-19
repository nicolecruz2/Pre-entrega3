🌳 Introducción

La deforestación representa una de las problemáticas ambientales más preocupantes en Argentina y el mundo. La pérdida de cobertura vegetal tiene consecuencias graves para la biodiversidad, el cambio climático y las comunidades locales.

En este trabajo, se utilizó aprendizaje automático supervisado para analizar datos de deforestación registrados entre los años 2001 y 2020 en distintas provincias de Argentina. El objetivo fue construir un modelo que permita predecir la cantidad de hectáreas deforestadas a partir de variables como el año, la región y la provincia. Esta información podría servir como base para la toma de decisiones ambientales y la prevención de la pérdida de bosques nativos.

📊 Dataset utilizado

Fuente: Base entregada por la cátedra

Observaciones: 2.381 filas

Columnas:
Año
País
ISO del País
Región
ISO de Región
Provincia
ISO de Provincia
Deforestación en hectáreas

Se eliminaron columnas redundantes como los códigos ISO

🔄 Metodología

Se aplicaron los siguientes pasos:
1. Carga y exploración de datos
2. Análisis exploratorio con gráficos
3. Codificación de variables categóricas
4. División del dataset en entrenamiento y prueba
5. Entrenamiento de modelo supervisado
6. Evaluación con métricas de regresión
7. Optimización de hiperparámetros con GridSearchCV
El modelo elegido fue Random Forest Regressor, por su robustez frente a outliers y su buen rendimiento sin necesidad de normalización previa.

🌐 Resultados

El modelo obtuvo un coeficiente R² superior al 0.80 luego de la optimización de hiperparámetros, lo que indica un buen ajuste para predecir la cantidad de hectáreas deforestadas.
Entre los hallazgos destacados:
Algunas provincias del norte argentino mostraron altos niveles de deforestación.
Se observaron picos entre 2006 y 2012.

🌱 Conclusiones y futuro

Este modelo demuestra el potencial del Machine Learning para detectar patrones espaciales y temporales en procesos de degradación ambiental. Puede servir como punto de partida para:
Alertas tempranas de riesgo de deforestación
Evaluación del impacto de políticas públicas
Visualización de tendencias ecológicas
Para el futuro, podría integrarse con variables climáticas, socioeconómicas o uso del suelo para enriquecer el modelo.
