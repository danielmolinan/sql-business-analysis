# SQL Business Analysis

Repositorio de análisis de negocio realizados con SQL, combinando consultas técnicas con interpretación orientada a la toma de decisiones. Los casos están basados en datasets reales utilizados durante el **Máster en Data Science, Big Data & Business Analytics** en la Universidad Complutense de Madrid. Los datos pueden ser descargados desde el siguiente enlace:

[💾Datasets](https://drive.google.com/drive/folders/16X_SxwOKAlhnYZBA5g1B-MgfmGd2zSeE?usp=sharing)

---

##  Casos de análisis

### [Smart Desk — Análisis de Ventas Globales (2019–2021)](./smart-desk-case/)

**Contexto:** Smart Desk es una empresa con presencia en cuatro regiones globales (NAM, EMEA, APAC y LATAM). El análisis abarca el período 2019–2021, coincidiendo con el impacto del COVID-19 en la economía mundial, y busca responder una pregunta de negocio concreta:

> *¿Qué región tuvo el mejor y peor desempeño en ventas y beneficios entre 2019 y 2021, y qué factores lo explican?*

**Base de datos:** Snowflake · Schema `SMART_DESK` · Tablas: `SALES`, `ACCOUNTS`, `FORECASTS`

**Análisis realizados:**

| # | Análisis | Técnicas SQL utilizadas |
|---|----------|------------------------|
| 1 | Ventas y beneficio por categoría de producto (cuenta Adabs Entertainment, 2020) | `WHERE`, `TO_VARCHAR`, formateo numérico |
| 2 | Comparación de rendimiento por país en regiones APAC y EMEA | `INNER JOIN`, `GROUP BY`, `AVG`, `ORDER BY` |
| 3 | Beneficio por industria en clientes en etapa de compromiso | `INNER JOIN` múltiple, subconsulta con `IN`, `CASE WHEN`, `SUM` |
| 4 | Evolución del pronóstico vs. beneficio real por categoría | `FULL OUTER JOIN`, `COALESCE`, `MIN`/`MAX` |
| 5 | Análisis exploratorio libre: desempeño regional durante el COVID-19 | `INFORMATION_SCHEMA`, `CASE WHEN`, `COUNT DISTINCT`, análisis multidimensional |

**Principales hallazgos:**
- NAM (Estados Unidos) lideró las ventas históricas con ~$98M, seguida de cerca por EMEA con ~$97M, mientras que LATAM quedó muy rezagada con ~$7M.
- A pesar del COVID-19, las ventas globales de Smart Desk crecieron año a año: +28% entre 2019 y 2020, y +31% entre 2020 y 2021.
- APAC mostró un comportamiento anómalo: triplicó sus ventas entre 2019 y 2020, pero las redujo un 36% en 2021 — el único caso de retroceso en ese año.
- NAM redujo sus ventas en 2020 (el único año afectado por la pandemia) pero las duplicó en 2021, alcanzando ~$44M.
- Singapur generó más ingresos promedio que Alemania a pesar de tener una población 13 veces menor.

**Recomendaciones derivadas del análisis:**
- Diversificar mercados en LATAM (Brasil, Colombia, Chile) para reducir la dependencia de Argentina y México.
- Investigar el retroceso de APAC en 2021, especialmente la ausencia de Singapur tras su excepcional rendimiento en 2020.
- Evaluar la incorporación de Canadá a la región NAM para reducir la dependencia de un único mercado.
- Estudiar los factores que permitieron a Francia, España, Australia y Singapur crecer en 2020 para replicarlos en mercados más débiles.

---

## Técnicas SQL demostradas

- Joins: `INNER JOIN`, `FULL OUTER JOIN`
- Agregaciones: `SUM`, `AVG`, `COUNT DISTINCT`, `MIN`, `MAX`, `ROUND`
- Lógica condicional: `CASE WHEN`, `COALESCE`
- Subconsultas correlacionadas con `IN`
- Exploración de schema con `INFORMATION_SCHEMA.COLUMNS`
- Formateo de salida con `TO_VARCHAR` y máscaras numéricas
- Ordenación y filtrado multidimensional

**Plataforma:** Snowflake (compatible con SQL estándar)

---

## Estructura del repositorio

```
sql-business-analysis/
│
└── smart-desk-case/
    ├── smart_desk_analysis.sql   # Consultas completas con comentarios
    └── smart_desk_report.pdf     # Análisis e interpretación de resultados
```

---

## Autor

**Daniel Molina Novoa** · Data Analyst  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/daniel-molina-novoa/)
[![GitHub](https://img.shields.io/badge/GitHub-danielmolinan-181717?style=flat&logo=github&logoColor=white)](https://github.com/danielmolinan)
