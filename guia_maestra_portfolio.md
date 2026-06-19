🎯 GUÍA MAESTRA: Bellabeat Case Study — Portfolio Profesional

Proyecto end-to-end de Data Analytics | Stack: SQL + Python + Power BI

**Nivel:** Junior → Profesional
**Duración:** 20 días (4 semanas)
**Stack:** SQLite/SQL + Python (pandas/matplotlib/seaborn) + Power BI (DAX + Modelo Estrella)
**Idioma:** Español (entregables) / Inglés (README GitHub opcional)
**Dataset:** Fitbit Fitness Tracker Data (Kaggle)

📑 ÍNDICE DE DOCUMENTOS DEL PORTFOLIO

| # | Documento | Descripción | Peso |
| --- | --- | --- | --- |
| 1 | bellabeat_portfolio_guia_maestra.md | **Este documento.** Plan día a día, storytelling, mockups, arquitectura | Maestro |
| 2 | bellabeat_portfolio_sql_scripts.md | Scripts SQL completos: limpieza, ETL, modelo estrella | Técnico |
| 3 | bellabeat_portfolio_dax_medidas.md | Medidas DAX, KPIs, columnas calculadas, formato condicional | Técnico |
| 4 | bellabeat_portfolio_readme_github.md | README profesional para repositorio público | Comunicación |
| 5 | bellabeat_portfolio_linkedin_post.md | Publicación optimizada para LinkedIn | Comunicación |
| 6 | bellabeat_portfolio_presentacion_guion.md | Guion de 10 diapositivas con storytelling de 3 actos | Storytelling |

🏗️ ARQUITECTURA DEL PROYECTO

Stack tecnológico visual

┌─────────────────────────────────────────────────────────────┐
│  CAPA 1: EXTRACCIÓN (Kaggle)                                │
│  • dailyActivity_merged.csv                                 │
│  • sleepDay_merged.csv                                      │
│  • hourlySteps_merged.csv                                   │
│  • hourlyCalories_merged.csv                                │
│  • weightLogInfo_merged.csv                                 │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  CAPA 2: TRANSFORMACIÓN (SQL + Python)                      │
│  • SQL: limpieza, deduplicación, joins, normalización       │
│  • Python: feature engineering, EDA, outliers, segmentación   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  CAPA 3: MODELADO (Power BI — Modelo Estrella)              │
│  • Tabla de Hechos: `fact_actividad_sueño`                  │
│  • Dimensiones: `dim_usuario`, `dim_tiempo`, `dim_categoria`│
│  • Medidas DAX: 15+ KPIs calculados                         │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  CAPA 4: VISUALIZACIÓN (Dashboard + Presentación)           │
│  • Dashboard interactivo de 1 página (Power BI)             │
│  • Presentación ejecutiva de 10 diapositivas              │
│  • Narrativa: "Del dato a la decisión de negocio"           │
└─────────────────────────────────────────────────────────────┘

Estructura de carpetas del repositorio GitHub

📁 bellabeat-data-analysis/
├── 📁 .github/
│   └── workflows/ (opcional: CI para tests de datos)
├── 📁 data/
│   ├── 📁 01_raw/
│   │   ├── dailyActivity_merged.csv
│   │   ├── sleepDay_merged.csv
│   │   ├── hourlySteps_merged.csv
│   │   ├── hourlyCalories_merged.csv
│   │   └── weightLogInfo_merged.csv
│   ├── 📁 02_processed/
│   │   ├── fact_actividad_sueño.csv
│   │   ├── dim_usuario.csv
│   │   ├── dim_tiempo.csv
│   │   └── dim_categoria_actividad.csv
│   └── 📁 03_analysis/
│       ├── eda_correlaciones.ipynb
│       ├── segmentacion_usuarios.ipynb
│       └── informe_estadistico.pdf
├── 📁 sql/
│   ├── 01_limpieza_dedup.sql
│   ├── 02_feature_engineering.sql
│   ├── 03_creacion_modelo_estrella.sql
│   └── 04_vistas_analiticas.sql
├── 📁 powerbi/
│   ├── bellabeat_dashboard.pbix
│   ├── 📁 dax_measures/
│   │   └── medidas_calculadas.dax
│   └── 📁 docs/
│       ├── modelo_estrella.png
│       └── guia_uso.md
├── 📁 docs/
│   ├── presentacion_ejecutiva.pdf
│   ├── mockup_dashboard.png
│   └── storytelling.md
├── 📁 assets/
│   ├── logo_bellabeat.png
│   └── paleta_colores.json
├── README.md
├── requirements.txt
└── .gitignore

