
# Predicción de Default de Tarjeta de Crédito – Optimización de Hiperparámetros

**Autora:** Sara González Rodríguez

## Descripción

Este proyecto analiza el riesgo de incumplimiento de pago en clientes de tarjetas de crédito, utilizando técnicas de aprendizaje automático. El enfoque se centra en comparar tres modelos de clasificación: un modelo base sin ajuste, uno optimizado mediante búsqueda aleatoria (**Random Search**) y otro con optimización bayesiana usando **Optuna**. El objetivo es evaluar cómo la optimización de hiperparámetros mejora el rendimiento predictivo en términos de clasificación y calibración de probabilidades.

## Dataset

Se emplea el dataset **"Default of Credit Card Clients"**, proveniente de la base de datos del UCI Machine Learning Repository. Este contiene información de 30.000 clientes, incluyendo características socioeconómicas y financieras.

Entre las variables más importantes se incluyen:

- **LIMIT_BAL:** Monto del crédito otorgado
- **AGE:** Edad del cliente
- **SEX, EDUCATION, MARRIAGE:** Datos demográficos
- **PAY_0 a PAY_6:** Historial de pagos anteriores
- **BILL_AMT1 a BILL_AMT6:** Monto de facturación en los últimos seis meses
- **PAY_AMT1 a PAY_AMT6:** Pagos realizados en los últimos seis meses
- **default:** Variable objetivo (1 = incumplimiento, 0 = no)

## Análisis Exploratorio de Datos (EDA)

- Se identificó un desbalance en la variable objetivo: el 22 % de los clientes incurrieron en default.
- El crédito otorgado se concentra entre los 50.000 y 150.000 unidades, y la mayoría de clientes tiene entre 25 y 40 años.
- Las variables más correlacionadas con el default fueron los atrasos en pagos (`PAY_0` a `PAY_6`), mientras que otras como edad o facturación mensual mostraron baja correlación.

## Modelado y Resultados

Se implementaron tres enfoques:

- **Modelo Base (Random Forest sin ajuste):** Usado como punto de partida.
- **Modelo con Random Search:** Ajuste de hiperparámetros usando búsqueda aleatoria en un espacio definido.
- **Modelo con Optuna:** Optimización bayesiana para encontrar la mejor combinación de hiperparámetros.

### Métrica de evaluación:  
Se utilizó **ROC AUC** tanto en validación cruzada como en el conjunto de prueba.

| Modelo            | AUC (Entrenamiento CV) | AUC (Test) |
|-------------------|-------------------------|------------|
| Baseline          | 0.764                   | 0.760      |
| Random Search     | 0.782                   | 0.779      |
| Optuna (Bayesian) | 0.783                   | 0.782      |

### Visualizaciones realizadas:

- Curvas ROC comparadas entre modelos
- Distribución de probabilidades predichas
- Gráfico de barras con el AUC de cada modelo
- Matrices de confusión (tras binarización de probabilidades)
- Importancia de características (modelo final)

## Conclusiones

Los resultados muestran que la optimización de hiperparámetros mejora el rendimiento predictivo frente al modelo base. Ambos métodos, Random Search y Optuna, presentan mejoras consistentes. Aunque Optuna ofrece un rendimiento ligeramente superior, Random Search se mantiene como una alternativa válida y computacionalmente menos costosa. Además, los modelos optimizados muestran mejor calibración en la predicción de probabilidades, lo que es clave para la toma de decisiones en contextos de riesgo crediticio.

## Contenido del Repositorio

- Código de hiperparámetros, EDA, y gráficos
- Base de datos utilizada
- Archivo README
