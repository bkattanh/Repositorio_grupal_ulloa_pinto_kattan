# Ficha Técnica – Base de Datos Limpia (Florencia Ulloa)

## 1. Fuente de los datos
- **Instituto Nacional de Deportes (IND)**: Resultados oficiales de los **Juegos Deportivos Escolares (JDE)** para los años **2023, 2024 y 2025**.  
- **Federación Atlética de Chile (FEDACHI)**: Resultados oficiales del **Campeonato Nacional Adulto** (2023–2025).  
- Los documentos fueron publicados en formato PDF en sitios oficiales y descargados como insumo primario del proyecto.

---

## 2. Metodología de construcción de la base

1. **Extracción de datos** desde los PDF oficiales utilizando Python con las librerías `tabula-py` y `camelot`.  
2. **Validación manual en Excel**, verificando nombres, categorías y valores atípicos.  
3. **Homologación de variables** para todas las fuentes:
   - Estandarización de nombres (`nombre_atleta`, `prueba`, `resultado`, `region_club`).
   - Conversión de los tiempos a segundos y de las distancias a metros.  
4. **Eliminación de duplicados** y corrección de valores vacíos o inconsistentes.  
5. **Normalización de categorías**: U14, U18, U20 y Adulto.  
6. **Revisión final de consistencia** mediante estadísticas descriptivas y revisión cruzada con las bases de Mario y Benjamín.

---

## 3. Alcance y características

- **Cobertura temporal:** 2023–2025  
- **Ámbito:** Nacional  
- **Nivel de competencia:** Escolar (JDE) y Adulto (Campeonato Nacional)  
- **Unidad de análisis:** cada fila representa la participación de un atleta en una prueba específica.  
- **Dimensión longitudinal:** permite comparar rendimiento a lo largo de los años.  

---

## 4. Variables incorporadas

| Variable        | Descripción                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| `anio`          | Año de la competencia (2023, 2024 o 2025).                                  |
| `competencia`   | Tipo de evento: Escolar (JDE) o Adulto (Campeonato Nacional).               |
| `nombre_atleta` | Nombre completo del atleta.                                                 |
| `sexo`          | Hombre / Mujer.                                                             |
| `categoria`     | Categoría etaria: U14, U18, U20, Adulto.                                    |
| `region_club`   | Región (JDE) o club (Campeonato Adulto).                                    |
| `prueba`        | Disciplina (ejemplo: 100m planos, 800m, salto largo, etc.).                 |
| `resultado`     | Tiempo (en segundos) o distancia (en metros), según la prueba.              |
| `lugar`         | Posición obtenida en la prueba.                                             |
| `valido`        | Indica si la marca fue válida (1) o no válida (0: DNS, DNF, DSQ).           |

---

## 5. Observaciones

- Las marcas no válidas se conservaron con el fin de mantener trazabilidad, diferenciadas mediante la variable `valido`.  
- La base fue integrada con las de Mario y Benjamín para formar un total de **848 registros**, manteniendo formato y unidades homogéneas.  
- Para la visualización individual se filtró exclusivamente la **prueba de 800m masculinos** con marcas válidas.  
- Los resultados finales fueron exportados en formato `.csv`, listos para análisis y visualización reproducible en Python.

---

**Florencia Ulloa**  
Proyecto de Visualización de Datos – Entrega 03  
Escuela de Periodismo · 2025
