# Ficha Técnica – Base de Datos Limpia

## Fuente de los datos
- **Instituto Nacional de Deportes (IND)**: Resultados oficiales de los Juegos Deportivos Escolares (JDE) para los años 2023, 2024 y 2025.
- **Federación Atlética de Chile (Fedachi)**: Resultados oficiales del Campeonato Nacional Adulto para los años 2023, 2024 y 2025.
- Los documentos fueron publicados en formato PDF en sitios oficiales y recopilados como insumo primario del proyecto.

---

## Metodología de construcción de la base
1. Extracción de datos desde PDFs utilizando herramientas de lectura de tablas (Python con librerías `tabula-py` y `camelot`) y validación manual en Excel.
2. Homogenización de variables:
   - Estándar de nombres (`nombre_atleta`, `prueba`, `resultado`, `region_club`).
   - Normalización de formatos de tiempos (segundos) y distancias (metros).
3. Integración de todas las competencias en una sola base con las variables comunes.
4. Eliminación de duplicados y estandarización de categorías (U14, U18, U20, Adulto).
5. Validación final de consistencia mediante estadísticas descriptivas y revisión manual.

---

## Alcance de los datos
- Cobertura temporal: 2023–2025.
- Nivel de competencia:  
  - **Escolar (U14)**: Final Nacional de los Juegos Deportivos Escolares.  
  - **Adulto (U18, U20 y Adulto)**: Campeonato Nacional Adulto.  
- Ámbito: Nacional, con representación de todas las regiones (JDE) y clubes (Adulto).

---

## Características de los datos
- **Unidad de análisis**: cada registro corresponde a la participación de un atleta en una prueba específica.
- **Dimensión longitudinal**: permite observar continuidad y evolución de atletas a lo largo de distintas competencias y años.
- **Datos comparables**: las variables fueron estandarizadas para facilitar cruces entre categorías escolares y adultas.

---

## Variables incorporadas

| Variable        | Descripción                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| `anio`          | Año de la competencia (2023, 2024, 2025).                                   |
| `competencia`   | Tipo de evento: Escolar (JDE) o Adulto (Campeonato Nacional).               |
| `nombre_atleta` | Nombre completo del atleta.                                                 |
| `sexo`          | Hombre / Mujer.                                                            |
| `categoria`     | U14, U18, U20, Adulto.                                                     |
| `region_club`   | Región (en JDE) o Club (en Campeonato Adulto).                              |
| `prueba`        | Disciplina específica (ejemplo: 100m planos, salto largo, 1500m).           |
| `resultado`     | Tiempo (en segundos) o distancia (en metros).                               |
| `lugar`         | Posición obtenida en la prueba.                                             |
| `valido`        | Marca válida (1) o no válida (0: DNS, DNF, DSQ).                            |

---

## Observaciones
- La base consolidada permite trazar la continuidad de atletas desde su etapa escolar hacia la adulta.  
- Existen casos de atletas que cambian de club o región entre competencias; se mantuvo el registro según la fuente oficial de cada campeonato.  
- Los valores de resultado no válidos fueron conservados como información contextual pero diferenciados en la variable `valido`.  
- La estructura de la base es **simple, clara y estandarizada**, por lo que puede utilizarse directamente para análisis y visualización.

---
