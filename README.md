[proyecto rappiplus.md](https://github.com/user-attachments/files/30565159/proyecto.rappiplus.md)
# 🚀 Proyecto RappiPlus: De Datos a Decisiones de Negocio

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Data%20Extraction-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![PowerBI](https://img.shields.io/badge/Power_BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

## 📌 Descripción General del Proyecto

El objetivo principal de este proyecto es evaluar integralmente el desempeño del servicio de suscripción **RappiPlus** mediante un enfoque integral *Data-Driven*. A través del procesamiento, modelado y análisis estadístico de múltiples fuentes de datos (transacciones, catálogo, inversiones en marketing, logs de eventos en SQL y resultados de pruebas A/B), se transforman datos crudos en **insights estratégicos y recomendaciones accionables de negocio**.

El proyecto abarca desde la auditoría y depuración de datos hasta la construcción de un embudo de conversión, análisis de cohortes de retención, evaluación de experimentos de UI/UX y la creación de tableros directivos.

---

## 📂 Estructura del Repositorio

```text
├── data/
│   ├── raw/                        # Datasets originales sin procesar
│   │   ├── rappiplus_orders_raw.csv
│   │   ├── rappiplus_catalog.csv
│   │   ├── rappiplus_marketing_spend.csv
│   │   └── experiment_checkout_ui.csv
│   └── processed/                  # Datasets limpios y transformados
│       ├── orders_clean.csv
│       ├── catalog_clean.csv
│       └── marketing_clean.csv
├── notebooks/
│   └── rappiplus_analysis.ipynb    # Notebook principal con todo el pipeline de análisis
├── sql/
│   └── funnel_user_activity.sql    # Consultas SQL para extracción de eventos y comportamiento
├── dashboards/
│   └── rappiplus_executive_bi.pbix # Dashboard interactivo en Power BI / Tableau
├── .gitignore
├── README.md
└── requirements.txt                # Librerías y dependencias necesarias
