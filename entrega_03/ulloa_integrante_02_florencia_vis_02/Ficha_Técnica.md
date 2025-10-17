# Ficha Técnica – Base de Datos Limpia (Florencia Ulloa)

## 1. Fuente de los datos
- **Instituto Nacional de Deportes (IND)**: Resultados oficiales de los **Juegos Deportivos Escolares (JDE)** para los años **2023, 2024 y 2025**.  
- **Federación Atlética de Chile (FEDACHI)**: Resultados oficiales del **Campeonato Nacional Adulto** (2023–2025).  
- Los documentos fueron publicados en formato PDF en sitios oficiales y descargados como insumo primario del proyecto.

---

## 2. Metodología de construcción de la base

1. **Extracción de datos** desde los PDF oficiales realizandolo manualmente.  
2. **Validación manual en Excel**, verificando nombres, categorías y valores atípicos.  
3. **Homologación de variables** para todas las fuentes:
   - Estandarización de nombres (`nombre_atleta`, `prueba`, `resultado`).
5. **Normalización de categorías**: Escolar y Adulto.  
6. **Revisión final de consistencia** mediante estadísticas descriptivas y revisión cruzada entre las pruebas de salto.
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
| `categoria`     | Salto Largo, Salto Alto, Salto Garrocha|
| `Estandarización`   | Escolar (JDE) o Campeonato Adulto.                                    |
| `prueba`        | Saltos              |
| `resultado`     | Cantidad de atletas           |

---

## 5. Observaciones


- La base fue integrada con los documentos publicados por las distintas ediciones de los JDE y Fedachi, para formar un total de **848 registros**, manteniendo formato y unidades homogéneas.  
- Para la visualización individual se filtró exclusivamente la participación de atletas en saltos .  
- Los resultados finales fueron exportados en formato `.csv`, listos para análisis y visualización reproducible en Python.
