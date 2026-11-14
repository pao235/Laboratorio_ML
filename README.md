# Laboratorio de IA · Regresión, Clasificación y Clustering con Machine Learning

**Tres modelos de ML desarrollados en Google Colab**
Tarea 3 · Inteligencia Artificial · ITCH · Semestre enero–junio 2026

![Plataforma](https://img.shields.io/badge/Plataforma-Google%20Colab-orange)
![Lenguaje](https://img.shields.io/badge/Lenguaje-Python-blue)
![Framework](https://img.shields.io/badge/Framework-TensorFlow%2FKeras-red)
![Estado](https://img.shields.io/badge/Estado-Completado-brightgreen)

---

## Descripción

Este repositorio reúne tres cuadernos de Jupyter (`.ipynb`) que aplican la metodología de diseño de sistemas de IA basados en Machine Learning: **datos → modelo → prueba → inferencia**. Cada cuaderno resuelve un tipo de problema distinto: regresión, clasificación y clustering.

---

## Contenido

| Cuaderno | Problema | Técnica | Abrir en Colab |
|----------|----------|---------|----------------|
| `01_Regresion.ipynb` | Eliminar ruido de una señal coseno | Red `SimpleRNN` | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pao235/NOMBRE_REPO/blob/main/01_Regresion.ipynb) |
| `02_Clasificacion.ipynb` | Clasificar prendas de vestir | Red `Dense` | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pao235/NOMBRE_REPO/blob/main/02_Clasificacion.ipynb) |
| `03_Clustering.ipynb` | Predecir el aula de una medición | K-Means y Fuzzy C-Means | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pao235/NOMBRE_REPO/blob/main/03_Clustering.ipynb) |

---

## 1. Modelo de regresión: eliminación de ruido

**Objetivo:** generar un modelo que elimine el ruido de una señal sinusoidal.

- **Datos:** la entrada `x(t)` es una señal coseno con ruido aditivo gaussiano; la señal objetivo `o(t)` es el mismo coseno sin ruido.
- **Modelo:** red `SimpleRNN`. Se varió la cantidad de neuronas para encontrar el mejor desempeño posible.
- **Prueba e inferencia:** el modelo corre en tiempo real durante 2,500 iteraciones. En las primeras 1,500 se entrena con `o(t)`; en las restantes solo genera su salida `y(t)` a partir de `x(t)`.
- **Métricas:** MSE y MAE.

---

## 2. Modelo de clasificación: Fashion-MNIST

**Objetivo:** clasificar imágenes de prendas de vestir.

- **Dataset:** [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist), con 70,000 imágenes en escala de grises de 28×28 px, divididas en 60,000 para entrenamiento y 10,000 para prueba. Tiene 10 clases perfectamente balanceadas.
- **Preprocesamiento:** descarga en Colab, normalización de las muestras y visualización de 10 ejemplos.
- **Modelo:** red de capas `Dense`, con la cantidad de neuronas ajustada hasta obtener el mejor desempeño. Compilada con optimizador **Adam**, pérdida **entropía cruzada categórica** y métrica **accuracy**.
- **Evaluación:** accuracy y loss sobre el conjunto de prueba, y **matriz de confusión** para analizar el comportamiento del modelo por clase.

---

## 3. Modelo de clustering: aulas

**Objetivo:** determinar si un análisis categórico puede predecir el aula donde se tomaron las mediciones.

- **Dataset:** `Aula.csv`, con mediciones de tres puntos en tres aulas.
- **Preprocesamiento:** visualización de los datos en 3D y normalización con `StandardScaler`.
- **Modelos:** **K-Means** y **Fuzzy C-Means**.
- **Evaluación:** gráficas 3D y coeficiente de **silueta** para K-Means, Fuzzy C-Means y la información original, para determinar qué resultado se asemeja más a la agrupación real.

---

## Estructura del repositorio

```
├── 01_Regresion.ipynb
├── 02_Clasificacion.ipynb
├── 03_Clustering.ipynb
├── Aula.csv
└── README.md
```

---

## Cómo ejecutarlo

1. Haz clic en el botón **Open in Colab** del cuaderno que quieras.
2. Ejecuta **Entorno de ejecución → Ejecutar todo**.
3. En el cuaderno de clustering, sube `Aula.csv` al entorno de Colab (o móntalo desde Drive) antes de ejecutarlo.

Las librerías principales son TensorFlow/Keras, NumPy, Matplotlib, scikit-learn y scikit-fuzzy, que Colab ya incluye o se instalan desde el propio cuaderno.

---

## Autor

**Ana Paola Cardona Valenzuela** · Inteligencia Artificial · ITCH · Semestre 8

## Licencia

Uso académico.