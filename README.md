# Big Data para Negocios: Inventario de productos (Online Retail)

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GoldenDiegos/big-data-inventario-productos-online-retail/blob/main/notebooks/analisis_online_retail.ipynb)

- **Equipo 2:** Héctor Oropeza, Diego Lara, Jorge Alvarez
- **Materia:** Big Data para Negocios
- **Profesor:** Abel Soto

Análisis estadístico descriptivo de las ventas de una tienda en línea de artículos de regalo con sede en Reino Unido, entre el 1 de diciembre de 2010 y el 9 de diciembre de 2011. Después de la limpieza se analizan 519,231 líneas de venta de 3,790 productos distintos.

## Conjunto de datos

En Kaggle aparece como "Supermarket Dataset" (archivo `supermarket_data.csv`):
https://www.kaggle.com/datasets/saurabhbadole/supermarket-data

Aunque el nombre dice supermercado, el contenido es la hoja "Year 2010-2011" del conjunto Online Retail II de UCI, con las mismas columnas y las mismas 541,910 filas. En este repositorio el archivo se guardó sin cambios como `data/raw/online_retail.csv`. Los datos originales se publican en UCI con licencia CC BY 4.0, que permite compartirlos citando la fuente.

## Requisitos del proyecto

| Requisito | Dónde se cumple |
|---|---|
| Conjunto de datos de Kaggle con más de 150 productos | 3,790 productos distintos después de la limpieza |
| Estadística descriptiva en Python: media, mediana, moda, rango intercuartílico, varianza y desviación estándar | Sección 4 del notebook y `outputs/tables/descriptive_stats.csv` |
| Covarianza y correlación (opcional) | Sección 4 del notebook, con Pearson y Spearman |
| Al menos 5 gráficas | El notebook genera 10 (sección 5 y `outputs/figures/`) |
| Conclusiones | Sección 6 del notebook y apartado 6 del documento de Word |

## Entregables

| Entregable | Archivo |
|---|---|
| Código | `notebooks/analisis_online_retail.ipynb` |
| Documento de resultados | `deliverables/Equipo2_Inventario_Resultados.docx` |
| PDF con capturas de la ejecución | `deliverables/Equipo2_Capturas_Ejecucion.pdf` (25 capturas en orden, con su etiqueta; las imágenes sueltas están en `screenshots/`) |

## Contenido del notebook

1. Carga y verificación de los datos
2. Limpieza de datos, con bitácora de 10 pasos
3. Variable calculada y verificación del conjunto limpio
4. Estadística descriptiva: media, mediana, moda, cuartiles, rango intercuartílico, varianza, desviación estándar, covarianza y correlación
5. Visualización de datos (10 gráficas)
6. Conclusiones
7. Validación final de resultados

## Gráficas

| Figura | Archivo | Qué muestra |
|---|---|---|
| 1 | `fig01_histograma_quantity.png` | Histograma de unidades por línea de venta |
| 2 | `fig02_densidad_price.png` | Histograma y curva de densidad del precio unitario |
| 3 | `fig03_densidad_total.png` | Curva de densidad del importe por línea, en escala logarítmica |
| 4 | `fig04_boxplots.png` | Diagramas de caja de Quantity, Price y Total |
| 5 | `fig05_dispersion_unidades_ingreso.png` | Unidades vendidas frente a ingreso por producto |
| 6 | `fig06_ingreso_mensual.png` | Ingreso mensual |
| 7 | `fig07_top10_productos.png` | Diez productos con mayor ingreso |
| 8 | `fig08_ingreso_por_pais.png` | Diez países con mayor ingreso, sin contar al Reino Unido |
| 9 | `fig09_correlacion_productos.png` | Mapa de calor de la correlación de Spearman por producto |
| 10 | `fig10_pareto_ingreso.png` | Curva de concentración del ingreso (Pareto) |

## Principales resultados

| Concepto | Valor |
|---|---|
| Líneas de venta después de la limpieza | 519,231 (95.81 % del original) |
| Productos distintos | 3,790 |
| Ingreso total | £9,798,951.95 |
| Venta típica (medianas) | 4 unidades, £2.08 por unidad, £9.90 por línea |
| Productos que generan el 80 % del ingreso | 834 (22.0 %) |
| Mes con mayor ingreso | Noviembre de 2011, £1,438,321 |
| Participación del Reino Unido en el ingreso | 84.80 % |

## Abrir en Google Colab

Abrir con el botón de Colab de arriba y en el menú Entorno de ejecución elegir Ejecutar todas.

- La primera celda descarga el conjunto de datos de Kaggle, sin necesidad de cuenta. Si Kaggle no responde, usa la copia de `data/raw/` de este repositorio.
- La segunda celda verifica con su huella SHA-256 que el archivo sea idéntico al original.
- La última celda comprueba que las cifras del análisis sean las esperadas.
- Colab usa sus propias versiones de las librerías, no las de `requirements.txt`. El notebook da las mismas cifras con pandas 2.2 y con pandas 3.0.
- Las tablas y gráficas que se generan en Colab se borran al cerrar la sesión. Las versiones finales ya están en `outputs/`.

## Ejecutar en una computadora

Requiere Python 3.12 o superior.

```
git clone https://github.com/GoldenDiegos/big-data-inventario-productos-online-retail.git
cd big-data-inventario-productos-online-retail
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe -m jupyter notebook notebooks
```

Abrir `analisis_online_retail.ipynb` y ejecutar todas las celdas en orden (Kernel, Restart Kernel and Run All Cells). La ejecución completa tarda unos 20 segundos. En macOS o Linux, usar `.venv/bin/python` en lugar de `.venv\Scripts\python.exe`.

## Estructura del repositorio

| Carpeta | Contenido |
|---|---|
| `data/raw/` | Archivo original de Kaggle (`supermarket_data.csv`, renombrado). No se modifica. |
| `data/processed/` | Datos después de la limpieza. Los genera el notebook y no se suben al repositorio. |
| `notebooks/` | Notebook con todo el análisis. |
| `outputs/tables/` | Tablas de resultados en CSV. |
| `outputs/figures/` | Gráficas en PNG a 300 dpi. |
| `deliverables/` | Documento de resultados en Word y PDF con las capturas de la ejecución. |
| `screenshots/` | Guía y capturas de la ejecución del notebook. |

## Verificación del archivo original

SHA-256 de `data/raw/online_retail.csv`:

```
cb304b33513787ba84fc0e7d38b21f49279f6817e48f99d6d3cc3a849cc436ca
```

## Referencias

- Badole, S. (2024). Supermarket Dataset [Conjunto de datos]. Kaggle. https://www.kaggle.com/datasets/saurabhbadole/supermarket-data
- Chen, D. (2019). Online Retail II [Conjunto de datos]. UCI Machine Learning Repository. https://doi.org/10.24432/C5CG6D
