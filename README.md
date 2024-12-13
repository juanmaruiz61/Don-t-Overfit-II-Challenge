# Proyecto: Don’t Overfit II

## Descripción del Problema
Nos enfrentamos con el desafío de modelar una matriz de 20,000 x 200 variables continuas utilizando tan solo 250 muestras de entrenamiento, con el objetivo de predecir un resultado binario sin caer en el sobreajuste. 

## Contexto del Problema
La naturaleza del desafío está en el desequilibrio entre el número de variables y la cantidad limitada de datos de entrenamiento disponibles. Este desequilibrio hace que sea muy fácil para los modelos de aprendizaje automático sobreajustar los datos.

## Objetivos
1. **Predecir el objetivo binario**: Cada fila en la matriz debe ser categorizada correctamente en una de dos clases, basándonos en las 200 variables continuas proporcionadas.
2. **Evitar el sobreajuste**: Implementar técnicas y enfoques que aseguren que el modelo no se ajuste demasiado a los datos de entrenamiento limitados, sino que pueda predecir con precisión en un conjunto de prueba mucho más grande.

## Restricciones
- **Conjunto de entrenamiento reducido**: Solo 250 muestras de entrenamiento disponibles.
- **Alta dimensionalidad**: 200 variables continuas por muestra.
- **Conjunto de pruebas extenso**: 19,750 muestras para las cuales se deben generar predicciones.

---

## Enfoque del Proyecto
El proyecto aborda el problema de modelar numerosas variables continuas utilizando un conjunto de entrenamiento limitado, sin sobreajuste. Nuestro procedimiento se puede dividir en los siguientes pasos:

### 1. Carga y Verificación de Datos
- **Lectura de archivos CSV**: Cargamos los datos de entrenamiento (`train.csv`), prueba (`test.csv`) y el archivo de muestra para el envío (`sample_submission.csv`).
- **Verificación de valores nulos**: Comprobamos que los datos no contengan valores nulos para evitar problemas durante el análisis y modelado.

### 2. Análisis Exploratorio de Datos
- **Visualización**: Gráficos de torta para la distribución de clases del objetivo binario en el conjunto de entrenamiento.
- **Distribución de variables**: Histogramas para identificar patrones y diferencias entre clases objetivo.

### 3. Ingeniería de Características
- **Estandarización de datos**: Uso de `StandardScaler` para normalizar las variables continuas.
- **Generación de nuevas características**:
  - Estadísticas descriptivas: suma, mínimo, máximo, media, desviación estándar, asimetría, curtosis y mediana.
  - Percentiles: Cálculo de percentiles específicos (1%, 5%, 50%, 99%) por fila.
  - Cuadrados de las variables.
  - Frecuencia de valores.

### 4. Preparación de Datos
- **División del conjunto de datos**: División estratificada para mantener la proporción de clases.
- **Normalización y transformación**: Aplicación de técnicas para preparar los datos para el modelado.

### 5. Entrenamiento de Modelos
- **Clasificadores utilizados**:
  - Regresión logística (Logistic Regression)
  - Bosques aleatorios (Random Forest)
  - Máquinas de soporte vectorial (SVM)
  - Bosques de árboles extra (Extra Trees)
- **Clasificador de votación**: Combinación de clasificadores con votación "suave" (`soft voting`).
- **Validación cruzada estratificada**: Uso de 10 particiones (`k-fold cross-validation`) para evaluar el modelo.

### 6. Evaluación y Análisis de Resultados
- **Métricas de rendimiento**: F1-score y ROC-AUC.
- **Visualización de métricas**: Matriz de confusión, curvas ROC, curvas de precisión-recall, entre otras.

---

## Resumen del Proceso
El enfoque combinó análisis de datos, estandarización, generación de características y uso de modelos de aprendizaje automático con métodos de validación. Este enfoque ayudó a mitigar el riesgo de sobreajuste y a garantizar que el modelo generalice bien con datos nuevos.

---

## Resultados
### Resultados obtenidos en entrenamiento:
- *(Agregar resultados específicos aquí)*

### Resultados obtenidos en test:
- *(Agregar resultados específicos aquí)*

---

## Conclusiones
1. **Equilibrio entre ajuste y generalización**: Encontrar un balance adecuado para evitar el sobreajuste y garantizar una buena capacidad de generalización.
2. **Estrategias clave para evitar el sobreajuste**:
   - Regularización: Uso de L1 y L2 para penalizar coeficientes grandes.
   - Validación cruzada: Evaluación robusta del modelo.
   - Selección de características: Reducción de variables irrelevantes.
   - Modelos de ensamble: Métodos como bagging, boosting y stacking.
3. **Importancia de la exploración de datos**: Un análisis exhaustivo lleva a mejores resultados.
4. **Evaluación adecuada**: Uso de métricas como F1-score y ROC-AUC para medir el rendimiento del modelo.

En conclusión, el problema “Don’t Overfit II” subraya la complejidad de construir modelos precisos y generalizables. Las técnicas para evitar el sobreajuste, junto con una sólida validación y experimentación, son fundamentales para lograr buenos resultados en problemas de machine learning.


