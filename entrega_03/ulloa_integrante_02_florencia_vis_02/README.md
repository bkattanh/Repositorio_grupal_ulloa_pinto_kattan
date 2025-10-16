### README Personal: Visualización Atómica - Tendencia Anual del Rendimiento Atlético

#### Base de Datos y Procesamiento
La base de datos utilizada es `Florencia_database_limpia.csv` (Simulada para este análisis).

**Procesamiento para la Visualización:**
1.  **Carga y Filtrado:** Se cargó el archivo CSV. Se filtraron solo las competencias **'Nacional Escolar'** y **'Nacional Adulto'**.
2.  **Conversión de 'Marca':** La columna 'Marca' se transformó a un valor numérico (`Marca_Num`). Los tiempos se convirtieron a **segundos** (donde menor es mejor) y las distancias se mantuvieron como **metros** (donde mayor es mejor).
3.  **Clasificación de Pruebas:** Se creó la columna `Tipo_Prueba` para diferenciar entre **'Tiempo (Menor es Mejor)'** (carreras) y **'Distancia/Metros (Mayor es Mejor)'** (saltos y lanzamientos).
4.  **Agregación de Datos:** Se calculó el **rendimiento promedio** (`Marca_Num_Media`) para cada combinación de `Año`, `Tipo_Prueba` y `Categoria`.

**Selección de Datos y Justificación:**
Se seleccionaron las variables **Año**, **Tipo_Prueba**, **Categoria** y **Marca_Num** para trazar la progresión anual del rendimiento. El gráfico de líneas es ideal para contrastar la hipótesis de **aumento de rendimiento** en 2025.

#### Ficha Técnica de la Base de Datos

| Característica | Descripción |
| :--- | :--- |
| **Fuente** | Registros de Competencias de Atletismo (simulados o reales) |
| **Cobertura Temporal** | Años 2023, 2024, 2025 |
| **Observaciones** | Registros filtrados para solo incluir competencias 'Nacional Escolar' y 'Nacional Adulto'. Todas las marcas son de tiempo (segundos) o de distancia (metros). |

#### Variables Incorporadas

| Variable | Descripción |
| :--- | :--- |
| `Año` | Año de la competencia (2023, 2024, 2025). |
| `Categoria` | Nivel de los atletas (Escolar/Adulto y Masculino/Femenino). |
| `Tipo_Prueba` | Clasificación de la prueba: 'Tiempo' (Menor es Mejor) o **'Distancia/Metros'** (Mayor es Mejor). |
| `Marca_Num_Media`| La media del rendimiento (segundos o metros), agrupada por Año, Tipo_Prueba y Categoria. |

#### Preguntas que Responde la Visualización

1.  ¿El rendimiento promedio en las pruebas de **Tiempo** (carreras) en eventos nacionales mostró una tendencia a la baja (mejor rendimiento) en 2025?
2.  ¿El rendimiento promedio en las pruebas de **Distancia/Metros** (saltos/lanzamientos) en eventos nacionales mostró una tendencia al alza (mejor rendimiento) en 2025?
3.  ¿La tendencia de aumento de rendimiento se observa en todas las categorías?
