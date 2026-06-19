# 🌿 Bellabeat Case Study — Análisis de Datos de Wearables

Proyecto de análisis de datos (Capstone — Google Data Analytics Certificate) que analiza datos de uso de dispositivos Fitbit para generar recomendaciones de marketing y producto para **Bellabeat**, fabricante de wearables de bienestar para mujeres.

## 📌 Contexto de negocio

Bellabeat quiere consolidarse como un actor global más grande en el mercado de dispositivos inteligentes de salud. Como analista de datos junior del equipo de Marketing, este proyecto busca responder:

> **¿Cómo usan los consumidores los dispositivos de fitness, y qué tendencias de comportamiento pueden informar la estrategia de marketing de Bellabeat para aumentar la adopción y retención de usuarias?**

**Stakeholders:** Urška Sršen (cofundadora y CCO), Sandro Mur (cofundador), equipo de Marketing y equipo de Producto.
**Producto focalizado:** Leaf / Ivy (wearables con tracking de actividad, sueño y estrés).

## 📊 Sobre los datos

- **Fuente:** [Fitbit Fitness Tracker Data](https://www.kaggle.com/datasets/arashnic/fitbit) (Kaggle, dominio público)
- **Periodo:** 12 abril – 12 mayo 2016 (31 días)
- **Tamaño:** 18 archivos CSV con datos a nivel diario, horario y por segundo
- **Usuarios tras limpieza:** 32

> El dataset original **no se incluye** en este repositorio por tamaño y para mantenerlo ligero. Descárgalo desde Kaggle y colócalo en `data/raw/` (ver sección [Cómo reproducir](#-cómo-reproducir-el-análisis)).

**Limitaciones (evaluación ROCCC):**
- Muestra pequeña (32 usuarias) y un solo mes de 2016 → resultados no generalizables a toda la población.
- Sin datos demográficos (edad, género, ubicación).
- Cobertura desigual entre módulos: sueño (44 %), frecuencia cardíaca (36 %) y peso (7 %) registrados de forma mucho más parcial que la actividad diaria.
- Participación voluntaria → posible sesgo hacia usuarios ya interesados en el fitness.

## 🗂️ Estructura del repositorio

```
bellabeat-data-analysis/
├── notebooks/
│   ├── 01_limpieza_transformacion.ipynb   # Carga, auditoría de calidad, limpieza y feature engineering
│   └── 02_eda.ipynb                       # Análisis exploratorio, correlaciones, segmentación, insights
├── tableau/
│   └── bellabeat_dashboard.twbx           # Dashboard interactivo (Tableau Packaged Workbook)
├── docs/
│   ├── plan_de_trabajo.md                 # Plan de trabajo: stakeholders, hipótesis, fases
│   ├── guia_maestra_portfolio.md          # Guía de planificación del portfolio completo
│   └── checklist_fases_proyecto.md        # Checklist del framework Ask-Prepare-Process-Analyze-Share
├── data/
│   ├── raw/                               # CSV originales de Kaggle (no incluidos, ver más abajo)
│   └── processed/                         # Salida limpia generada por el notebook 01
├── requirements.txt
└── LICENSE
```

## 🔍 Metodología

Framework **Ask → Prepare → Process → Analyze → Share**:

| Fase | Dónde |
|---|---|
| Ask / Prepare | `docs/plan_de_trabajo.md` |
| Process (limpieza, deduplicación, outliers, feature engineering) | `notebooks/01_limpieza_transformacion.ipynb` |
| Analyze (EDA, correlaciones, segmentación, pruebas estadísticas) | `notebooks/02_eda.ipynb` |
| Share | `tableau/bellabeat_dashboard.twbx` + este README |

**Stack:** Python (pandas, numpy, scipy, matplotlib, seaborn) en Jupyter Notebook, y Tableau para el dashboard final.

## 💡 Hallazgos clave

KPIs globales sobre los 32 usuarios y 31 días analizados:

| Métrica | Valor |
|---|---|
| Pasos medios/día | 7,657 |
| Calorías medias/día | 2,315 |
| Minutos activos (moderado+)/día | 34.8 |
| Minutos sedentarios/día | 988 |
| Minutos dormidos/noche (cuando hay registro) | 419 |
| % de días que cumplen recomendación OMS de actividad | 42.6 % |

1. **El domingo es el día más sedentario.** Los pasos caen a 6,691 el domingo frente a 8,219 el sábado y 7,781 el lunes — no es un efecto "fin de semana" general (sábado es el día más activo de toda la semana), sino una caída específica del domingo. Oportunidad: notificación push el sábado por la noche con un plan ligero para el domingo.
2. **El tiempo sedentario se asocia con menos sueño registrado**, más que los pasos en sí (r = -0.60 entre minutos sedentarios y minutos dormidos, p < 0.001, frente a r = -0.19 para pasos). Sugiere que reducir el sedentarismo —no solo aumentar pasos— podría ser el mensaje más relevante para una función de bienestar del sueño.
3. **25 % de las usuarias son sedentarias** (< 5,000 pasos/día) frente a un 22 % "muy activas" (≥ 10,000 pasos/día). Oportunidad de gamificación (badges, recordatorios de "levántate cada 2h") para el segmento sedentario.
4. **Solo el 44 % de los días tiene registro de sueño**, frente al ~100 % de cobertura en actividad diaria. El uso del tracking de sueño es claramente menor — una oportunidad de mejora de producto/UX en Ivy (auto-detección de sueño).
5. **El pico de actividad diaria es a las 18:00h.** Ventana recomendada para notificaciones y campañas contextuales: 16:00–18:00h.

*(Detalle estadístico completo, gráficos y segmentación por niveles de actividad en `notebooks/02_eda.ipynb`.)*

## ⚙️ Cómo reproducir el análisis

```bash
git clone <(https://github.com/Adnamantina-web/Bellabeat_case_study)>>
cd bellabeat-data-analysis
pip install -r requirements.txt
```

1. Descarga el dataset desde [Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit) y descomprime los CSV en `data/raw/`.
2. Ejecuta `notebooks/01_limpieza_transformacion.ipynb` de principio a fin → genera los CSV limpios en `data/processed/data_clean/`.
3. Ejecuta `notebooks/02_eda.ipynb` para reproducir el análisis exploratorio y los insights.
4. Abre `tableau/bellabeat_dashboard.twbx` con [Tableau Public/Desktop](https://public.tableau.com/app/profile/bego.a.armillas.alonso/viz/Bellabeat_case_estudy/Dashboard1)) para explorar el dashboard interactivo.

## 📈 Dashboard

El dashboard interactivo está en `tableau/bellabeat_dashboard.twbx`. Si tienes Tableau Public, también puedes publicarlo ahí y enlazar la versión web aquí.

## 📄 Licencia

Código y notebooks bajo licencia [MIT](LICENSE). El dataset es propiedad de sus autores originales en Kaggle (Möbius / Fitbit), bajo dominio público — atribuir la fuente si lo reutilizas.

## 🙋 Autor

Proyecto Capstone del **Google Data Analytics Certificate**.
*(Begoña Armillas Alonso - armillas1976@gmail.com)*
