# 🔎 Credit Card Fraud Detection

> Proyecto completo de Machine Learning para detectar transacciones fraudulentas en datos reales de tarjetas de crédito.

---

## 🎯 Objetivo

El objetivo principal es **identificar de forma automática las transacciones fraudulentas** en un conjunto de datos altamente desbalanceado, usando técnicas de Machine Learning supervisado.  

El desafío radica en:
- Detectar fraudes con alta recall.
- Minimizar falsos negativos (fraudes no detectados).
- Manejar el desbalance extremo entre clases legítimas y fraudulentas.

---

## 📦 Datos

Dataset público: [Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)  
- la data es muy grande se recomienda descargarla desde su respositorio.

- ~284,807 transacciones
- Solo ~0.17% son fraudes
- Variables: 28 componentes PCA + `Amount` + `Time`
- Etiqueta: `Class` (0 = legítima, 1 = fraude)

---

## 🧭 Metodología

✔️ Descarga y carga del dataset original.  
✔️ Limpieza (eliminación de duplicados).  
✔️ Exploratory Data Analysis (EDA): visualización de montos y clases.  
✔️ Feature Engineering: creación de `Time_of_day` y `Day`.  
✔️ División estratificada Train/Test.  
✔️ Balanceo de clases con **SMOTE**.  
✔️ Entrenamiento y comparación de modelos:
- Logistic Regression
- Random Forest
- XGBoost (con tuning de hiperparámetros vía Optuna)
✔️ Evaluación con métricas clave:
- Recall para la clase fraude
- Average Precision (PR AUC)
- ROC AUC
✔️ Interpretabilidad:
- SHAP values para XGBoost
✔️ Predicción sobre dataset completo y guardado etiquetado en CSV.

---

## ⚙️ Modelos entrenados

✅ **XGBoost** (con hiperparámetros optimizados con Optuna):  
- Mejor balance entre Precision-Recall
- Alta interpretabilidad (SHAP)

✅ **Random Forest**  
- Robusto, menos tuning necesario

✅ **Logistic Regression**  
- Base lineal para comparar

---

## 📊 Resultados de ejemplo

| Modelo              | Average Precision (PR AUC) | ROC AUC | Recall (Fraude) |
|----------------------|---------------------------|---------|------------------|
| XGBoost              | 0.8331                    | 0.9688  | 0.8421           |
| Random Forest        | 0.7612                    | 0.9799  | 0.8421           |
| Logistic Regression  | 0.7550                    | 0.9818  | 0.8842           |

✅ XGBoost elegido como **modelo final** para etiquetar la base completa.

---

