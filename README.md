# README: Proyecto Telecom X - Modelo Predictivo de Churn  

## 📌 Descripción del Proyecto  
Este proyecto tiene como objetivo desarrollar un modelo predictivo para identificar clientes con alta probabilidad de cancelar sus servicios (**Churn**) en una empresa de telecomunicaciones. El enfoque incluye:  
- Preparación y limpieza de datos.  
- Análisis de correlación y selección de características.  
- Entrenamiento y evaluación de modelos de clasificación.  
- Interpretación de resultados y recomendaciones estratégicas.  

---

## 🎯 Objetivos  
1. **Preparar los datos**:  
   - Tratamiento de valores nulos.  
   - Codificación de variables categóricas.  
   - Normalización con `StandardScaler`.  
2. **Seleccionar variables clave**:  
   - Identificar correlaciones y eliminar redundancias.  
3. **Entrenar modelos**:  
   - Comparar rendimiento de **Regresión Logística** y **Random Forest**.  
4. **Optimizar hiperparámetros**:  
   - Mejorar métricas con `GridSearchCV` y balanceo de datos (**SMOTE**).  
5. **Interpretar resultados**:  
   - Analizar factores críticos que influyen en el Churn.  

---

## 📊 Estructura del Proyecto  

### 1. Preparación de Datos  
- Eliminación de columnas irrelevantes (ej. `customerID`).  
- Filtrado de valores desconocidos (`unkomn` en la columna `Churn`).  
- Codificación **One-Hot** para variables categóricas.  
- Normalización con `StandardScaler`.  

### 2. Análisis Exploratorio  
- **Distribución de Churn**: 73% "No" vs. 27% "Yes".  
- **Correlaciones destacadas**:  
  - `Tipo de contrato_month-to-month` (+0.91 con Churn).  
  - `Meses de contrato` (-0.37 con Churn).  
- Visualizaciones con `Plotly` (boxplots, scatter plots).  

### 3. Modelado  
#### Modelos Evaluados:  
- **Regresión Logística**:  
  - Exactitud: **79.8%** (mejor recall: 54.5%).  
  - Optimizado con `C=10` y regularización `L2`.  
- **Random Forest**:  
  - Exactitud: **79.1%** (mejor F1-score tras ajuste: 56.9%).  
  - Hiperparámetros óptimos: `max_depth=10`, `min_samples_leaf=4`.  

#### Técnicas de Mejora:  
- `GridSearchCV`: Para optimizar hiperparámetros.  
- `SMOTE`: Balanceo de datos para mejorar detección de Churn.  

### 4. Resultados Clave  
| Modelo                | Exactitud | Precisión | Recall | F1-Score |  
|-----------------------|-----------|-----------|--------|----------|  
| Regresión Logística    | 79.8%     | 64.3%     | 54.5%  | 59.0%    |  
| Random Forest          | 79.4%     | 64.3%     | 51.0%  | 56.9%    |  

**Mejor modelo**: Regresión Logística (mayor equilibrio entre precisión y recall).  

---

## 🔍 Hallazgos Clave  
### Factores que **aumentan** Churn:  
- Contratos mensuales (`month-to-month`).  
- Método de pago `electronic check`.  
- Servicio de Internet `fibra óptica`.  

### Factores que **reducen** Churn:  
- Mayor duración del contrato (`Meses de contrato`).  
- Pagos automáticos (`bank transfer` o `credit card`).  

---

## 📂 Archivos Relevantes  
### Datos:  
- `df_normalizado_customer.xlsx`: Datos originales normalizados.  
- `df_enco.xlsx`: Datos codificados.  

### Resultados:  
- `datoscorr.xlsx`: Matriz de correlación.  
- `df_final.xlsx`: Dataset final para modelado.  

---

## 🛠️ Tecnologías Utilizadas  
- **Lenguaje**: Python.  
- **Librerías**:  
  - `pandas`, `numpy`: Manipulación de datos.  
  - `scikit-learn`: Modelado (`LogisticRegression`, `RandomForest`, `GridSearchCV`).  
  - `plotly`, `seaborn`: Visualizaciones.  
  - `imbalanced-learn` (**SMOTE**): Balanceo de datos.  

---

## 📝 Conclusiones y Recomendaciones  
### Acciones prioritarias:  
1. Ofrecer incentivos para migrar clientes de contratos mensuales a anuales.  
2. Promover pagos automáticos para reducir Churn.  
3. Monitorear clientes con fibra óptica y alto costo mensual.  

### Próximos pasos:  
- Implementar el modelo en producción con monitoreo continuo.  
- Explorar modelos avanzados (**XGBoost**, **Redes Neuronales**).  

---

## 👨‍💻 Autor  
- **Nombre**: Kevin Gutierrez Cancino  
- **Contacto**: kevincancino15@gmail.com.  

*Documentación generada para el proyecto Telecom X - Parte 2 (Rev00).*  
📅 **Fecha**: 14/09/25. 
