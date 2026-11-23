# Pre-entrega: Análisis visual de distribuciones categóricas y outliers

## Objetivo

En esta actividad, aplicarás técnicas de ingeniería de datos para caracterizar variables en un dataset real. El objetivo es identificar la forma de las distribuciones, calcular estadísticos de tendencia central y dispersión, y detectar valores atípicos (outliers) mediante visualizaciones y métricas.

## Entregable

Un repositorio de GitHub que contenga un Jupyter Notebook con el análisis exploratorio, visualizaciones de distribución y detección de outliers.

## Criterios de entrega

- [x] El repositorio contiene un archivo `.ipynb` ejecutable y un `README.md` descriptivo.
- [x] Incluye al menos tres visualizaciones (Barplot, Boxplot y Violin Plot) generadas con Python (Pandas/Seaborn/Matplotlib).
- [x] Calcula explícitamente los valores de asimetría (Skewness) y curtosis para al menos una variable numérica.
- [x] Identifica y segmenta los outliers utilizando la técnica de IQR documentada en el código.
- [x] El código sigue buenas prácticas de nombrado de variables y comentarios explicativos.

## Pasos sugeridos

1. **Preparación del entorno:** crea un repositorio en GitHub e inicializa un Notebook de Jupyter (`.ipynb`).
2. **Carga y limpieza:** importa un dataset de tu elección (o usa el dataset de «Viviendas» o «Propinas» de Seaborn). Asegúrate de que contenga variables categóricas y numéricas.
3. **Análisis de distribución:**
   - Genera gráficos de barras para las variables categóricas principales.
   - Calcula y describe la asimetría (skewness) y la curtosis de las variables numéricas clave para entender su forma.
4. **Detección de outliers:**
   - Utiliza diagramas de caja (Boxplots) y diagramas de violín (Violin Plots) para visualizar la distribución y la presencia de valores extremos.
   - Implementa la técnica del Rango Intercuartílico (IQR) para filtrar y listar aquellos registros considerados outliers.
5. **Documentación:** en el README del repositorio, explica brevemente qué decisiones tomarías con los outliers encontrados (¿eliminarlos?, ¿transformarlos?) basándote en el análisis visual.

## Errores comunes

- Confundir la asimetría positiva (cola a la derecha) con la negativa.
- No documentar el origen de los datos en el repositorio.