📅 PLAN DÍA A DÍA (20 Días)

SEMANA 1: FUNDAMENTOS Y PREPARACIÓN

Día 1 — Preguntar (Ask)

- ☐ Leer el caso Bellabeat completo (Google Data Analytics Capstone)

- ☐ Identificar stakeholders y sus intereses

- ☐ Escribir la declaración del problema en 1 párrafo

- ☐ Formular 5 preguntas SMART de análisis

- ☐ **Entregable:** Documento 01_declaracion_problema.md

Día 2 — Preparar (Prepare)

- ☐ Descargar dataset de Kaggle (18 archivos CSV)

- ☐ Crear diccionario de datos propio (columna, tipo, descripción, unidad)

- ☐ Evaluar ROCCC (Reliable, Original, Comprehensive, Current, Cited)

- ☐ Documentar limitaciones: muestra 30 usuarios, sin género, datos 2016

- ☐ **Entregable:** 02_diccionario_datos.md + 03_limitaciones.md

Día 3 — Inspección inicial (Python)

- ☐ Cargar archivos principales en Jupyter Notebook

- ☐ Usar df.info(), df.describe(), df.isnull().sum()

- ☐ Identificar duplicados en sleepDay_merged (3 registros)

- ☐ Detectar outliers con boxplots (pasos > 30.000, calorías < 500)

- ☐ **Entregable:** Notebook 04_inspeccion_inicial.ipynb

Día 4 — Limpieza con SQL (Parte I)

- ☐ Crear base de datos SQLite: bellabeat.db

- ☐ Importar CSVs como tablas staging: stg_daily_activity, stg_sleep

- ☐ Ejecutar deduplicación: ROW_NUMBER() OVER (PARTITION BY Id, SleepDay)

- ☐ Estandarizar fechas: DATE(ActivityDate) y DATE(SleepDay)

- ☐ **Entregable:** Script 05_limpieza_sql.sql + base de datos limpia

Día 5 — Limpieza con SQL (Parte II)

- ☐ Validar rangos: pasos ≥ 0, sedentary ≤ 1440, sueño ≤ 1440

- ☐ Manejar nulos: excluir columna Fat de weightLogInfo (65% nulos)

- ☐ Crear vista limpia: v_daily_activity_clean, v_sleep_clean

- ☐ **Entregable:** Script 06_validacion_sql.sql

SEMANA 2: PROCESAMIENTO Y MODELADO

Día 6 — Feature Engineering (SQL)

- ☐ Crear DayOfWeek, IsWeekend, WeekNumber

- ☐ Calcular ActiveMinutes = VeryActive + FairlyActive

- ☐ Calcular SleepEfficiency = TotalMinutesAsleep / TotalTimeInBed

- ☐ Calcular SedentaryPercentage = SedentaryMinutes / 1440

- ☐ Categorizar usuarios: Sedentario, Ligeramente Activo, Moderado, Muy Activo

- ☐ **Entregable:** Script 07_feature_engineering.sql

Día 7 — Feature Engineering (Python)

- ☐ Cargar datos limpios desde SQLite

- ☐ Crear UserCategory con pd.cut() basado en promedio de pasos

- ☐ Calcular adherencia: días de uso / 31 días por usuario

- ☐ Crear lag features: actividad del día anterior vs sueño de hoy

- ☐ **Entregable:** Notebook 08_feature_engineering.ipynb

