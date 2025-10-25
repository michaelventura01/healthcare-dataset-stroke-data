#### **Objetivo**
Predecir la probabilidad de que un paciente sufra un stroke **(ACV)** a partir de variables demográficas, clínicas y de estilo de vida.


#### **Tipo de Modelado**
- Tipo de problema: Clasificación binaria (stroke: 0 o 1)
- Modelos a aplicar:
  - 3 modelos tradicionales:
    - Logistic Regression
    - Random Forest
    - Support Vector Machine (SVM)
  - Red Neuronal con 1 capa oculta
  - Red Neuronal con múltiples capas ocultas (DNN)


#### **Procesamiento y Preparación del Dataset**
<table>
  <thead>
    <th>Columna</th>
    <th>Tipo</th>
    <th>Tratamiento</th>
  </thead>
  <tbody>
    <tr>
      <td>id</td>	
      <td>Identificador</td>	
      <td>Eliminar (no aporta valor predictivo)</td>
    </tr>
    <tr>
      <td>gender</td>
      <td>Categórica</td>
      <td>One-hot encoding o Label encoding</td>
    </tr>
    <tr>
      <td>age</td>
      <td>Numérica</td>
      <td>Normalizar o escalar</td>
    </tr>
    <tr>
      <td>hypertension</td>	
      <td>Binaria (0/1)</td>	
      <td>Usar directamente</td>
    </tr>
    <tr>
      <td>heart_disease</td>	
      <td>Binaria (0/1)</td>	
      <td>Usar directamente</td>
    </tr>
    <tr>
      <td>ever_married</td>
      <td>Categórica</td>	
      <td>Convertir a 0 (No), 1 (Yes)</td>
    </tr>
    <tr>
      <td>work_type</td>
      <td>Categórica</td>	
      <td>One-hot encoding</td>
    </tr>
    <tr>
      <td>Residence_type</td>
      <td>Categórica</td>	
      <td>One-hot encoding (Urban/Rural)</td>
    </tr>
    <tr>
      <td>avg_glucose_level</td>	
      <td>Numérica</td>	
      <td>Normalizar o escalar</tr>
    <tr>
      <td>bmi</td>	
      <td>Numérica</td>	
      <td>Imputar valores nulos (media o regresión)</td>
    </tr>
    <tr>
      <td>smoking_status</td>	
      <td>Categórica</td>	
      <td>One-hot encoding, considerar categoría 'unknown'</td>
    <tr>
      <td>stroke</td>	
      <td>Binaria</td>	
      <td>Variable objetivo</td>
    </tr>
  </tbody>
</table>

#### **Pipeline sugerido (EDA y Modelado)**
**EDA (Exploratory Data Analysis)**
- Distribución del target (stroke) → Notarás que está desbalanceado.
- Distribuciones por age, bmi, glucose_level.
- Gráficas por categoría (work_type vs stroke, gender vs stroke).
- Heatmap de correlaciones.
- Outliers (en bmi, glucose, etc).

**Preprocesamiento**
- Encoding de variables categóricas.
- Escalado de variables numéricas.
- Imputación de valores nulos (bmi).
- Balanceo de clases con SMOTE o class_weight.

**Modelos Tradicionales**
- Logistic Regression (baseline simple, interpretable).
- Random Forest (para ver importancia de variables).
- SVM (bueno para espacios de alta dimensión).

Evalúa con:
- accuracy, precision, recall, f1-score, AUC
- Confusion matrix
- Curva ROC
