# Resultados de Ejecución - Sistema Multiagente para Predicción de Churn

## Información General

* Proyecto: Sistema Multiagente para Predicción de Churn
* Dataset: Telco Customer Churn
* Entorno: Google Colab
* Lenguaje: Python
* Tipo de problema detectado: Clasificación

---

# Agente 1 - Normalizador

## Funciones realizadas

* Carga del dataset original.
* Eliminación de la columna `customerID`.
* Conversión de variables al formato adecuado.
* Tratamiento de valores faltantes.
* Eliminación de registros duplicados.
* Codificación de variables categóricas.
* Escalado de variables numéricas.
* Generación del dataset limpio.

## Resultados obtenidos

| Métrica                  | Valor |
| ------------------------ | ----- |
| Filas originales         | 7043  |
| Columnas originales      | 21    |
| Valores nulos detectados | 0     |
| Duplicados eliminados    | 22    |
| Filas finales            | 7021  |
| Columnas finales         | 20    |

Archivo generado:

```text
dataset_limpio.csv
```

---

# Agente 2 - Entrenador

## Tipo de problema detectado

Clasificación binaria (Churn).

## División de datos

| Concepto              | Valor |
| --------------------- | ----- |
| Total registros       | 7021  |
| Entrenamiento         | 5616  |
| Prueba                | 1405  |
| Variables predictoras | 19    |

---

## Modelos Evaluados

### Regresión Logística

| Métrica   | Valor  |
| --------- | ------ |
| Accuracy  | 0.8000 |
| Precision | 0.7904 |
| Recall    | 0.8000 |
| F1-Score  | 0.7928 |

### Árbol de Decisión

| Métrica   | Valor  |
| --------- | ------ |
| Accuracy  | 0.7495 |
| Precision | 0.7429 |
| Recall    | 0.7495 |
| F1-Score  | 0.7457 |

### Random Forest

| Métrica   | Valor  |
| --------- | ------ |
| Accuracy  | 0.7801 |
| Precision | 0.7653 |
| Recall    | 0.7801 |
| F1-Score  | 0.7676 |

### Gradient Boosting

| Métrica   | Valor  |
| --------- | ------ |
| Accuracy  | 0.8007 |
| Precision | 0.7903 |
| Recall    | 0.8007 |
| F1-Score  | 0.7922 |

### KNN

| Métrica   | Valor  |
| --------- | ------ |
| Accuracy  | 0.7516 |
| Precision | 0.7426 |
| Recall    | 0.7516 |
| F1-Score  | 0.7463 |

---

## Modelo Ganador

### Regresión Logística

Métrica principal utilizada:

```text
F1-Score = 0.7928
```

El modelo fue seleccionado automáticamente por el Agente 2 debido a que obtuvo el mayor F1-Score entre todos los modelos evaluados.

---

## Matriz de Confusión del Modelo Ganador

| Valor Real | Predicción 0 | Predicción 1 |
| ---------- | ------------ | ------------ |
| 0          | 928          | 105          |
| 1          | 176          | 196          |

Interpretación:

* 928 clientes fueron clasificados correctamente como no churn.
* 196 clientes fueron clasificados correctamente como churn.
* 105 clientes fueron clasificados incorrectamente como churn.
* 176 clientes con churn no fueron detectados correctamente.

---

# Agente 3 - Comunicador

## Resultado

El agente recibió:

* Modelo ganador.
* Métricas obtenidas.
* Resultados del entrenamiento.

Se intentó utilizar un modelo Transformer para generar el reporte automáticamente.

Durante la ejecución se produjo una incompatibilidad con la versión instalada de Transformers, por lo que el sistema activó el mecanismo de respaldo implementado.

El reporte final fue generado exitosamente mediante la plantilla automática integrada en el agente.

Archivo generado:

```text
reporte_final_churn.txt
```

---

# Flujo Multiagente Ejecutado

```text
Dataset CSV
        ↓
Agente 1 - Normalizador
        ↓
Dataset Limpio
        ↓
Agente 2 - Entrenador
        ↓
Modelo + Métricas
        ↓
Agente 3 - Comunicador
        ↓
Reporte Final
```

---

# Conclusiones

* El sistema multiagente se ejecutó correctamente.
* Los tres agentes colaboraron de forma secuencial.
* El dataset fue limpiado y transformado exitosamente.
* Se entrenaron cinco modelos de Machine Learning.
* La Regresión Logística obtuvo el mejor desempeño.
* El sistema generó automáticamente un informe final.
* La arquitectura propuesta cumple los requisitos del proyecto académico.