Día 8 — Modelo Estrella (SQL)

- ☐ Diseñar esquema en estrella:

- **Hechos:** fact_actividad_sueño (granularidad: 1 fila = 1 día × 1 usuario)

- **Dimensiones:** dim_usuario, dim_tiempo, dim_categoria

- ☐ Crear tablas dimensionales con claves surrogadas

- ☐ Poblar fact_actividad_sueño con JOIN de actividad + sueño + categoría

- ☐ **Entregable:** Script 09_modelo_estrella.sql + diagrama ER

Día 9 — EDA con Python (Parte I — Descriptivo)

- ☐ Estadísticas descriptivas: media, mediana, std, percentiles 25/75

- ☐ Distribución de pasos, calorías, sueño (histogramas + KDE)

- ☐ Análisis por día de semana: groupby + barplots

- ☐ **Entregable:** Notebook 10_eda_descriptivo.ipynb

Día 10 — EDA con Python (Parte II — Diagnóstico)

- ☐ Matriz de correlaciones (heatmap con seaborn)

- ☐ Scatter plots: pasos vs sueño, actividad vs sedentarismo

- ☐ Boxplots: fin de semana vs entre semana

- ☐ Test t de Student para comparar medias

- ☐ **Entregable:** Notebook 11_eda_diagnostico.ipynb

SEMANA 3: POWER BI Y DASHBOARD

Día 11 — Importar a Power BI

- ☐ Conectar Power BI a bellabeat.db (SQLite) o importar CSVs procesados

- ☐ Verificar tipos de datos en Power Query (fechas como Date, Id como Texto)

- ☐ Crear relaciones en modelo estrella (1:N correctas)

- ☐ **Entregable:** Archivo .pbix base con modelo cargado

Día 12 — Medidas DAX (KPIs Principales)

- ☐ Crear medidas calculadas: pasos promedio, calorías promedio, sueño promedio

- ☐ Medidas de adherencia: % días con registro, % usuarios con sueño

- ☐ Medidas de cumplimiento OMS: % días con ≥ 21 min activos (150/7)

- ☐ **Entregable:** 12_dax_kpis_principales.dax (ver documento separado)

Día 13 — Medidas DAX (Avanzadas)

- ☐ Medidas de inteligencia temporal: promedio vs mes anterior, acumulado semanal

- ☐ Segmentación dinámica: RANKX de usuarios por actividad

- ☐ Formato condicional: semáforos para metas de pasos y sueño

- ☐ **Entregable:** 13_dax_avanzado.dax

Día 14 — Diseño del Dashboard (Mockup → Realidad)

- ☐ Crear wireframe en papel o Figma (ver sección Mockups más abajo)

- ☐ Implementar en Power BI: fondo oscuro, tipografía clean, paleta Bellabeat

- ☐ Paleta recomendada: #2E7D32 (verde salud), #FF6F00 (naranja energía), #37474F (gris oscuro), #FFFFFF (blanco)

- ☐ **Entregable:** Dashboard v1.0 en .pbix

Día 15 — Interactividad y UX

- ☐ Añadir slicers: usuario, categoría, día de semana, rango de fechas

- ☐ Crear tooltips informativos con medidas adicionales

- ☐ Configurar drill-through: de resumen a detalle por usuario

- ☐ Añadir botones de navegación y bookmarks

- ☐ **Entregable:** Dashboard v1.1 interactivo

SEMANA 4: STORYTELLING Y ENTREGA

Día 16 — Storytelling de 3 Actos

- ☐ **Acto I (Setup):** Contexto Bellabeat, problema, dataset, metodología

- ☐ **Acto II (Confrontación):** 3 hallazgos sorprendentes con datos

- ☐ **Acto III (Resolución):** 4 recomendaciones accionables para marketing

- ☐ Escribir guion narrativo de 5 minutos de presentación

- ☐ **Entregable:** 14_storytelling.md (ver documento separado)

Día 17 — Presentación Ejecutiva (10 diapositivas)

