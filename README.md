# 📊 Telecom X – Parte 2: Predicción de Cancelación (Churn)

## 🎯 Propósito del Proyecto
Este proyecto tiene como objetivo **predecir la cancelación de clientes (churn)** en la empresa **Telecom X**, utilizando técnicas de **Machine Learning** aplicadas a los datos históricos de clientes.  
La predicción del churn permite a la compañía **anticipar qué clientes tienen mayor riesgo de abandonar la plataforma** y, de esta manera, implementar estrategias de retención más efectivas.

---

## 🎯 Misión
Tu nueva misión es desarrollar modelos predictivos capaces de prever qué clientes tienen mayor probabilidad de cancelar sus servicios. La empresa quiere anticiparse al problema de la cancelación, y te corresponde a ti construir un pipeline robusto para esta etapa inicial de modelado.

---

## 🧠 Objetivos del Desafío
Preparar los datos para el modelado (tratamiento, codificación, normalización).
Realizar análisis de correlación y selección de variables.
Entrenar dos o más modelos de clasificación.
Evaluar el rendimiento de los modelos con métricas.
Interpretar los resultados, incluyendo la importancia de las variables.
Crear una conclusión estratégica señalando los principales factores que influyen en la cancelación.

## 📂 Estructura del Proyecto
La organización de los archivos es la siguiente:

### ⚙️ Preparación de los Datos

#### 1. Clasificación de variables
- **Variables categóricas:** Tipo de contrato, método de pago, género, servicios adicionales, etc.  
- **Variables numéricas:** Meses de contrato, cuentas totales, gasto mensual, gasto total, edad, etc.

#### 2. Normalización y codificación
- Se aplicó **OneHotEncoding** para variables categóricas nominales.  
- Para variables numéricas se probó la **normalización Min-Max** en algoritmos sensibles a escala (Logistic Regression, SVM, KNN).  
- Modelos basados en árboles (Random Forest, XGBoost) se entrenaron **sin normalización** ya que no dependen de la escala.

#### 3. División de datos
- Los datos fueron separados en:  
  - **Entrenamiento:** 80%  
  - **Prueba:** 20%  
- Se aplicó estratificación para mantener la proporción de clientes que cancelaron/no cancelaron.

---

### 🧠 Modelización y Justificación
- Se entrenaron distintos modelos de clasificación:
  - **Regresión Logística** (baseline, interpretabilidad alta).  
  - **Random Forest** (ensamble, buena capacidad predictiva).  
  - **XGBoost** (robusto ante desbalance, optimiza recall).  
- Se aplicó **balanceo de clases con SMOTE** para evitar sesgo hacia la clase mayoritaria.  
- Métricas usadas: **Accuracy, Precision, Recall, F1-score y ROC-AUC**.  

**Justificación:**  
- Se priorizó **Recall**, ya que el objetivo es identificar la mayor cantidad posible de clientes que podrían cancelar, incluso si implica algunos falsos positivos.

---

### 📈 Exploración de Datos (EDA)

Durante el análisis exploratorio, se observaron los siguientes patrones:

- **Tiempo de contrato × Cancelación:**  
  Los clientes con menos meses de contrato presentan mayor probabilidad de cancelar.

- **Cuentas totales × Cancelación:**  
  Los clientes con menor gasto acumulado tienden a tener más churn.

#### Ejemplos de visualizaciones:
- **Boxplots:** Comparación de distribución de meses de contrato y cuentas totales según la evasión.
  <img width="701" height="556" alt="image" src="https://github.com/user-attachments/assets/ea56c967-7e19-432f-9c5b-955183d633ba" />
- **Heatmap de correlación:** Identificación de variables fuertemente correlacionadas.
  <img width="1126" height="1025" alt="image" src="https://github.com/user-attachments/assets/d0461fb9-7a7e-423c-9bd2-d8869a3ae28c" />
- **Scatter plots con jitter:** Distribución de clientes según variables clave.  
  <img width="798" height="801" alt="image" src="https://github.com/user-attachments/assets/0c2fe5e4-b4a2-4139-829c-9a4006f9d16a" />

---

## 🚀 Ejecución del Cuaderno

### 1. Instalación de dependencias
Asegúrate de tener **Python 3.8+** y luego instala las bibliotecas necesarias:
