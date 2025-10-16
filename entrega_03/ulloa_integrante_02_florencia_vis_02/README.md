# README – Entrega 03 Individual  
**Autora:** Florencia Ulloa  
**Visualización:** Brecha de rendimiento entre atletas escolares y adultos en 800 metros planos  
**Librería utilizada:** Altair (Python)  
**Período analizado:** 2023–2025  

---

## 1. Descripción general

Este trabajo forma parte del proyecto grupal sobre la evolución del rendimiento atlético en Chile, con foco en la comparación entre etapas escolares y adultas.  
La subhistoria individual se centra en **cómo varía la brecha de rendimiento entre atletas escolares (JDE) y adultos (Campeonato Nacional)** en la prueba de **800 metros planos**, observando su evolución entre los años 2023 y 2025.

---

## 2. Hipótesis personal

> El atletismo masculino tiende a reducir la brecha de rendimiento entre la etapa escolar y adulta entre los años 2023 y 2025.

---

## 3. Preguntas que guía la visualización

- ¿Cuánto difieren los tiempos promedio entre atletas escolares y adultos en la prueba de 800 metros?  
- ¿Esa diferencia se mantiene o se reduce con el paso de los años?  
- ¿Qué tanto se acercan los registros escolares al estándar adulto en la categoría masculina?

---

## 4. Proceso de trabajo

### a) Selección de base
Se utilizó la base limpia `Florencia_database_limpia.csv`, derivada de resultados oficiales del IND y Fedachi (ver ficha técnica).  
De ella se seleccionaron exclusivamente los registros correspondientes a la prueba “800m” y al sexo masculino.

### b) Limpieza y procesamiento
1. Filtrado de registros por `prueba == "800m"` y `sexo == "Hombre"`.  
2. Eliminación de marcas no válidas (`valido == 0`).  
3. Conversión de todos los resultados a segundos.  
4. Agrupación por `anio` y `competencia` para obtener el promedio anual.  
5. Cálculo de la **brecha promedio**: diferencia entre el tiempo medio de atletas escolares y adultos para cada año.

### c) Visualización
Se construyó un **gráfico de líneas** con Altair, donde:
- El eje X representa los años (2023–2025).  
- El eje Y muestra los tiempos promedio en segundos.  
- Las líneas comparan a atletas escolares y adultos.  
- Se añadió una capa adicional con la brecha porcentual.

El gráfico busca **mostrar la tendencia de cierre de brecha** a lo largo del tiempo, evidenciando si los atletas jóvenes se aproximan al rendimiento adulto.

---

## 5. Ejemplo de preguntas que puede responder

- ¿Qué tan significativa es la mejora del grupo escolar entre 2023 y 2025?  
- ¿Cuánto más rápidos son los adultos en promedio cada año?  
- ¿Se observan convergencias o divergencias entre ambos grupos?  

---

## 6. Archivos asociados

- `visualizacion/vis_01.html` → Visualización interactiva en Altair  
- `visualizacion/vis_01.jpg` → Captura estática  
- `visualizacion/cronica.md` → Texto narrativo que acompaña la visualización  
- `scripts/codigo_para_visualizar_1.ipynb` → Notebook con procesamiento y generación de la visualización  
- `Ficha_Técnica.md` → Documento técnico de la base de datos  
- `Florencia_database_limpia.csv` → Fuente de datos utilizada

---

## 7. Observaciones

La visualización permite ver que la **diferencia entre los promedios escolares y adultos disminuye progresivamente**, lo que puede asociarse a un **mayor nivel competitivo en el ámbito escolar** y una **mejor transición hacia el alto rendimiento**.  
El objetivo final es integrar esta pieza a la webstory grupal, destacando cómo la brecha de rendimiento se acorta con el tiempo y qué factores podrían explicarlo.

---