- ☐ Diapositiva 1: Título + hook

- ☐ Diapositiva 2: Resumen ejecutivo (3 bullets)

- ☐ Diapositiva 3: Metodología + limitaciones

- ☐ Diapositivas 4-7: Hallazgos con gráficos exportados de Power BI

- ☐ Diapositiva 8: Recomendaciones estratégicas

- ☐ Diapositiva 9: Próximos pasos / ROI esperado

- ☐ Diapositiva 10: Preguntas

- ☐ **Entregable:** presentacion_ejecutiva.pptx (o Google Slides)

Día 18 — README profesional para GitHub

- ☐ Redactar README con badges, estructura, instalación, resultados

- ☐ Incluir screenshots del dashboard y snippets de código

- ☐ Añadir sección “What I learned” y “Future improvements”

- ☐ **Entregable:** README.md (ver documento separado)

Día 19 — Publicación de LinkedIn

- ☐ Redactar post con hook, proceso, resultado, llamada a la acción

- ☐ Incluir 3-5 hashtags optimizados (#DataAnalytics #PowerBI #Portfolio)

- ☐ Preparar imagen de portada: screenshot del dashboard + título

- ☐ **Entregable:** 15_linkedin_post.md (ver documento separado)

Día 20 — Revisión final y publicación

- ☐ Revisar coherencia entre datos, análisis y recomendaciones

- ☐ Validar que todos los links funcionan (Kaggle, repositorio)

- ☐ Subir a GitHub con commits descriptivos

- ☐ Publicar en LinkedIn con link al repositorio

- ☐ **Entregable:** Portfolio público y visible ✅

🎭 STORYTELLING DE 3 ACTOS

ACTO I: El Setup (Contexto y Problema)

*“**Bellabeat es una empresa de wellness femenino que factura millones, pero compite contra gigantes como Apple y Fitbit. Urška Sršen, su cofundadora, necesita saber: ¿qué hacen realmente los usuarios con sus wearables? No basta con vender dispositivos; hay que vender hábitos.**”*

**Elementos clave:** - Presentar a Bellabeat como protagonista (empresa con misión, no solo producto) - El dataset Fitbit como “ventana al comportamiento del consumidor” - Tu rol: el analista que traduce datos en oportunidades de negocio

ACTO II: La Confrontación (Hallazgos con impacto emocional)

*“**Lo que descubrimos desafía la intuición. No todos los usuarios son** **‘**fitness addicts**’**. De hecho, el 40% apenas camina 5.000 pasos al día. Pero hay algo más sorprendente: los días que más caminan, duermen mejor. Y los domingos… casi nadie se mueve.**”*

**3 hallazgos con gancho narrativo:** 1. **“****El domingo negro****”** — Los usuarios reducen su actividad un 35% los domingos. Es el día de mayor sedentarismo. 2. **“****El ciclo del bienestar****”** — Correlación positiva entre pasos y minutos de sueño profundo. No es solo fitness; es salud integral. 3. **“****La mitad invisible****”** — El 50% de los usuarios no registra su sueño. No es que no duerman; es que no interactúan con la función.

ACTO III: La Resolución (Recomendaciones accionables)

*“**Estos datos no son números en una pantalla. Son oportunidades de marketing. Si sabemos que el domingo es el día débil, enviemos una notificación el sábado por la noche:** **‘**Mañana es tu día de descanso activo**’**. Si sabemos que el sueño mejora con la actividad, mostrémoslo en la app:** **‘**Hoy caminaste 8.000 pasos. Tu sueño mejorará un 15%**’**.**”*

**4 recomendaciones con ROI implícito:** 1. **Campaña**** ****“****Domingo Activo****”** — Push notifications + email marketing con retos ligeros para domingo (yoga, caminata). *Impacto esperado: +20% engagement dominical.* 2. **Feature**** ****“****Ciclo de Bienestar****”** — Dashboard en app que conecte actividad de hoy con predicción de sueño de mañana. *Impacto: +15% retención de usuarias.* 3. **Gamificación de sueño** — Badge “Reina del descanso” por 7 noches registradas. *Impacto: +30% uso de tracking de sueño.* 4. **Segmentación de contenido** — Usuarias sedentarias reciben “empieza con 5 minutos”; usuarias activas reciben “supera tu récord”. *Impacto: +25% CTR en campañas.*

🎨 MOCKUPS DEL DASHBOARD (Power BI)

Layout de 1 página (1920×1080)

┌─────────────────────────────────────────────────────────────────────┐
│  BELLABEAT | Análisis de Comportamiento de Usuarios de Wearables   │
│  [Filtro: Usuario] [Filtro: Categoría] [Filtro: Fecha]            │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐          │
│  │  7,638   │  │  2,303   │  │  419     │  │  87%     │          │
│  │ Pasos    │  │ Calorías │  │ Min      │  │ Adheren- │          │
│  │ Promedio │  │ Promedio │  │ Sueño    │  │ cia      │          │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘          │
│                                                                     │
│  ┌────────────────────────────┐  ┌────────────────────────────┐  │
│  │  PASOS POR DÍA DE SEMANA   │  │  CORRELACIÓN PASOS-SUEÑO  │  │
│  │      [Barras verticales]   │  │      [Scatter + línea]     │  │
│  │  Lun Mar Mié Jue Vie Sab Dom│  │                             │  │
│  └────────────────────────────┘  └────────────────────────────┘  │
│                                                                     │
│  ┌────────────────────────────┐  ┌────────────────────────────┐  │
│  │  HEATMAP: ACTIVIDAD HORARIA│  │  SEGMENTACIÓN DE USUARIOS  │  │
│  │  [Día × Hora, color inten- │  │  [Donut: Sedentario/       │  │
│  │   sidad de pasos]          │  │   Ligero/Moderado/MuyAct]  │  │
│  └────────────────────────────┘  └────────────────────────────┘  │
│                                                                     │
│  ┌────────────────────────────────────────────────────────────┐  │
│  │  TENDENCIA TEMPORAL: Pasos, Calorías y Sueño (31 días)     │  │
│  │  [Líneas múltiples con eje Y secundario]                   │  │
│  └────────────────────────────────────────────────────────────┘  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘

Paleta de colores Bellabeat (recomendada)

| Rol | Color | Hex | Uso |
| --- | --- | --- | --- |
| Primario | Verde salud | #2E7D32 | KPIs positivos, metas alcanzadas |
| Secundario | Naranja energía | #FF6F00 | Alertas, fines de semana, call-to-action |
| Acento | Rosa Bellabeat | #EC407A | Mujeres, wellness, marca |
| Fondo | Gris oscuro | #263238 | Fondo del dashboard |
| Superficie | Gris medio | #37474F | Tarjetas y contenedores |
| Texto | Blanco | #FFFFFF | Títulos y labels |
| Texto secundario | Gris claro | #B0BEC5 | Subtítulos, ejes |

Reglas de diseño UX

- **Regla del 5 segundos:** Un ejecutivo debe entender el insight principal en 5 segundos.

- **Jerarquía visual:** KPIs arriba (más importantes), detalles abajo.

- **Consistencia:** Mismo color = mismo significado en todo el dashboard.

- **Contexto:** Cada gráfico debe tener un título que responda a una pregunta, no solo describa datos.

- ❌ “Pasos por día” → ✅ “¿Qué días somos más sedentarios?”

📊 MODELO ESTRELLA (Star Schema) — Diagrama

                    ┌─────────────────┐
                    │   dim_tiempo    │
                    │─────────────────│
                    │  tiempo_id (PK) │
                    │  fecha          │
                    │  dia_semana     │
                    │  nombre_dia     │
                    │  es_fin_de_sem  │
                    │  semana_num     │
                    │  mes            │
                    │  año            │
                    └────────┬────────┘
                             │
                             │ 1:N
                             ▼
┌─────────────────┐    ┌─────────────────────────────┐    ┌─────────────────┐
│   dim_usuario   │    │     fact_actividad_sueño    │    │ dim_categoria   │
│─────────────────│    │─────────────────────────────│    │─────────────────│
│  usuario_id (PK)│◄───│  actividad_id (PK)          │───►│  categoria_id   │
│  id_original    │    │  usuario_id (FK)            │    │  nombre_categ   │
│  categoria_user │    │  tiempo_id (FK)             │    │  rango_pasos_min│
│  adherencia_pct │    │  categoria_id (FK)          │    │  rango_pasos_max│
│  dias_registro  │    │                             │    └─────────────────┘
│  es_usuario_vip │    │  total_pasos                 │
└─────────────────┘    │  total_distancia             │
                       │  total_calorias              │
                       │  min_very_active             │
                       │  min_fairly_active           │
                       │  min_lightly_active          │
                       │  min_sedentary                │
                       │  min_total_active             │
                       │  pct_sedentary                │
                       │  min_sueno                    │
                       │  min_en_cama                  │
                       │  eficiencia_sueno             │
                       │  cumple_oms                   │
                       └─────────────────────────────┘

**Notas de modelado:** - Granularidad de la tabla de hechos: **1 fila por usuario por día** - dim_usuario se enriquece con atributos calculados (categoría, adherencia) - dim_tiempo permite inteligencia temporal (comparar vs mes anterior, acumulados) - dim_categoria permite filtrar usuarios por segmento de actividad

✅ CHECKLIST DE CALIDAD ANTES DE PUBLICAR

Técnico

- ☐ Todos los scripts SQL ejecutan sin errores

- ☐ El modelo estrella tiene relaciones 1:N correctas sin bidireccionalidad forzada

- ☐ Las medidas DAX devuelven resultados coherentes (validar con Excel)

- ☐ No hay datos personales ni IDs reales (anonimización)

- ☐ El .pbix pesa menos de 50MB (comprimir imágenes si es necesario)

Analítico

- ☐ Cada hallazgo tiene un gráfico que lo respalde

- ☐ Las correlaciones tienen valores p o al menos R² mencionados

- ☐ Las segmentaciones tienen criterios justificados (literatura OMS/CDC)

- ☐ Las limitaciones están documentadas honestamente

De comunicación

- ☐ El README tiene badges de herramientas y un screenshot del dashboard

- ☐ La presentación tiene máximo 15 palabras por diapositiva (regla del ” billboard”)

- ☐ El post de LinkedIn tiene un hook en la primera línea

- ☐ El repositorio tiene una descripción corta y profesional en GitHub

De portfolio

- ☐ El repositorio es público

- ☐ Hay un link directo al dataset de Kaggle (atribución)

- ☐ Se menciona que es un proyecto académico/capstone (transparencia)

- ☐ Se incluye un archivo LICENSE (MIT recomendado para código)

🚀 PRÓXIMOS PASOS TRAS PUBLICAR

- **Solicitar feedback** en comunidades: r/datascience, DataTalks.Club, Foro de Google Data Analytics

- **Añadir mejoras iterativas:**

- Predecir abandono del dispositivo con regresión logística

- Incluir análisis de sentimiento si se obtienen reviews de Bellabeat

- Automatizar ETL con Python + Airflow (versión senior)

- **Crear un artículo de Medium** explicando el proceso paso a paso

- **Preparar respuestas** para entrevistas técnicas sobre este proyecto:

- “¿Por qué elegiste un modelo estrella?”

- “¿Cómo manejaste los valores nulos en sleepDay?”

- “¿Qué harías diferente si tuvieras datos de 10.000 usuarios?”

*“**Un buen proyecto de portfolio no muestra que sabes usar una herramienta. Muestra que sabes resolver un problema de negocio con datos.**”*

**¡Manos a la obra! Día 1 empieza hoy.** 🎯

*Guía maestra generada para portfolio profesional de Data Analytics — Bellabeat Case Study*

Generated by Kimi.ai