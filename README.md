# Big Data para Negocios: Inventario de productos (Online Retail)

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GoldenDiegos/big-data-inventario-productos-online-retail/blob/main/notebooks/analisis_online_retail.ipynb)

- **Equipo 2:** Héctor Oropeza, Diego Lara, Jorge Alvarez
- **Materia:** Big Data para Negocios
- **Profesor:** Abel Soto

Análisis estadístico descriptivo de las ventas de una tienda en línea de artículos de regalo con sede en Reino Unido, entre el 1 de diciembre de 2010 y el 9 de diciembre de 2011. Después de la limpieza se analizan 519,231 líneas de venta de 3,790 productos distintos.

**Conjunto de datos:** Online Retail, publicado en Kaggle con el archivo `supermarket_data.csv`
https://www.kaggle.com/datasets/saurabhbadole/supermarket-data

## Contenido del notebook

1. Carga y verificación de los datos
2. Limpieza de datos, con bitácora de 10 pasos
3. Variable calculada y verificación del conjunto limpio
4. Estadística descriptiva: media, mediana, moda, cuartiles, rango intercuartílico, varianza, desviación estándar, covarianza y correlación
5. Visualización de datos (10 gráficas)
6. Conclusiones
7. Validación final de resultados

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

Usar el botón "Open in Colab" de arriba y ejecutar Entorno de ejecución, Ejecutar todas.

- La primera celda descarga el conjunto de datos de Kaggle. Si Kaggle no responde, usa la copia de `data/raw/` de este repositorio.
- La segunda celda verifica con su huella SHA-256 que el archivo sea idéntico al original.
- La última celda comprueba que las cifras del análisis sean las esperadas.

## Ejecutar en una computadora

Requiere Python 3.12 o superior.

```
git clone https://github.com/GoldenDiegos/big-data-inventario-productos-online-retail.git
cd big-data-inventario-productos-online-retail
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe -m jupyter notebook notebooks
```

Abrir `analisis_online_retail.ipynb` y ejecutar todas las celdas en orden (Kernel, Restart and Run All). En macOS o Linux, usar `.venv/bin/python` en lugar de `.venv\Scripts\python.exe`.

## Estructura del repositorio

| Carpeta | Contenido |
|---|---|
| `data/raw/` | Archivo original descargado de Kaggle. No se modifica. |
| `data/processed/` | Datos después de la limpieza. Los genera el notebook y no se suben al repositorio. |
| `notebooks/` | Notebook con todo el análisis. |
| `outputs/tables/` | Tablas de resultados en CSV. |
| `outputs/figures/` | Gráficas en PNG a 300 dpi. |
| `deliverables/` | Documento de resultados en Word. |
| `screenshots/` | Guía y capturas de la ejecución del notebook. |

## Verificación del archivo original

SHA-256 de `data/raw/online_retail.csv`:

```
cb304b33513787ba84fc0e7d38b21f49279f6817e48f99d6d3cc3a849cc436ca
```

El notebook se probó con Python 3.14 (pandas 3.0) y con Python 3.12 (pandas 2.2, matplotlib 3.9), y en ambos casos produce exactamente los mismos resultados.

## Referencias

- Badole, S. (s. f.). Supermarket data [Conjunto de datos]. Kaggle. https://www.kaggle.com/datasets/saurabhbadole/supermarket-data
- Chen, D. (2015). Online Retail [Conjunto de datos]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
