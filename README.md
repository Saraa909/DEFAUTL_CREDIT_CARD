# Predicción de Enfermedad Cardíaca - Análisis con UCI Heart Disease Dataset

Autor: Sara González Rodríguez

## Descripción

Este proyecto se centra en el análisis del conjunto de datos UCI Heart Disease, disponible en el repositorio de la University of California, Irvine (UCI). El objetivo principal es desarrollar y evaluar modelos de machine learning para predecir la presencia de enfermedad cardíaca en pacientes, basándose en un conjunto de características clínicas.

## Dataset

El dataset original de UCI Heart Disease es multivariado y contiene 76 atributos. Sin embargo, este análisis se enfoca en un subconjunto de 14 variables, consideradas las más relevantes para la predicción del diagnóstico:

* **age:** Edad del paciente
* **sex:** Sexo (1 = masculino; 0 = femenino)
* **cp:** Tipo de dolor en el pecho (0–3)
* **trestbps:** Presión arterial en reposo
* **chol:** Colesterol sérico en mg/dl
* **fbs:** Azúcar en sangre en ayunas > 120 mg/dl (1 = verdadero; 0 = falso)
* **restecg:** Resultados del electrocardiograma en reposo (0–2)
* **thalach:** Frecuencia cardíaca máxima alcanzada
* **exang:** Angina inducida por ejercicio (1 = sí; 0 = no)
* **oldpeak:** Depresión del ST inducida por ejercicio en relación al reposo
* **slope:** Pendiente del segmento ST en el ejercicio máximo (0–2)
* **ca:** Número de vasos principales coloreados por fluoroscopia (0–3)
* **thal:** Resultado de la prueba de talio (1 = normal; 2 = defecto fijo; 3 = defecto reversible)
* **num:** Diagnóstico de enfermedad cardíaca (0 = no; 1,2,3,4 = sí)

## Análisis Exploratorio de Datos (EDA)

El Análisis Exploratorio de Datos reveló lo siguiente:

* El dataset presenta una variabilidad considerable en las características de los pacientes, reflejando una diversidad en edad, condición física y resultados de pruebas médicas.
* La edad promedio de los pacientes sugiere que la mayoría son de mediana edad, lo cual es un factor de riesgo importante para enfermedades cardíacas.
* Las medidas de presión arterial y colesterol muestran una amplia dispersión, indicando diferentes niveles de riesgo cardiovascular entre los pacientes.
* La frecuencia cardíaca máxima alcanzada varía significativamente, lo que refleja la diversidad en la condición física de los pacientes.
* Las mediciones de la depresión del segmento ST y los resultados de fluoroscopias proporcionan información relevante sobre la respuesta cardíaca y la posible afectación de los vasos.
* La variable objetivo (num) muestra una distribución variada, incluyendo pacientes sin enfermedad y aquellos con diferentes grados de afectación.  Para el modelado, esta variable fue binarizada (0 = no enfermedad, 1 = enfermedad).

## Modelado y Resultados

Se implementaron y compararon varios modelos de clasificación:

* KNN
* Árbol de Decisión
* Regresión Logística
* Random Forest

Los resultados, evaluados mediante la métrica AUC y matrices de confusión, indican que el modelo de **Random Forest** supera a los demás en términos de rendimiento predictivo y estabilidad.

* **Random Forest:** Obtuvo el AUC más alto (0.96) y demostró la mejor capacidad para distinguir entre pacientes con y sin enfermedad cardíaca, minimizando tanto los falsos positivos como, crucialmente, los falsos negativos.
* **Regresión Logística:** Mostró un rendimiento competitivo con un AUC de 0.92 y ofrece la ventaja de una mayor interpretabilidad.
* **KNN y Árbol de Decisión:** Tuvieron un rendimiento inferior en comparación.

Las matrices de confusión confirmaron la superioridad de Random Forest en la correcta clasificación de pacientes.

## Conclusiones

El análisis del conjunto de datos UCI Heart Disease destaca la importancia de considerar múltiples variables clínicas para la predicción precisa de enfermedades cardíacas. El modelo de Random Forest demostró ser el más efectivo en este contexto, proporcionando un equilibrio óptimo entre precisión y la minimización de errores críticos. Aunque la Regresión Logística es una alternativa válida por su interpretabilidad, Random Forest se posiciona como la herramienta más robusta para la predicción en este dataset.

## Contenido del Repositorio

* `MODELADOS.ipynb`:  Notebook de Jupyter con el código del análisis exploratorio, preprocesamiento y modelado.
* `heart_disease_uci.csv`: El dataset utilizado.
* `README.md`:  Este archivo, que proporciona una descripción general del proyecto.