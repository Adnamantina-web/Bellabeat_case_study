📊 PLAN DE TRABAJO: Bellabeat Case Study

Proyecto completo de Análisis de Datos | Google Data Analytics Certificate

**Empresa:** Bellabeat (fabricante de dispositivos wellness para mujeres)
**Rol:** Analista de datos junior — Equipo de Marketing
**Dataset:** [Fitbit Fitness Tracker Data](https://www.kaggle.com/datasets/arashnic/fitbit) (Kaggle)
**Periodo de datos:** Abril — Mayo 2016 | 30 usuarios | 18 archivos CSV
**Producto focalizado:** Leaf / Ivy (wearables con tracking de actividad, sueño y estrés)
**Fecha del plan:** 31 de mayo de 2026

🎯 RESUMEN EJECUTIVO

Bellabeat quiere convertirse en un actor global más grande en el mercado de dispositivos inteligentes. Urška Sršen (CCO y cofundadora) cree que analizar datos de uso de dispositivos de la competencia (Fitbit) revelará oportunidades de crecimiento. Este proyecto busca entender **cómo usan los consumidores sus dispositivos no-Bellabeat** para aplicar esos insights a la estrategia de marketing de un producto Bellabeat concreto.

**Hipótesis inicial:** *“Los usuarios de dispositivos fitness presentan patrones de actividad inconsistentes entre semana y fin de semana, con déficits de sueño correlacionados con días de baja actividad. Bellabeat puede aprovechar estos insights para crear campañas de marketing personalizadas por día de la semana y funciones de ‘recordatorios inteligentes’ en su app.”*

🔷 FASE 1: PREGUNTAR (Ask) — Definir el problema y los objetivos

1.1. Stakeholders clave

| Stakeholder | Rol | Interés en el proyecto |
| --- | --- | --- |
| Urška Sršen | Cofundadora y CCO | Estrategia de marketing global, narrativa de marca |
| Sandro Mur | Cofundador y matemático | Viabilidad técnica, análisis de datos |
| Equipo de Marketing | Ejecución de campañas | Insights accionables para campañas y producto |
| Equipo de Producto | Desarrollo de wearables | Features basadas en comportamiento de usuarios |

1.2. Declaración del problema

**¿Cómo usan los consumidores dispositivos de fitness y qué tendencias de comportamiento pueden informar la estrategia de marketing de Bellabeat para aumentar la adopción y retención de usuarias?**

1.3. Preguntas guía de análisis (SMART)

- ¿Cuáles son los patrones de actividad física diaria de los usuarios (pasos, distancia, minutos activos)?

- ¿Existe correlación entre la calidad del sueño y los niveles de actividad física?

- ¿Qué días de la semana y qué horarios presentan mayor/menor actividad?

- ¿Qué porcentaje de usuarios cumple con las recomendaciones de actividad de la OMS (150 min/semana moderada)?

- ¿Cómo varían los hábitos de salud entre usuarios más y menos activos?

- ¿Cuántos días a la semana usan realmente el dispositivo (adherencia/retención)?

1.4. Entregables de esta fase

- ☐ Mapa de stakeholders completado

- ☐ Declaración del problema redactada

- ☐ Preguntas guía validadas

- ☐ Justificación del producto Bellabeat seleccionado (Leaf o Ivy)

🔷 FASE 2: PREPARAR (Prepare) — Recopilar y organizar los datos

2.1. Origen y credibilidad del dataset

- **Fuente:** Kaggle — Dataset público Fitbit Fitness Tracker Data (subido por Mobius)

- **Licencia:** CC0 (dominio público)

- **Recolección:** Datos generados por consentimiento de usuarios de Fitbit mediante Amazon Mechanical Turk

- **Periodo:** 12 de abril — 12 de mayo de 2016 (31 días)

- **Usuarios:** 30 usuarios identificados por ID anónimo

- **Granularidad:** Diaria, por hora y por minuto

2.2. Archivos clave a utilizar

| Archivo | Registros | Descripción | Relevancia |
| --- | --- | --- | --- |
| dailyActivity_merged.csv | ~940 filas | Resumen diario: pasos, distancia, minutos activos, calorías | **⭐ Principal** |
| sleepDay_merged.csv | ~410 filas | Minutos dormidos, minutos en cama, registros de sueño | **⭐ Principal** |
| hourlySteps_merged.csv | ~22.000 filas | Pasos acumulados por hora | Patrones horarios |
| hourlyCalories_merged.csv | ~22.000 filas | Calorías quemadas por hora | Correlación temporal |
| hourlyIntensities_merged.csv | ~22.000 filas | Intensidad de actividad por hora | Análisis de picos |
| weightLogInfo_merged.csv | ~67 filas | Peso, IMC, grasa corporal (solo 8 usuarios) | Análisis limitado |
| heartrate_seconds_merged.csv | ~2.5M filas | Ritmo cardíaco por minuto | Análisis de intensidad |

2.3. Archivos redundantes (a excluir o usar solo para validación)

- dailyCalories_merged.csv, dailySteps_merged.csv, dailyIntensities_merged.csv → Ya están agregados en dailyActivity_merged.csv

2.4. Limitaciones del dataset (a documentar)

| Limitación | Impacto | Mitigación |
| --- | --- | --- |
| Solo 30 usuarios | Muestra pequeña, baja representatividad | Tratar como estudio piloto; no generalizar |
| Sin datos demográficos | No sabemos género, edad, ubicación | Asumir comportamientos generales; mencionar sesgo |
| Sesgo de autoselección | Usuarios de Fitbit son más activos que la media poblacional | Comparar con benchmarks de la OMS/CDC |
| Datos de 2016 | Tecnología y hábitos han evolucionado | Patrones biológicos (sueño, actividad) son estables |
| Desbalance en registros | No todos los usuarios registran sueño, peso o ritmo cardíaco | Analizar solo con usuarios que tienen datos completos |

2.5. Estructura de carpetas del proyecto

📁 bellabeat_case_study/
├── 📁 01_raw_data/
│   ├── dailyActivity_merged.csv
│   ├── sleepDay_merged.csv
│   ├── hourlySteps_merged.csv
│   ├── hourlyCalories_merged.csv
│   ├── hourlyIntensities_merged.csv
│   ├── weightLogInfo_merged.csv
│   └── heartrate_seconds_merged.csv
├── 📁 02_processed_data/
│   ├── daily_clean.csv
│   ├── sleep_clean.csv
│   ├── hourly_clean.csv
│   └── daily_merged.csv (actividad + sueño)
├── 📁 03_analysis/
│   ├── exploratory_analysis.R / .ipynb
│   ├── correlation_tests.R / .ipynb
│   └── segmentation.R / .ipynb
├── 📁 04_visualizations/
│   ├── dashboard.twbx / .pbix
│   └── charts/
└── 📁 05_deliverables/
    ├── presentation.pptx / .pdf
    └── executive_summary.pdf

2.6. Entregables de esta fase

- ☐ Dataset descargado de Kaggle y almacenado localmente

- ☐ Diccionario de datos creado (columna, tipo, descripción, unidades)

- ☐ Informe de limitaciones y credibilidad del dataset

- ☐ Estructura de carpetas implementada

🔷 FASE 3: PROCESAR (Process) — Limpiar y transformar los datos

3.1. Herramientas recomendadas

| Nivel | Herramienta | Uso |
| --- | --- | --- |
| Principiante | Excel / Google Sheets | Inspección, filtros, eliminación manual de duplicados |
| Intermedio | SQL (BigQuery / SQLite) | Joins, filtros, agregaciones |
| Avanzado | R (tidyverse) o Python (pandas) | Limpieza programática, transformaciones complejas |

3.2. Checklist de limpieza

- ☐ **Eliminar duplicados:** sleepDay_merged contiene 3 registros duplicados exactos

- ☐ **Manejar valores nulos:**

- weightLogInfo_merged: 65% de valores nulos en Fat → excluir columna o excluir archivo del análisis principal

- sleepDay_merged: usuarios sin registros de sueño → documentar y analizar solo con subconjunto válido

- ☐ **Estandarizar fechas:** Convertir todas las fechas a formato ISO YYYY-MM-DD o YYYY-MM-DD HH:MM:SS

- ☐ **Verificar consistencia de IDs:** Asegurar que Id sea numérico y consistente entre archivos

- ☐ **Validar rangos lógicos:**

- Pasos: ≥ 0

- Minutos sedentarios: ≤ 1440

- Calorías: > 0 y < 10.000 (rango fisiológico)

- Minutos dormidos ≤ minutos en cama

- ☐ **Eliminar redundancias:** No usar dailyCalories, dailySteps, dailyIntensities como tablas principales (ya están en dailyActivity)

3.3. Transformaciones y feature engineering

| Nueva métrica | Fórmula | Propósito |
| --- | --- | --- |
| DayOfWeek | WEEKDAY(ActivityDate) | Análisis por día de la semana |
| IsWeekend | IF DayOfWeek IN (Sábado, Domingo) | Comparar fin de semana vs entre semana |
| ActiveMinutes | VeryActiveMinutes + FairlyActiveMinutes | Actividad significativa (OMS) |
| SedentaryPercentage | SedentaryMinutes / 1440 * 100 | Porcentaje del día sedentario |
| SleepEfficiency | TotalMinutesAsleep / TotalTimeInBed | Calidad del sueño (0-1) |
| TotalDistanceKm | TotalDistance * 1.60934 | Conversión a kilómetros |
| UserCategory | CASE WHEN ActiveMinutes >= 150/7 THEN 'Activo' ELSE 'Sedentario' | Segmentación OMS diaria |
| WeekNumber | WEEK(ActivityDate) | Agrupación semanal |

3.4. Integración de datos (Merge principal)

**Tabla maestro:** daily_merged.csv - **Left table:** dailyActivity_merged (base completa, ~940 registros, 33 usuarios) - **Right table:** sleepDay_merged (~410 registros, 24 usuarios) - **Join keys:** Id + ActivityDate (o SleepDay convertido a fecha) - **Tipo de join:** LEFT JOIN (conservar todos los registros de actividad, aunque no tengan sueño) - **Resultado esperado:** ~940 registros con actividad + sueño (donde exista)

3.5. Entregables de esta fase

- ☐ Dataset limpio: daily_clean.csv, sleep_clean.csv, hourly_clean.csv

- ☐ Dataset integrado: daily_merged.csv

- ☐ Script/documento de limpieza (reproducible)

- ☐ Diccionario de datos actualizado con nuevas métricas

🔷 FASE 4: ANALIZAR (Analyze) — Explorar, modelar e interpretar

4.1. Análisis Descriptivo — ¿Qué está pasando?

4.1.1. Perfil general de los usuarios

| Métrica | Cálculo | Visualización |
| --- | --- | --- |
| Promedio diario de pasos | AVG(TotalSteps) | KPI card |
| Promedio diario de calorías | AVG(Calories) | KPI card |
| Promedio de minutos activos | AVG(ActiveMinutes) | KPI card |
| Promedio de minutos dormidos | AVG(TotalMinutesAsleep) | KPI card |
| Promedio de eficiencia del sueño | AVG(SleepEfficiency) | KPI card |
| Distribución de usuarios por categoría | COUNT(UserCategory) | Gráfico de barras/pastel |

4.1.2. Análisis temporal

| Análisis | Pregunta a responder | Visualización |
| --- | --- | --- |
| Pasos por día de la semana | ¿Hay días más activos que otros? | Barras agrupadas (Lun-Dom) |
| Calorías por día de la semana | ¿El gasto energético varía? | Líneas o barras |
| Minutos sedentarios por día | ¿Cuándo somos más sedentarios? | Barras apiladas |
| Sueño por día de la semana | ¿Dormimos más los fines de semana? | Barras comparativas |
| Actividad por hora del día | ¿A qué horas nos movemos más? | Heatmap (día × hora) o líneas |

4.1.3. Análisis de adherencia

| Métrica | Cálculo | Insight |
| --- | --- | --- |
| Días de uso por usuario | COUNT(DISTINCT ActivityDate) por Id | ¿Cuántos días usaron el dispositivo en el mes? |
| Tasa de adherencia | Días de uso / 31 días | % de cumplimiento del tracking |
| Usuarios con datos completos | Id que aparecen en actividad + sueño + peso | Subconjunto más fiable |

4.2. Análisis Diagnóstico — ¿Por qué está pasando?

4.2.1. Correlaciones clave a investigar

| Hipótesis | Variables | Método | Visualización |
| --- | --- | --- | --- |
| Más pasos = mejor sueño | TotalSteps vs TotalMinutesAsleep | Correlación Pearson | Scatter plot + línea de tendencia |
| Más actividad = menos sedentarismo | ActiveMinutes vs SedentaryMinutes | Correlación Pearson | Scatter plot |
| Eficiencia del sueño se relaciona con actividad previa | SleepEfficiency vs ActiveMinutes (día anterior) | Correlación con lag | Scatter plot |
| Día de la semana afecta la actividad | TotalSteps por DayOfWeek | ANOVA / t-test | Boxplot por día |
| Fines de semana vs entre semana | TotalSteps por IsWeekend | t-test | Boxplot comparativo |

4.2.2. Segmentación de usuarios

**Criterio recomendado:** Basado en promedio diario de pasos (benchmarks de la literatura) | Segmento | Rango de pasos/día | Perfil | |———-|——————-|——–| | Sedentario | < 5.000 | Baja actividad, alto riesgo cardiovascular | | Ligeramente activo | 5.000 — 7.499 | Actividad mínima, cumple mínimos básicos | | Moderado | 7.500 — 9.999 | Actividad saludable, cerca de recomendaciones | | Muy activo | ≥ 10.000 | Cumple/meta de 10.000 pasos, alto compromiso |

**Análisis por segmento:** - Comparar sueño, calorías, minutos activos y sedentarios entre segmentos - Identificar qué segmentos tienen mejor adherencia al dispositivo

4.3. Análisis avanzado (opcional)

- **K-Means Clustering:** Agrupar usuarios en 3-4 clusters basados en múltiples variables (pasos, sueño, sedentarismo, calorías)

- **Regresión lineal:** Predecir calorías quemadas en función de pasos + minutos activos

- **Análisis de series temporales:** Tendencias de actividad a lo largo del mes (¿hay fatiga? ¿aumento de uso?)

4.4. Entregables de esta fase

- ☐ Tablas de resumen estadístico (media, mediana, desviación estándar, min, max)

- ☐ Matriz de correlaciones (heatmap)

- ☐ Gráficos exploratorios (mínimo 5 visualizaciones)

- ☐ Segmentación de usuarios documentada

- ☐ Hallazgos clave redactados en lenguaje no técnico

🔷 FASE 5: COMPARTIR (Share) — Visualizar y presentar insights

5.1. Dashboard ejecutivo recomendado

Crear un dashboard interactivo (Tableau Public, Power BI o R Shiny) con las siguientes visualizaciones:

| # | Visualización | Insight que comunica | Tipo de gráfico |
| --- | --- | --- | --- |
| 1 | **KPI Cards** | Promedios globales: pasos, calorías, sueño, adherencia | Tarjetas numéricas |
| 2 | **Actividad por día de semana** | ¿Qué días somos más activos? | Barras verticales |
| 3 | **Heatmap de ****actividad horaria** | ¿A qué horas nos movemos? (día × hora) | Heatmap |
| 4 | **Scatter: Pasos vs Sueño** | ¿Más actividad = mejor descanso? | Dispersión + tendencia |
| 5 | **Distribución de segmentos** | ¿Qué % de usuarios son sedentarios? | Gráfico de pastel/donut |
| 6 | **Boxplot: Fin de semana vs Entre semana** | ¿Hay diferencia significativa? | Boxplot comparativo |
| 7 | **Tendencia temporal** | ¿Cómo evoluciona la actividad durante el mes? | Línea de tiempo |

5.2. Estructura de la presentación ejecutiva (7-10 diapositivas)

Diapositiva 1: Título y Contexto

- Título: “Análisis de comportamiento de usuarios de wearables — Oportunidades para Bellabeat”

- Tu nombre y rol: Analista de datos junior, Equipo de Marketing

- Fecha y dataset analizado

Diapositiva 2: Resumen Ejecutivo (3 insights principales)

- Insight 1: Patrón de actividad semanal

- Insight 2: Relación actividad-sueño

- Insight 3: Segmentación de usuarios y adherencia

Diapositiva 3: Metodología y Limitaciones

- Dataset: 30 usuarios, 31 días, Fitbit data (Kaggle)

- Herramientas utilizadas

- Limitaciones clave: muestra pequeña, sin datos demográficos, datos de 2016

Diapositiva 4: Hallazgo 1 — Patrones de actividad semanal

- Gráfico: Pasos por día de la semana

- Narrativa: “Los usuarios son más activos martes a sábado, con caída significativa los domingos y lunes”

Diapositiva 5: Hallazgo 2 — Sueño y actividad están conectados

- Gráfico: Scatter plot pasos vs minutos dormidos

- Narrativa: “Existe correlación positiva entre actividad diaria y calidad del sueño”

Diapositiva 6: Hallazgo 3 — Segmentación de usuarios

- Gráfico: Distribución de segmentos (sedentario a muy activo)

- Narrativa: “El 40% de los usuarios no alcanza los 7.500 pasos diarios recomendados”

Diapositiva 7: Hallazgo 4 — Adherencia al dispositivo

- Gráfico: Días de uso por usuario

- Narrativa: “Aunque los usuarios usan el dispositivo diariamente, solo el 60% registra sueño consistentemente”

Diapositiva 8: Recomendaciones estratégicas para Bellabeat

- 3-4 recomendaciones concretas vinculadas a los hallazgos

Diapositiva 9: Próximos pasos

- Ampliar muestra con datos propios de Bellabeat

- Incluir datos demográficos (edad, género) para personalización

- Realizar A/B testing de las recomendaciones de marketing

Diapositiva 10: Preguntas y discusión

5.3. Recomendaciones estratégicas vinculadas a los hallazgos

| Hallazgo | Recomendación de Marketing | Producto/Feature implicado |
| --- | --- | --- |
| Caída de actividad domingo-lunes | **Campaña “Domingo de preparación”:** Notificación push el domingo por la tarde con plan de actividad para la semana | App Bellabeat + Leaf/Ivy |
| Correlación positiva pasos-sueño | **Feature “Ciclo de bienestar”:** Dashboard en app que muestre “Tu actividad de hoy mejorará tu sueño de mañana” | App Bellabeat |
| 40% de usuarios son sedentarios (<7.500 pasos) | **Gamificación:** Sistema de badges “Meta semanal”, retos personalizados y recordatorios de “levántate y camina” cada 2 horas | Leaf / Ivy + App |
| Baja adherencia al tracking de sueño | **Simplificación:** Auto-detección del sueño en Ivy (sin necesidad de activar manualmente) + notificaciones suaves de “¿Lista para dormir?” | Ivy (mejora de UX) |
| Picos de actividad entre 17:00-19:00 | **Marketing contextual:** Anuncios en redes sociales entre 15:00-16:00 (antes del pico) promoviendo “Tu momento de moverte” | Campañas Meta/Instagram |

📅 CRONOGRAMA SUGERIDO (2-3 semanas)

| Semana | Fase | Actividades detalladas | Entregable |
| --- | --- | --- | --- |
| **Semana 1 (Días 1-2)** | **PREGUNTAR** | Leer caso Bellabeat, identificar stakeholders, formular preguntas, seleccionar producto | Plan de análisis aprobado |
| **Semana 1 (Días 3-4)** | **PREPARAR** | Descargar Kaggle, inspeccionar archivos, crear diccionario de datos, documentar limitaciones | Dataset organizado + diccionario |
| **Semana 1 (Días 5-7)** | **PROCESAR** | Limpiar duplicados, manejar nulos, estandarizar fechas, crear métricas derivadas, mergear tablas | Dataset procesado + script de limpieza |
| **Semana 2 (Días 8-10)** | **ANALIZAR (Descriptivo)** | Calcular estadísticas descriptivas, analizar patrones temporales, crear visualizaciones exploratorias | Tablas resumen + gráficos exploratorios |
| **Semana 2 (Días 11-12)** | **ANALIZAR (Diagnóstico)** | Correlaciones, segmentación de usuarios, pruebas estadísticas, análisis de adherencia | Hallazgos clave documentados |
| **Semana 2 (Días 13-14)** | **COMPARTIR (Dashboard)** | Construir dashboard interactivo en Tableau/Power BI/R | Dashboard funcional |
| **Semana 3 (Días 15-17)** | **COMPARTIR (Presentación)** | Diseñar diapositivas, redactar narrativa, vincular hallazgos con recomendaciones | Presentación ejecutiva |
| **Semana 3 (Días 18-19)** | **Revisión** | Revisar coherencia, validar datos, ensayar presentación | Versión final aprobada |
| **Semana 3 (Día 20)** | **Entrega** | Publicar en portfolio / entregar a stakeholders | Proyecto completo entregado |

🛠️ STACK TECNOLÓGICO RECOMENDADO

| Fase | Opción Principiante | Opción Intermedio | Opción Avanzado |
| --- | --- | --- | --- |
| **Preparar** | Excel / Google Sheets | SQL (BigQuery) | R (readr) / Python (pandas) |
| **Procesar** | Google Sheets + funciones | SQL + Excel | R (dplyr, tidyr) / Python (pandas, numpy) |
| **Analizar** | Excel (tablas dinámicas) | SQL + Excel avanzado | R (ggplot2, summary) / Python (matplotlib, seaborn, scipy) |
| **Compartir** | Google Slides + Canva | Tableau Public | Power BI / R Markdown / Jupyter Notebook |

📋 CHECKLIST FINAL DEL PROYECTO

Antes de empezar:

- ☐ He leído completamente el caso Bellabeat

- ☐ He descargado el dataset de Kaggle

- ☐ He elegido un producto Bellabeat como foco (Leaf / Ivy / Time / Spring)

- ☐ He definido mis preguntas de análisis

Durante el procesamiento:

- ☐ He documentado todos los pasos de limpieza

- ☐ He verificado que no hay duplicados

- ☐ He creado métricas derivadas (SleepEfficiency, ActiveMinutes, etc.)

- ☐ He guardado el dataset integrado (daily_merged.csv)

Durante el análisis:

- ☐ He calculado estadísticas descriptivas

- ☐ He identificado al menos 3 correlaciones o patrones significativos

- ☐ He segmentado a los usuarios en grupos de comportamiento

- ☐ He documentado los hallazgos en lenguaje no técnico

Durante la presentación:

- ☐ Mis gráficos tienen títulos claros, ejes etiquetados y leyendas

- ☐ He limitado cada diapositiva a 1 insight principal

- ☐ He vinculado cada hallazgo con una recomendación de negocio

- ☐ He mencionado las limitaciones del análisis con transparencia

📚 RECURSOS ADICIONALES

- **Dataset Kaggle:** [Fitbit Fitness Tracker Data](https://www.kaggle.com/datasets/arashnic/fitbit)

- **Caso original:** Google Data Analytics Certificate — Capstone (Bellabeat)

- **Benchmarks de actividad:** OMS recomienda 150-300 min/semana de actividad moderada o 75-150 min intensa

- **Meta de pasos:** 10.000 pasos/día es una meta popular; 7.500 es considerada saludable por la literatura reciente

- **Guía de correlación:** Pearson para relaciones lineales; Spearman para relaciones monotónicas

**Nota para el analista:** Este plan es una guía estructurada pero flexible. Adapta las herramientos y profundidad del análisis según tu nivel técnico y el tiempo disponible. Lo más importante es mantener la coherencia entre los hallazgos de datos y las recomendaciones de negocio para Bellabeat.

*Documento generado para el proyecto Bellabeat Case Study — Google Data Analytics*

**Diccionario**** ****abreviado**** para dashboards (Python)**

columnas_dashboard = {

    "Id": "id",

    "ActivityDate": "fecha",

    "TotalSteps": "pasos",

    "TotalDistance": "dist_total",

    "TrackerDistance": "dist_rastreador",

    "LoggedActivitiesDistance": "dist_manual",

    "VeryActiveDistance": "dist_muy_act",

    "ModeratelyActiveDistance": "dist_mod",

    "LightActiveDistance": "dist_lig",

    "SedentaryActiveDistance": "dist_sed",

    "VeryActiveMinutes": "min_muy_act",

    "FairlyActiveMinutes": "min_mod",

    "LightlyActiveMinutes": "min_lig",

    "SedentaryMinutes": "min_sed",

    "Calories": "kcal"

}

df = df.rename(columns=columnas_dashboard)

Generated by Kimi.ai