## 🇬🇧 English

# Suitability Map — Biomethane Plant · Huesca

![Map preview](gif_huesca.gif)

Interactive visualisation of the territorial suitability analysis for biomethane plant deployment across the province of **Huesca, Spain**. The map allows cell-by-cell exploration of suitability scores and the factors behind them.

> The full geospatial analysis pipeline that produces these results lives in a separate repository: [**Biomethane-Plant-Design**](https://github.com/BabylonFushi/Biomethane-Plant-Design).

---

## View the map

**[Open interactive map](https://babylonfushi.github.io/biomethane_map/)**

---

## What does this map show?

The province of Huesca is divided into a grid of **500 × 500 metre cells** (~63,600 cells in total). Each cell receives a suitability score between 0 and 100 based on six key criteria for biomethane plant viability.

Cells are classified into four categories:

| Category | Score |
|---|---|
| 🟢 Optimal | ≥ 65 |
| 🟡 Good | 50 – 64 |
| 🟠 Moderate | 35 – 49 |
| 🔘 Unsuitable / Excluded | < 35 or exclusion criterion met |

Two final selections are additionally highlighted across eligible cells:

- 🟣 **Top 10** — The ten locations with the highest overall score.
- 🌸 **Viable in both models** — Cells that simultaneously meet the minimum thresholds for biomass, distance to pipeline, slope, and road type.

---

## Model variables

Each cell is evaluated on the following variables, weighted according to their relative importance in the final decision:

| Variable | Description | Weight |
|---|---|---|
| **Available biomass (10 km radius)** | Total pig farming capacity (places) within a 10 km radius. Primary feedstock source for the plant. | 25 % |
| **Distance to gas pipeline** | Distance in km to the nearest gas pipeline. Determines the cost of injecting biomethane into the grid. | 25 % |
| **Land classification** | Urban planning and land-use suitability based on official classification (SENU, SDUD, industrial, etc.). | 15 % |
| **Distance to urban centres** | Proximity to populated areas (exclusion buffers and accessibility). | 10 % |
| **Average slope** | Mean terrain slope in degrees. Affects construction and plant operation. | 10 % |
| **Road type** | Category of the nearest road (motorway, primary, secondary, local). Determines logistical accessibility. | 7 % |
| **Distance to road** | Distance in km to the nearest road suitable for heavy vehicles. | 5 % |
| **Natura 2000 network** | Penalty for overlap with ZEC, ZEPA, or combined protected areas. | 3 % |

### Automatic exclusion criteria

A cell is excluded from the analysis regardless of its score if any of the following conditions apply:

- Land classified as protected, residential, or incompatible use.
- Overlap with high-sensitivity Natura 2000 zones (ZEC + ZEPA).
- Average slope exceeding 15°.
- No access to roads suitable for heavy vehicles.
- Biomass below 200,000 places within a 10 km radius.

---

## How to use the map

- **Pan and zoom** using the mouse or trackpad.
- **Click on any cell** to view its full profile in the tooltip:
  - Score, cluster, biomass, distances, slope, land classification, and exclusion reason (if applicable).
- The **legend** (bottom-left corner) identifies K-Means clusters and final selection categories.

---

## Technologies

- [deck.gl](https://deck.gl/) — WebGL geospatial layer rendering
- [pydeck](https://deckgl.readthedocs.io/en/latest/) — Map generation from Python
- [GeoPandas](https://geopandas.org/) — Vector data processing
- [Shapely](https://shapely.readthedocs.io/) — Geometric operations
- GitHub Pages — Static map hosting

---

## Context

This map is the visual output of a **Master's Thesis** focused on territorial viability analysis for biomethane plants in Aragon, Spain. The province of Huesca hosts a significant pig farming industry, making it a strategic candidate for biomethane production from slurry.

The full analysis (preprocessing, scoring and clustering) is available in the [**Biomethane-Plant-Design**](https://github.com/BabylonFushi/Biomethane-Plant-Design) repository.

---

*Data sources: IGN, OpenStreetMap, MITECO, Government of Aragon · Projection: EPSG:25830 → EPSG:4326*

<br>

---

## 🇪🇸 Español

# Mapa de Idoneidad — Planta de Biometano · Huesca

![Vista previa del mapa](gif_huesca.gif)

Visualización interactiva del análisis de idoneidad territorial para la implantación de plantas de biometano en la provincia de **Huesca, España**. El mapa permite explorar celda por celda las puntuaciones de idoneidad y los factores que las determinan.

> El pipeline completo de análisis geoespacial que genera estos resultados se encuentra en un repositorio independiente: [**Biomethane-Plant-Design**](https://github.com/BabylonFushi/Biomethane-Plant-Design).

---

## Ver el mapa

**[Abrir mapa interactivo](https://babylonfushi.github.io/biomethane_map/)**

---

## ¿Qué muestra este mapa?

La provincia de Huesca está dividida en una cuadrícula de celdas de **500 × 500 metros** (~63.600 celdas en total). Cada celda recibe una puntuación de idoneidad entre 0 y 100 basada en seis criterios clave para la viabilidad de una planta de biometano.

Las celdas se clasifican en cuatro categorías:

| Categoría | Puntuación |
|---|---|
| 🟢 Óptima | ≥ 65 |
| 🟡 Buena | 50 – 64 |
| 🟠 Moderada | 35 – 49 |
| 🔘 No apta / Excluida | < 35 o cumple un criterio de exclusión |

Además, se destacan dos selecciones finales entre las celdas elegibles:

- 🟣 **Top 10** — Las diez ubicaciones con la puntuación global más alta.
- 🌸 **Viable en ambos modelos** — Celdas que cumplen simultáneamente los umbrales mínimos de biomasa, distancia al gasoducto, pendiente y tipo de vía.

---

## Variables del modelo

Cada celda se evalúa según las siguientes variables, ponderadas según su importancia relativa en la decisión final:

| Variable | Descripción | Peso |
|---|---|---|
| **Biomasa disponible (radio de 10 km)** | Capacidad porcina total (plazas) en un radio de 10 km. Fuente principal de materia prima para la planta. | 25 % |
| **Distancia al gasoducto** | Distancia en km al gasoducto más cercano. Determina el coste de inyección del biometano en la red. | 25 % |
| **Clasificación del suelo** | Idoneidad urbanística y de uso del suelo según la clasificación oficial (SENU, SDUD, industrial, etc.). | 15 % |
| **Distancia a núcleos urbanos** | Proximidad a zonas habitadas (zonas de exclusión y accesibilidad). | 10 % |
| **Pendiente media** | Pendiente media del terreno en grados. Afecta a la construcción y operación de la planta. | 10 % |
| **Tipo de vía** | Categoría de la vía más cercana (autovía, primaria, secundaria, local). Determina la accesibilidad logística. | 7 % |
| **Distancia a vía** | Distancia en km a la vía más cercana apta para vehículos pesados. | 5 % |
| **Red Natura 2000** | Penalización por solapamiento con zonas ZEC, ZEPA o combinadas. | 3 % |

### Criterios de exclusión automática

Una celda queda excluida del análisis independientemente de su puntuación si se cumple alguna de las siguientes condiciones:

- Suelo clasificado como protegido, residencial o de uso incompatible.
- Solapamiento con zonas Natura 2000 de alta sensibilidad (ZEC + ZEPA).
- Pendiente media superior a 15°.
- Sin acceso a vías aptas para vehículos pesados.
- Biomasa inferior a 200.000 plazas en un radio de 10 km.

---

## Cómo usar el mapa

- **Desplázate y haz zoom** con el ratón o el trackpad.
- **Haz clic en cualquier celda** para ver su perfil completo en el tooltip:
  - Puntuación, clúster, biomasa, distancias, pendiente, clasificación del suelo y motivo de exclusión (si aplica).
- La **leyenda** (esquina inferior izquierda) identifica los clústeres K-Means y las categorías de selección final.

---

## Tecnologías

- [deck.gl](https://deck.gl/) — Renderizado de capas geoespaciales mediante WebGL
- [pydeck](https://deckgl.readthedocs.io/en/latest/) — Generación de mapas desde Python
- [GeoPandas](https://geopandas.org/) — Procesamiento de datos vectoriales
- [Shapely](https://shapely.readthedocs.io/) — Operaciones geométricas
- GitHub Pages — Alojamiento estático del mapa

---

## Contexto

Este mapa es el resultado visual de un **Trabajo de Fin de Máster** centrado en el análisis de viabilidad territorial para plantas de biometano en Aragón, España. La provincia de Huesca cuenta con una importante industria porcina, lo que la convierte en una candidata estratégica para la producción de biometano a partir de purines.

El repositorio con el análisis completo (preprocesamiento, puntuación y clustering) está disponible en [**Biomethane-Plant-Design**](https://github.com/BabylonFushi/Biomethane-Plant-Design).

---

*Fuentes de datos: IGN, OpenStreetMap, MITECO, Gobierno de Aragón · Proyección: EPSG:25830 → EPSG:4326*
