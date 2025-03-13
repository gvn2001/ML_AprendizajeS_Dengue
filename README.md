# 📊 Predicción de Casos de Dengue mediante Aprendizaje Supervisado  

## 📌 Descripción  
Este proyecto implementa algoritmos de **aprendizaje supervisado** para predecir la cantidad de casos de dengue en dos ciudades, basado en datos de la competición [DrivenData](https://www.drivendata.org/competitions/44/dengai-predicting-disease-spread/).  

### 🔍 Metodología  
1. **Exploración y selección de características**  
2. **Entrenamiento de distintos modelos**  
3. **Optimización de hiperparámetros (Random Search y Grid Search)**  
4. **Evaluación mediante el Error Absoluto Medio (MAE)**  

### 🔍 Principales hallazgos  
- **Modelos simples superaron a los más complejos** debido a problemas en la optimización de hiperparámetros.  
- **Árboles de Decisión (AD) fue el mejor modelo**, obteniendo el menor MAE.  

---

## 🛠️ Tecnologías Utilizadas  

### 📌 Lenguaje de Programación  
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### 📌 Librerías Principales  
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white) ![Scikit-Learn](https://img.shields.io/badge/Scikit%20Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=plotly&logoColor=white) ![Seaborn](https://img.shields.io/badge/Seaborn-008080?style=for-the-badge&logo=python&logoColor=white)


---

## 📂 Estructura del Proyecto  

📄 models.ipynb → Notebook que contiene el desarrollo completo del proyecto  

---

## 🚀 Modelos Evaluados  
Se evaluaron distintos modelos con los siguientes resultados:  

| Modelo   | MAE test (DrivenData) | MAE validación | Algoritmo | Hiperparámetros |
|----------|-----------------------|---------------|-----------|----------------|
| **Ejemplo-RL** | 27,2524 | NO | Regresión Lineal | NO |
| **KNN** | 27,550 | 21.9103 | K-Nearest Neighbors | metric = euclidean; n_neighbors = 62; weights = distance |
| **AD** ✅ | **26,7716** | **20.9725** | Árboles de Decisión | max_depth = 3; max_features = sqrt; min_samples_leaf = 13; min_samples_split = 8 |
| **CM-RF** | 28,9663 | 22.3295 | Random Forest | max_depth = 18; max_features = log2; min_samples_leaf = 18; min_samples_split = 2; n_estimators = 256 |
| **GB** | 28,0240 | 21.2116 | Gradient Boosting | n_estimators = 30 |
| **RR** | 27,2620 | 22.6635 | Regresión Ridge | alpha = 2 |

---

## 🏆 Modelo Final Elegido  
El modelo seleccionado para la predicción final fue **Árboles de Decisión (AD)** debido a su mejor rendimiento.  

📌 **Detalles del Modelo Final:**  
- **MAE test (DrivenData):** 26,7716  
- **MAE validación:** 20.9725  
- **Hiperparámetros:** max_depth = 3; max_features = sqrt; min_samples_leaf = 13; min_samples_split = 8  
- **Características usadas:** station_diur_temp_rng_c, station_avg_temp_c, precipitation_amt_mm, station_precip_mm, reanalysis_relative_humidity_percent, station_min_temp_c  
- **Optimización:** Random Search y Grid Search con validación cruzada  

---

## 📈 Conclusiones y Aspectos de Mejora  

✔ **Los modelos más simples obtuvieron mejores resultados**: Se esperaba que algoritmos más complejos como **Random Forest (CM-RF)** o **Gradient Boosting (GB)** fueran superiores, pero la optimización de hiperparámetros resultó desafiante.  
✔ **La selección de características podría mejorarse**: Probar técnicas más avanzadas podría mejorar el rendimiento.  
✔ **El dataset es limitado**: Con más datos, los modelos podrían generalizar mejor y mejorar sus predicciones.  



