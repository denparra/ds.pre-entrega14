# Pre-entrega M14: distribución de ventas y valores atípicos

| Campo | Detalle |
|---|---|
| Autor único | Dennys Parra |
| Curso | Data Science II — Machine Learning, Coderhouse |
| Entrega | Pre-entrega del módulo 14 |

Este trabajo analiza la distribución de ventas (`Sales`) por categoría en el conjunto Sample Superstore. Presenta estadísticas descriptivas, tres visualizaciones y una detección de valores atípicos mediante el rango intercuartílico (IQR).

## Ver el resultado sin instalar dependencias

Abre [el informe en PDF](Informe_pre-entrega_M14.pdf) para consultar el objetivo, los gráficos, los principales resultados y la interpretación. Es una versión estática del análisis: no requiere Python, Jupyter ni la instalación de paquetes.

Para revisar o reproducir el análisis, abre [el notebook](pre-entregamd14.ipynb).

## Datos y método

Se utiliza una copia local del conjunto limpio Sample Superstore, reutilizado en la entrega del módulo 11. Cada fila representa una línea de pedido. El archivo contiene 9.994 filas y 21 columnas, sin valores faltantes; la fuente original no se modifica.

El análisis incluye:

- Un gráfico de barras con la cantidad de líneas de pedido por categoría.
- Un boxplot y un violin plot para comparar la distribución de `Sales` entre categorías.
- Media, mediana, asimetría y curtosis de `Sales`.
- Límites IQR calculados por separado para cada categoría, con las filas marcadas exportadas a `outputs/outliers_sales_iqr.csv` al ejecutar el notebook.

## Resultados de referencia

`Sales` tiene una media de **229,8580**, una mediana de **54,4900**, una asimetría de **12,9728** y una curtosis de exceso de **305,3118**. La media mayor que la mediana y la asimetría positiva son coherentes con una cola de ventas altas. La curtosis reportada por pandas es de exceso: cero es la referencia de una distribución normal.

| Categoría | Filas marcadas | Total de filas | Porcentaje |
|---|---:|---:|---:|
| Furniture | 164 | 2.121 | 7,73 % |
| Office Supplies | 815 | 6.026 | 13,52 % |
| Technology | 172 | 1.847 | 9,31 % |
| **Total** | **1.151** | **9.994** | **11,52 %** |

## Decisión sobre los valores marcados

Una marca IQR señala un valor alejado del rango central; no demuestra que sea un error. Por eso, las filas se conservan. Antes de corregir o eliminar una, se debe revisar su origen y contexto. Si un modelo es sensible a los extremos, se puede comparar `log1p` —cuando las ventas no son negativas— con los resultados en la escala original. Solo se corregirían o excluirían registros si existe evidencia independiente de un problema.

## Reproducir el análisis

Se requiere Python 3.10 o superior. Ejecuta estos comandos desde esta carpeta:

```bash
python -m venv .venv
```

Activa el entorno en Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

En macOS o Linux:

```bash
source .venv/bin/activate
```

Instala las dependencias y abre el notebook:

```bash
python -m pip install -r requirements.txt
jupyter lab pre-entregamd14.ipynb
```

Ejecuta las celdas en orden. El notebook lee `data/dashboard_ventas.csv` y guarda el resultado en `outputs/outliers_sales_iqr.csv`. JupyterLab debe iniciarse desde esta carpeta para que funcionen las rutas relativas. Las versiones comprobadas fueron Python 3.13.9, pandas 2.2.3 y matplotlib 3.10.6; `requirements.txt` declara rangos compatibles, no un bloqueo exacto.

## Archivos de la entrega

| Archivo | Contenido |
|---|---|
| [`Informe_pre-entrega_M14.pdf`](Informe_pre-entrega_M14.pdf) | Informe estático para lectura sin instalar dependencias |
| [`pre-entregamd14.ipynb`](pre-entregamd14.ipynb) | Análisis ejecutable, tablas y visualizaciones |
| [`data/dashboard_ventas.csv`](data/dashboard_ventas.csv) | Copia local de los datos utilizados |
| [`requirements.txt`](requirements.txt) | Dependencias para ejecutar el notebook |
| [`pre-entregamd14.md`](pre-entregamd14.md) | Consigna de la actividad |
