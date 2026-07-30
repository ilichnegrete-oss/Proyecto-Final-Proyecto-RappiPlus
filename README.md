[README.md](https://github.com/user-attachments/files/30565279/README.md)
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
```

---

## 📊 Datasets Utilizados

| Dataset | Descripción | Variables Clave |
| :--- | :--- | :--- |
| `rappiplus_orders_raw.csv` | Registros transaccionales de órdenes | `id_pedido`, `id_usuario`, `fecha_hora_pedido`, `pais`, `monto_total`, `cantidad`, `precio_unitario`, `monto_descuento` |
| `rappiplus_catalog.csv` | Catálogo maestro de productos y costos | `nombre_producto`, `categoria_producto`, `costo_unitario`, `proveedor` |
| `rappiplus_marketing_spend.csv` | Inversión publicitaria por canal y región | `fecha`, `pais`, `id_campaña`, `canal`, `gasto` |
| `SQL Tables (events, users)` | Comportamiento del usuario en la app | `user_id`, `event_type`, `event_timestamp`, `device_type` |
| `experiment_checkout_ui.csv` | Resultados del experimento A/B en checkout | `user_id`, `variant` (Control / Tratamiento), `converted`, `revenue` |

---

## 🛠️ Metodología y Flujo de Trabajo

El análisis sigue una secuencia lógica y progresiva estructurada en 6 etapas estratégicas:

### 🔍 1. Carga y Validación de Calidad de Datos (Data Hygiene)
* **Auditoría de integridad**: Identificación y tratamiento de valores nulos, registros duplicados y formato correcto de fechas/tipos de datos.
* **Detección de anomalías**: Filtro de valores numéricos inconsistentes (por ejemplo, pedidos atípicos de volumen masivo/mayorista en laptops y precios fuera de rango).
* **Exportación de datos limpios**: Generación de pipelines replicables para salvar DataFrames depurados (`orders_clean`, `catalog_clean`, `marketing_clean`).

### 💰 2. Análisis de Rentabilidad y Unit Economics
* **Cálculo de KPIs Financieros**:
  * **Revenue Total** e **Ingreso Neto**.
  * **Costo de Ventas (COGS)** mediante merge con el catálogo de proveedores.
  * **Inversión en Marketing (CAC / Spend)** por canal y país.
  * **Profit/Margen Operativo** global y por categoría de producto.
* **Comportamiento Transaccional**: Ticket Promedio (AOV), Unidades por Orden y Productos Top Ventas.

### 🛒 3. Embudo de Conversión (Funnel Analysis - SQL)
* Modelado en SQL para mapear la trayectoria del usuario:  
  `Home / Search` ➔ `Product View` ➔ `Add to Cart` ➔ `Checkout` ➔ `Payment Success`.
* Identificación de los principales puntos de fuga (*churn points*) dentro de la aplicación.

### 🔁 4. Retención por Cohortes (Cohort Analysis)
* Agrupación de usuarios según su mes de adquisición/primer pedido.
* Matriz de retención temporal para evaluar la recurrencia y *Lifetime Value (LTV)* del usuario RappiPlus.

### 🧪 5. Experimentación A/B (Checkout UI Test)
* Evaluación del impacto de la nueva interfaz de checkout en la tasa de conversión y ticket promedio.
* Pruebas de hipótesis estadísticas ($t$-test, Chi-cuadrado / Z-test de proporciones) para validar significancia al 95% de confianza.

### 📊 6. Dashboard de Negocio en BI
* Diseño de un tablero interactivo para decisiones de nivel directivo (C-Level):
  * **Filtros dinámicos**: País, Canal de Marketing, Categoría y Ventana Temporal.
  * **Visuales clave**: Métrica de margen neto, ROI por canal, tendencias de ventas y embudo interactivo.

---

## 📈 Hallazgos Clave & Insights de Negocio

1. **Calidad de Datos & Outliers**: Se identificaron órdenes corporativas/anómalas con volúmenes superiores a 10,000 unidades en categoría electrónica, requiriendo segmentación entre cliente B2C y B2B.
2. **Canales de Marketing Eficientes**: Canales como *Paid Search* y *Social* concentran el mayor volumen de tráfico, pero muestran variaciones importantes en el Costo de Adquisición (CAC) según el país.
3. **Puntos de Fuga en el Embudo**: El paso entre *Add to Cart* y *Checkout* presenta la mayor caída porcentual de usuarios, sugiriendo fricción en la experiencia de pago o costos sorpresa de envío.

---

## ⚙️ Requisitos e Instalación

Para ejecutar este proyecto localmente, sigue estos pasos:

1. **Clonar el repositorio**:
   ```bash
   git clone https://github.com/tu-usuario/rappiplus-data-analysis.git
   cd rappiplus-data-analysis
   ```

2. **Crear y activar un entorno virtual (opcional pero recomendado)**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # En Linux/macOS
   # venv\Scripts\activate  # En Windows
   ```

3. **Instalar dependencias**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Ejecutar el Notebook**:
   ```bash
   jupyter notebook notebooks/rappiplus_analysis.ipynb
   ```

---

## 🛠️ Tecnologías y Librerías Utilizadas

* **Lenguaje**: Python 3.9+
* **Análisis de Datos**: `pandas`, `numpy`
* **Visualización de Datos**: `matplotlib`, `seaborn`
* **Estadística & Tests**: `scipy.stats`, `statsmodels`
* **Base de Datos**: PostgreSQL / MySQL (Sintaxis SQL estándar)
* **Business Intelligence**: Power BI / Tableau

---

## 🤝 Créditos y Agradecimientos

* **Autor**: Ilich
* **Revisor del Proyecto**: Patricio Requena (Bootcamp Data Analytics)

---
*Procesado y analizado con un enfoque directo en impacto financiero y decisiones estratégicas.*
