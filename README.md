# 💳 Predicción de Abandono de Clientes de Tarjeta de Crédito

Este proyecto aborda un problema real de negocio bancario: la predicción de abandono (churn) de clientes de tarjetas de crédito, con el objetivo de identificar clientes en riesgo y permitir acciones preventivas por parte del banco.

Se realiza un análisis exploratorio exhaustivo, un preprocesamiento avanzado, técnicas de balanceo de clases, reducción de dimensionalidad (PCA) y la comparación de distintos modelos de Machine Learning orientados a maximizar la métrica F1-score, adecuada para datos desbalanceados.

## 🎯Objetivo del proyecto

- Analizar el perfil demográfico, financiero y transaccional de los clientes.
- Comprender los factores asociados al abandono de clientes.
- Tratar el fuerte desbalance de clases presente en el dataset.
- Construir y comparar modelos predictivos para detectar churn.
- Evaluar modelos con métricas robustas y visualizaciones interpretables.

## 🏦Contexto del negocio

Un banco observa un incremento en la pérdida de clientes de tarjetas de crédito.
Dado que solo ~16% de los clientes abandonan, el desafío principal es detectar correctamente estos casos minoritarios sin sacrificar precisión.

## 📌Anticipar el churn permite:

- Reducir costos de adquisición.
- Mejorar la retención.
- Diseñar estrategias personalizadas de fidelización.

## 📊Dataset

- Fuente: Analyttica – Bank Churners Dataset
- Registros: ~10.000 clientes
- Variables: ~18 características
- Tipos de variables:
  - Demográficas: edad, género, estado civil, educación.
  - Financieras: límite de crédito, ingresos, categoría de tarjeta.
  - Comportamiento: transacciones, meses inactivos, productos contratados.
- Target:
  - Attrition_Flag
  - 1: Cliente que abandonó
  - 0: Cliente activo

## 🔍Metodología

1️⃣ Análisis Exploratorio de Datos (EDA)
- Distribuciones (histogramas y boxplots).
- Análisis por género, categoría de tarjeta, ingresos y educación.
- Visualizaciones interactivas con Plotly.
- Análisis de normalidad, curtosis y multimodalidad.
- Matrices de correlación (Pearson y Spearman).

2️⃣ Preprocesamiento de Datos
- Conversión de variables categóricas:
- One-Hot Encoding.
- Eliminación de categorías “Unknown”.
- Codificación binaria de variables objetivo y género.
- Limpieza de columnas irrelevantes (CLIENTNUM).

3️⃣ Manejo del Desbalance de Clases
- El dataset original presenta solo 16% de churn.
- Se aplica SMOTE (Synthetic Minority Over-sampling Technique) para:
  - Balancear las clases.
  - Mejorar la capacidad predictiva de los modelos.
  - Comparación de correlaciones antes y después del balanceo.

4️⃣ Reducción de Dimensionalidad
- PCA (Principal Component Analysis) sobre variables categóricas codificadas.
- Selección de 4 componentes principales.
- Evaluación de varianza explicada acumulada.
- Visualización de componentes y nuevas correlaciones.

5️⃣ Modelado Predictivo
- Modelos evaluados utilizando pipelines con escalado:

🌲 Random Forest Classifier

🚀 AdaBoost Classifier

🧠 Support Vector Machine (RBF Kernel)

- Características clave seleccionadas:
- Variables transaccionales.
- Componentes principales (PCA).
- Métricas de comportamiento del cliente.

6️⃣ Evaluación de Modelos
- Validación cruzada (5-fold).
- Métrica principal: F1-score.
- Evaluación en:
  - Datos balanceados (SMOTE).
  - Datos originales (sin oversampling).
  - Matriz de confusión.
  - Curva Precision-Recall.

## 📈Resultados

- Random Forest muestra el mejor equilibrio entre precisión y recall.
- El uso de SMOTE mejora significativamente la detección de churn.
- PCA ayuda a reducir dimensionalidad sin perder poder predictivo.
- El modelo mantiene buen desempeño al evaluarse sobre datos originales.

📌 El enfoque prioriza detectar clientes que abandonan, incluso a costa de algunos falsos positivos, alineado con el objetivo del negocio.

## 🛠️Tecnologías y Librerías

- Python
- Pandas / NumPy
- Matplotlib / Seaborn
- Plotly
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Scikit-plot

## 📁Estructura del proyecto

├── BankChurners.csv
├── clientes_tarjeta_de_credito.py
└── README.md


## 🚀Posibles mejoras futuras

- Ajuste de hiperparámetros con GridSearch / Optuna.
- Interpretabilidad con SHAP o LIME.
- Modelos XGBoost / LightGBM.
- Implementación como API para scoring en tiempo real.
- Segmentación de clientes en riesgo.

## 👤Autor

Flavia Hepp
Proyecto de Data Science aplicado a retención de clientes y analítica bancaria.
