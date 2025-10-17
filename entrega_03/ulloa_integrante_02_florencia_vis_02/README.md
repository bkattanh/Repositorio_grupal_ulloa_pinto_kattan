# README - Florencia Ulloa

### 1. Proceso y Decisiones de Visualización

**Objetivo:** Comunicar la brecha de participación de atletas únicos entre Salto Largo y Salto Garrocha por categoría.

**Pasos Clave:**
1.  **Carga y Filtrado:** Se cargó el archivo `Florencia_database_limpia 2.csv` y se filtraron solo las pruebas 'Salto Largo' y 'Salto Garrocha', ya que son las que mejor ilustran la disparidad de participación central a nuestra hipótesis.
2.  **Agregación (Conteo Único):** Se aplicó una función de agregación en Python (`groupby(['Categoria', 'Prueba'])['Nombre Atleta'].nunique()`) para asegurar que cada atleta se contara una sola vez por categoría y por prueba, eliminando la sobrestimación por múltiples registros de la misma persona.
3.  **Visualización (Altair):** Se eligió un **Gráfico de Barras Agrupadas** para permitir la **comparación visual directa** de la longitud de las barras (participación) entre las dos pruebas (colores) dentro de cada categoría (eje Y). El facetado por `Prueba` con escalas independientes en el eje X (resolve_scale(x='independent')) resalta la distribución interna, mientras que la longitud de las barras muestra la magnitud.
4.  **Diseño:** Se usó un color distintivo (Azul) para Salto Largo (alta participación) y un color de alerta (Rojo) para Salto Garrocha (baja participación) para reforzar el contraste de la narrativa.

---

### 2. Base de Datos, Procesamiento y Ficha Técnica

| Variable | Descripción |
| :--- | :--- |
| Categoria | Nivel y género del atleta Escolar Femenino, Escolar Masculino, Nacional Adulto Femenino, Nacional Adulto Masculino. |
| Prueba | Disciplina de salto (Salto Largo, Salto Garrocha, Salto Alto). |
| Marca | Resultado obtenido por el atleta (no utilizado en el conteo, pero parte de la fuente). |
| Año | Año de la competencia (2023, 2024, 2025). |
| Competencia | Nombre del evento deportivo Nacional Escolar o Adulto. |
| Nombre Atleta | Identificador del atleta Clave para el conteo único. |

**Procesamiento Específico (CSV de salida):**
La base de datos original fue procesada para crear el *dataframe* final utilizado en la visualización, conteniendo solo las pruebas de salto.

---

### 3. Ejemplos de Preguntas que Responde la Visualización

La visualización generada permite responder:
* **Magnitud de la Brecha:** ¿Cuántos atletas más hay en Salto Largo que en Salto Garrocha en la categoría **Escolar Femenino**?
* **Distribución de la Escasez:** ¿En qué categoría se concentra la menor participación absoluta en Salto Garrocha?
* **Comparación de Género:** ¿La diferencia de participación entre Salto Largo y Salto Garrocha es proporcionalmente mayor en categorías masculinas o femeninas?
