# 📊 Documentación del Proyecto — Clasificación de Riesgo de Salud

## 🧠 Integrantes del Grupo
- **Anny Consuelo Arias Figueroa**
- **Leonardo José Sullón Lévano**

---

## 🎯 Objetivos del Análisis
- Identificar cómo factores como la edad, el ejercicio, el sueño, la ingesta de azúcar, el consumo de alcohol y el tabaquismo influyen en el nivel de riesgo de salud.  
- Limpiar, codificar y escalar las variables numéricas y categóricas para preparar el dataset para los modelos de Machine Learning.  
- Entrenar y comparar al menos dos algoritmos de clasificación.  
- Evaluar con métricas: *accuracy, recall, precision, F1-score y ROC-AUC*.  
- Exportar el mejor modelo entrenado como `.pkl` y un `.csv` con las predicciones.  
- Analizar las características más relevantes para predecir riesgo alto de salud.

---

## 🧩 Formulación Analítica y Diccionario de Datos

| Variable | Tipo | Descripción | Notas |
|-----------|------|--------------|-------|
| age | numérica | Edad (años) | 18–80 |
| weight | numérica | Peso (kg) | — |
| height | numérica | Talla (cm) | — |
| exercise | categórica | Nivel de ejercicio | low/medium/high |
| sleep | numérica | Horas de sueño/día | 3–12 |
| sugar_intake | categórica | Ingesta de azúcar | low/medium/high |
| smoking | categórica | Hábito de fumar | yes/no |
| alcohol | categórica | Consumo de alcohol | yes/no |
| married | categórica | Estado civil | yes/no |
| profession | categórica | Ocupación | artist/teacher/... |
| bmi | numérica | Índice de masa corporal | — |
| health_risk | objetivo | Riesgo de salud | low/medium/high |

---

## ⚙️ Configuración Inicial
Librerías principales:
- `pandas`, `numpy`, `matplotlib`
- `scikit-learn` (para modelado, preprocesamiento, métricas)
- `joblib` (para guardar el modelo)

Configuración reproducible mediante `random_state = 42`.

---

## 📥 Recolección del Dataset
Dataset obtenido de **KaggleHub**:  
**"Lifestyle and Health Risk Prediction"**

Dimensiones aproximadas: `(filas, columnas)` con diversas variables de estilo de vida.

---

## 🔍 Análisis Exploratorio de Datos (EDA)
- Verificación de valores nulos (mínimos).  
- Balance de clases: riesgo bajo, medio y alto.  
- Estadísticas descriptivas (`describe()`).  
- Visualización con histogramas por variable numérica.

---

## 🧪 Transformación de Datos
- División en variables **X** (predictoras) y **y** (objetivo).  
- Imputación de valores faltantes (`SimpleImputer`).  
- Estandarización (`StandardScaler`) para numéricas.  
- Codificación (`OneHotEncoder`) para categóricas.  
- División de datos en entrenamiento y prueba (80/20).

---

## 🤖 Modelado
Se entrenaron dos modelos:
1. **Regresión Logística**
2. **Random Forest**

Validación cruzada (`StratifiedKFold`) con métrica F1-macro.

---

## 📈 Evaluación de Modelos
Para cada modelo se calcularon:
- Accuracy, F1 (macro y weighted), Precision, Recall, ROC-AUC.  
- Matriz de confusión y Curvas ROC.

**Mejor modelo:** el que obtuvo mayor F1-macro.

---

## 🚀 Despliegue
- Modelo guardado en `outputs/best_model_<modelo>.pkl`.  
- Resultados exportados en `outputs/predicciones_test.csv`.

El CSV incluye:
- `y_true`, `y_pred` y `proba_<clase>` para cada categoría del riesgo.

---

## 🧭 Conclusiones
- El proyecto demuestra un flujo completo de clasificación con Machine Learning.  
- Se evidencia la importancia del preprocesamiento para obtener métricas confiables.  
- El modelo puede ser base para estudios de **salud preventiva** o **bienestar personal**.

---

**Autores:**  
Leonardo José Sullón Lévano ✦ Anny Consuelo Arias Figueroa  
*Universidad Continental – Curso de Machine Learning (2025)*
