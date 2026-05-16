# 🌍 Remote Work: ¿Revolución o Ilusión?
### Análisis del Impacto del Trabajo Remoto en Salarios, Stack Tecnológico y Experiencia
*Evidencia global del sector tech — Stack Overflow Developer Survey 2021 & 2025*

---

## 📌 Introducción

El trabajo remoto transformó el sector tecnológico tras la pandemia de 2020. Pero cuatro años después, ¿ha sido realmente democratizador? ¿O ha generado nuevas formas de desigualdad salarial y profesional?

Este proyecto analiza más de **130.000 respuestas** de desarrolladores de todo el mundo (surveys 2021 y 2025 de Stack Overflow) para responder preguntas concretas sobre el impacto real del teletrabajo en salarios, tecnologías y trayectorias profesionales.

---

## 🎯 Hipótesis

| # | Hipótesis |
|---|---|
| **H1** | Los trabajadores remotos en países emergentes cobran significativamente menos que los presenciales en países de alto ingreso → el remoto **no elimina** la brecha geográfica |
| **H2** | Los desarrolladores con **más de 10 años de experiencia** trabajan en remoto con mayor frecuencia que los perfiles junior |
| **H3** | Los lenguajes modernos (Python, Rust, Go) tienen una proporción de teletrabajadores **significativamente mayor** que los lenguajes legacy |

---

## 📁 Estructura del repositorio

```
PROYECTO_EDA/
│
├── README.md
├── main.ipynb                  ← Notebook principal (EDA completo y reproducible)
├── Memoria.pdf                 ← Memoria técnica del proyecto
├── Presentacion.pdf            ← Diapositivas del vídeo
│
└── src/
    ├── data/
    │   ├── survey_results_public.csv     ← Dataset SO Survey 2025 (no incluido, ver abajo)
    │   ├── survey_2021_public.csv        ← Dataset SO Survey 2021 (no incluido, ver abajo)
    │   ├── survey_results_schema.csv     ← Diccionario de columnas 2025
    │   └── survey_clean.csv             ← Dataset limpio generado por el notebook
    │
    ├── imagenes/               ← Gráficos generados automáticamente por el notebook
    │   ├── 01_distribucion_remoto.png
    │   ├── 02_distribucion_salarios.png
    │   ├── 03_distribucion_experiencia.png
    │   ├── 04_top_paises_respuestas.png
    │   ├── 05_h1_salario_remoto_boxplot.png
    │   ├── 06_h1b_brecha_geografica.png
    │   ├── 07_h2_experiencia_remoto.png
    │   ├── 08_h3_remoto_por_lenguaje.png
    │   ├── 09_heatmap_exp_remoto_salario.png
    │   ├── 10_pairplot_salario_exp.png
    │   ├── 11_remoto_por_devtype.png
    │   ├── 12_paises_remoto.png
    │   ├── 13_scatter_exp_salario_remoto.png
    │   ├── 14_evolucion_salario_2021_2025.png
    │   └── 15_evolucion_lenguajes_2021_2025.png
    │
    ├── notebooks/              ← Notebooks de exploración y versiones intermedias
    └── utils/
        └── funciones_eda.py   ← Funciones reutilizables del proyecto
```

---

## 📊 Dataset

Los datos provienen de la encuesta anual de Stack Overflow, una de las más representativas del sector tech a nivel global.

| Año | Respondentes | Países | Columnas |
|-----|-------------|--------|---------|
| 2025 | 49.191 | 177 | 172 |
| 2021 | 83.439 | 181 | 48 |

> ⚠️ **Los CSV no están incluidos en el repositorio** por su tamaño. Descárgalos aquí:
> - **2025:** https://survey.stackoverflow.co/ → *Download full data*
> - **2021:** https://www.kaggle.com/datasets/ruchi798/stack-overflow-annual-developer-survey-2021

Una vez descargados, colócalos en `src/data/` con estos nombres exactos:
```
src/data/survey_results_public.csv
src/data/survey_2021_public.csv
```

---

## ▶️ Cómo ejecutar el proyecto

### Requisitos

```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Ejecución

1. Clona el repositorio:
```bash
git clone https://github.com/[usuario]/PROYECTO_EDA.git
cd PROYECTO_EDA
```

2. Descarga los datasets y colócalos en `src/data/` (ver sección anterior)

3. Abre y ejecuta el notebook:
```bash
jupyter notebook main.ipynb
```

4. Ejecuta **Restart & Run All** para reproducir el análisis completo

> El notebook detecta automáticamente si el dataset de 2021 está disponible y activa/desactiva la sección comparativa sin errores.

---

## 🔍 Principales hallazgos

> *Completar con los resultados reales tras ejecutar el notebook*

- **H1 — Brecha salarial:** [resultado]
- **H1b — Brecha geográfica:** Los trabajadores remotos en países emergentes tienen una mediana salarial de $44k frente a los $77k de trabajadores remotos en países de alto ingreso, lo que confirma que el remoto no elimina la brecha geográfica
- **H2 — Experiencia:** [resultado]
- **H3 — Lenguajes:** [resultado]
- **Evolución 2021→2025:** [resultado comparativa]

---

## ⚠️ Limitaciones

- Dataset **auto-reportado** → sesgo de selección (más probable que respondan perfiles activos online)
- Salarios en **USD sin ajuste por PPP** (poder adquisitivo local)
- `RemoteWork` refleja un **momento puntual**, no una tendencia histórica
- El **survey 2021 no incluía pregunta sobre modalidad** de trabajo remoto, por lo que la comparativa temporal se limita a salarios y tecnologías
- Columnas multi-valor (`LanguageHaveWorkedWith`, `DevType`) requieren un paso de *explode* y pueden sobrerrepresentar perfiles con múltiples respuestas

---

## 🛠️ Tecnologías utilizadas

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-teal)
![SciPy](https://img.shields.io/badge/SciPy-1.x-8CAAE6)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626)

---

## 👥 Autores

| Persona | Rol | Responsabilidades |
|---------|-----|-------------------|
| Isaac | Data Engineer | Carga, limpieza, análisis univariante y bivariante, comparativa 2021 vs 2025 |
| Claudia | Narrativa & Comunicación | Análisis multivariante, verificación de hipótesis, memoria técnica, presentación |

---

## 📄 Licencia

Proyecto desarrollado en el marco del **Data Science Bootcamp — The Bridge**.  
Los datos originales pertenecen a Stack Overflow y están disponibles bajo licencia [ODbL](https://opendatacommons.org/licenses/odbl/).
