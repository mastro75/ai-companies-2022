# README Técnico — Understanding the 2022 AI Companies Landscape

**Metodología, decisiones técnicas y estructura del proyecto.**

---

## Estructura del repositorio

```
├── README.md                         # La historia del análisis
├── README_technical.md               # Metodología y decisiones técnicas (este archivo)
├── notebooks/
│   └── 1_understanding_2022_ai_landscape.ipynb
├── data/
│   └── AI_Companies_marce_con_categorias.csv
└── images/
    └── Gráficos y visualizaciones seleccionadas
```

---

## Dataset original

- **Fuente:** Kaggle — AI Companies Dataset (Vineeth Akkinapalli, 2022)
- **Empresas:** ~3.100 listadas en Clutch.co
- **Columnas originales:** 9
  - `Company_Name`
  - `Website`
  - `Location`
  - `Minimum Project Size`
  - `Average Hourly Rate`
  - `Number of Employees`
  - `Percent AI Service Focus`
  - `Unnamed: 7` (columna vacía, eliminada)

---

## Procesamiento realizado

### 1. Limpieza y estandarización

- Eliminación de columnas vacías o redundantes.
- Corrección de valores inconsistentes (`Undisclosed`, `Unknown`).
- Normalización de formatos en precios y rangos de empleados.
- Desglose de la columna `Location` en `Ciudad`, `Estado` y `Pais`.

### 2. Tratamiento de datos faltantes

- Búsqueda manual de ubicaciones para empresas sin `Location`.
- Corrección de países mal asignados (ej: `United States Minor Outlying Islands` → `United Kingdom`).
- Estandarización de nombres de países (ej: `Panamá` → `Panama`, `Reino Unido` → `United Kingdom`).

### 3. Feature Engineering

#### Segmentación por tamaño (`Number of Employees`)

- Extracción del número máximo de empleados a partir de rangos (`50 - 249` → `249`).
- Clasificación basada en umbrales de la Comisión Europea y la OCDE.

| Rango | Clasificación | Tipo de proveedor |
|-------|---------------|-------------------|
| `1 – 9` | Microempresa | SMB |
| `10 – 49` | Empresa pequeña | SMB |
| `50 – 249` | Empresa mediana / SME | SMB |
| `250 – 999` | Empresa grande / fuera de SME | Mid-market |
| `1000 – 4999` | Empresa grande / fuera de SME | Enterprise |
| `5000 – 9999` | Empresa grande / fuera de SME | Enterprise |
| `10000` | Empresa grande / fuera de SME | Enterprise |
| `Freelancer` | No aplica | Freelancer |

#### Segmentación por enfoque en IA (`Percent AI Service Focus`)

| Rango | Segmentación |
|-------|--------------|
| `70% – 100%` | AI Focus principal |
| `50% – 69%` | AI Focus |
| `20% – 49%` | AI Service complementary |
| `0% – 19%` | AI Service residual |

#### Transparencia comercial

- Creación de la columna `Transparencia_Comercial`:
  - `2`: informa ambos datos (`Minimum Project Size` y `Average Hourly Rate`)
  - `1`: informa solo uno
  - `0`: no informa ninguno

### 4. Análisis geográfico

- Agrupación de países en 8 regiones mediante un diccionario manual.
- Regiones definidas: América del Norte, Centroamérica, América del Sur, Europa, Asia, Oceanía, África, Oriente Medio.

---

## Tecnologías utilizadas

- **Python 3**
- **Pandas** — manipulación de datos
- **NumPy** — operaciones numéricas
- **Matplotlib** — visualizaciones base
- **Seaborn** — visualizaciones estadísticas
- **Jupyter Notebook** — entorno de desarrollo

---

## Cómo replicar el análisis

1. Clonar el repositorio.
2. Instalar las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Abrir y ejecutar el notebook:
   ```bash
   jupyter notebook notebooks/1_understanding_2022_ai_landscape.ipynb
   ```

---

## Notas sobre la reproducibilidad

- El dataset original está disponible en Kaggle.
- El archivo `AI_Companies_marce_con_categorias.csv` incluido en `data/` es el resultado del proceso de limpieza y transformación documentado en el notebook.
- Las rutas en el notebook son relativas (`data/archivo.csv`), por lo que el proyecto es portable.

---

## Limitaciones técnicas

- El dataset representa únicamente empresas listadas en Clutch.co.
- Los datos son de 2022 y no reflejan el estado actual del mercado.
- La información es auto-reportada por las empresas.
- La segmentación por tamaño y enfoque en IA es una aproximación basada en los datos disponibles, no una certificación formal.
