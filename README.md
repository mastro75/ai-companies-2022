# Understanding the 2022 AI Companies Landscape

**Marcela Zena · Agosto 2026**

## Sobre este proyecto

En 2022, antes de la adopción masiva de la IA generativa, miles de empresas ya ofrecían servicios relacionados con Inteligencia Artificial.

¿Cómo era ese ecosistema?

Este proyecto explora un dataset público de aproximadamente 3.100 empresas listadas en Clutch.co en 2022 para comprender el ecosistema representado en los datos: dónde estaban ubicadas las empresas, qué tipos de proveedores existían, qué tan enfocadas estaban en IA y qué diferencias aparecían entre distintos segmentos.

El dataset es imperfecto y representa una única fuente.

En lugar de tratar esas limitaciones como algo a eliminar, forman parte de la investigación: entender qué pueden decirnos los datos, qué no pueden decirnos y qué nuevas preguntas aparecen a partir de ellos.

---

## Preguntas que explora el análisis

El análisis comenzó con una pregunta amplia:

**¿Qué puedo comprender de este dataset y del ecosistema de empresas de IA que representa?**

A partir de ahí aparecieron nuevas preguntas:

- ¿Dónde estaban ubicadas estas empresas?
- ¿Qué tipos de proveedores estaban representados?
- ¿Qué tan central era la IA dentro de su oferta de servicios?
- ¿Cómo cambiaban esos patrones según el tamaño de las empresas?
- ¿Qué nivel de transparencia mostraban sobre información comercial como tarifas y tamaño mínimo de proyecto?

---

## De los datos originales a una vista más útil

El dataset original contiene información sobre empresas, ubicaciones, servicios AI y valores generales (Minimum Project Size y Average Hourly Rate)

Para poder comparar mejor esas dimensiones, el análisis incluyó:

1. Exploración inicial del dataset y evaluación de su calidad.
2. Limpieza y estandarización de información inconsistente.
3. Separación y normalización de datos geográficos.
4. Creación de nuevas variables para representar tamaño de empresa y foco en IA.
5. Exploración de relaciones entre geografía, tipo de proveedor, especialización en IA y transparencia comercial.
6. Identificación de patrones, casos particulares y preguntas que podrían justificar una investigación posterior.

El proceso completo de transformación y las decisiones metodológicas están documentados en el notebook.

---

## Una señal inesperada: Uruguay

Uno de los resultados llamó especialmente mi atención.

Dentro de las **465 empresas clasificadas como SMB + AI Focus principal**, Uruguay representa solamente **6 empresas**.

Las seis alcanzan el nivel máximo de transparencia comercial definido para este análisis.

Esto **no significa** que las empresas uruguayas de IA sean, en general, más transparentes.

Seis empresas constituyen una muestra demasiado pequeña para sostener esa conclusión y, además, el dataset representa únicamente empresas listadas en Clutch.co.

Pero el resultado abre una pregunta interesante:

**¿Existe alguna característica del ecosistema tecnológico uruguayo que pueda ayudar a explicar este patrón o se trata simplemente de una particularidad de esta muestra?**

Responder esa pregunta requeriría salir de este dataset: investigar las empresas individualmente, incorporar otras fuentes y comparar esta fotografía de 2022 con evidencia más reciente.

Por ahora, lo considero una señal que merece ser investigada, no una conclusión.

---

## Qué permite —y qué no permite— concluir este análisis

Este dataset debe entenderse como una fotografía histórica de un conjunto de empresas listadas en Clutch.co en 2022.

### Permite

- explorar patrones dentro de esta muestra
- comparar distintos segmentos de empresas
- identificar casos particulares
- generar hipótesis
- detectar preguntas para futuras investigaciones

### No permite

- describir la totalidad del mercado global de IA en 2022
- asumir que estas empresas mantienen actualmente las mismas características
- explicar por qué ocurrió un determinado patrón
- establecer causalidad a partir de relaciones observadas en los datos
- generalizar automáticamente los hallazgos más allá del dataset

A lo largo del análisis intento mantener una distinción entre **evidencia, interpretación e hipótesis**.

---

## Estructura del repositorio

├── README.md                         # La historia del análisis
├── README_technical.md               # Metodología y decisiones técnicas
├── notebooks/
│   └── 1_understanding_2022_ai_landscape.ipynb
├── data/
│   └── AI_Companies_marce_con_categorias.csv
└── images/
    └── Gráficos y visualizaciones seleccionadas

---

## Herramientas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- SCImago Graphica

Las herramientas acompañan la investigación.

**Las preguntas vienen primero.**
