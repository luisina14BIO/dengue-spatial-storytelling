# Análisis espacial del dengue en Argentina — 2023

**Spatial analysis of dengue incidence in Argentina during 2023**

## Descripción del proyecto

Este proyecto desarrolla un análisis exploratorio y espacial de la distribución territorial del dengue en Argentina durante el año calendario 2023.

El objetivo principal es comparar la distribución de los casos absolutos con la incidencia por cada 100.000 habitantes, para identificar diferencias entre las provincias con mayor volumen de casos y aquellas con mayor carga epidemiológica relativa.

A través de herramientas de análisis de datos y visualización geoespacial, se busca transformar datos epidemiológicos y demográficos en información útil para interpretar patrones territoriales.

## Pregunta de investigación

**¿La distribución territorial de los casos de dengue refleja también dónde fue mayor la carga epidemiológica relativa?**

La pregunta se aborda mediante dos indicadores complementarios:

- **Casos absolutos:** permiten observar el volumen de casos registrados en cada provincia.
- **Incidencia por 100.000 habitantes:** permite comparar la magnitud relativa del problema entre provincias con poblaciones diferentes.

## Datos utilizados

El análisis integra tres fuentes principales:

1. **Ministerio de Salud de la Nación:** registros de vigilancia epidemiológica de dengue y zika correspondientes a las semanas epidemiológicas 1 a 52 de 2023-2024. Para este proyecto se seleccionaron los registros de dengue del año calendario 2023.
2. **INDEC:** estimaciones y proyecciones de población provincial para 2023, utilizadas como denominador para calcular la incidencia.
3. **Georef Argentina:** información geográfica de las provincias argentinas, utilizada para la representación cartográfica.

Los archivos originales se encuentran en `data/raw/` y los conjuntos de datos preparados para el análisis en `data/processed/`.

## Metodología

El trabajo se organizó en dos etapas principales:

### 1. Exploración y preparación de datos

- Lectura y exploración de los registros epidemiológicos.
- Filtrado de los casos correspondientes a dengue durante 2023.
- Evaluación de registros duplicados y valores faltantes.
- Agregación de casos por provincia.
- Integración con las estimaciones de población provincial del INDEC.
- Cálculo de la incidencia por cada 100.000 habitantes.
- Integración de los datos epidemiológicos con la información geográfica.

### 2. Análisis espacial y visualización

- Elaboración de un mapa coroplético de incidencia provincial.
- Clasificación de los valores mediante **Jenks Natural Breaks**, en cinco categorías.
- Identificación de las ocho provincias con mayor incidencia.
- Comparación de los rankings de casos absolutos e incidencia.
- Desarrollo de visualizaciones orientadas a comunicar los principales hallazgos.

La clasificación cartográfica es una herramienta estadística de representación y no constituye una categorización oficial de riesgo epidemiológico.

## Principales hallazgos

El análisis muestra que la distribución de los casos absolutos no coincide completamente con la distribución de la incidencia.

Algunos resultados destacados:

- **Tucumán** presentó el mayor número de casos absolutos, con 24.172 registros.
- **Chaco** presentó la incidencia más elevada, con 1.537,63 casos por cada 100.000 habitantes.
- **Santiago del Estero** ocupó el segundo lugar en incidencia, con 1.509,42 casos por cada 100.000 habitantes.
- Las cinco provincias con mayor incidencia fueron Chaco, Santiago del Estero, Tucumán, Formosa y Salta.
- **Buenos Aires**, a pesar de ubicarse entre las provincias con mayor cantidad de casos absolutos, presentó una incidencia considerablemente menor en comparación con las provincias del norte.

Estos resultados muestran la importancia de complementar los recuentos absolutos con indicadores relativos para comprender mejor la distribución territorial de un fenómeno epidemiológico.

## Visualizaciones

Las principales visualizaciones generadas incluyen:

- Mapa provincial de incidencia de dengue en 2023.
- Ranking de las ocho provincias con mayor incidencia.
- Comparación entre los rankings de casos absolutos e incidencia.

Las figuras se encuentran en `outputs/figures/`.

## Estructura del repositorio

```text
dengue-spatial-storytelling/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_exploracion_geoespacial.ipynb
│   └── 02_analisis_espacial_y_storytelling.ipynb
│
├── outputs/
│   └── figures/
│
├── presentation/
│
├── .gitignore
├── requirements.txt
└── README.md
```

## Tecnologías y herramientas

- **Python:** lenguaje principal de programación.
- **Pandas y NumPy:** manipulación y análisis de datos.
- **GeoPandas:** procesamiento y análisis de datos geoespaciales.
- **Matplotlib:** visualización de datos.
- **Mapclassify:** clasificación estadística para mapas coropléticos.
- **Jupyter Notebook / JupyterLab:** desarrollo y documentación del análisis.

## Limitaciones

Este trabajo tiene un alcance exploratorio y descriptivo.

- El análisis se limita al año calendario 2023 y no representa la totalidad de la temporada epidemiológica 2023-2024.
- Los registros con provincia de residencia desconocida fueron excluidos del análisis provincial.
- Se conservaron determinados registros repetidos cuando no fue posible establecer con certeza que fueran errores de carga.
- Se identificó una diferencia entre el total de registros provinciales disponibles y el total informado en el Boletín Epidemiológico Nacional. Esta discrepancia no pudo reconciliarse con la información disponible.
- La incidencia se calculó utilizando estimaciones de población provincial para 2023.
- No se incorporaron variables climáticas, ambientales, socioeconómicas ni entomológicas. Por lo tanto, los resultados no permiten establecer relaciones causales ni explicar los factores que originaron los patrones observados.

## Posibles líneas de investigación futuras

- Incorporar variables climáticas y ambientales para estudiar su relación con la distribución territorial del dengue.
- Analizar la evolución temporal de los casos por provincia y semana epidemiológica.
- Explorar indicadores socioeconómicos y demográficos asociados con la distribución de la incidencia.
- Desarrollar modelos predictivos de evolución y distribución de casos.
- Ampliar el análisis a otras temporadas epidemiológicas para identificar patrones espaciales persistentes.

## Autora

Proyecto desarrollado como parte de un trabajo práctico de Data Science II, con foco en análisis de datos epidemiológicos, visualización y storytelling geoespacial.
