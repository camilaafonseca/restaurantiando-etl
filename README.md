# 🍽️ Restaurantiando — ETL para Modelo de Recomendación

**Restaurantiando** es una página web que usa un modelo de Machine Learning para recomendar un restaurante y la ruta más óptima basada en las preferencias y ubicación del usuario.

Este repositorio contiene el proceso de ETL (Extracción, Transformación y Carga) que construyó la base de datos que alimenta dicho modelo.

---

## 📌 Contexto y Objetivo

La necesidad de construir esta base de datos surge porque el modelo requería cubrir cuatro zonas específicas: **Chía, Cajicá, Tenjo y Tabio**. La fuente de información fue TripAdvisor, ya que permitió obtener toda la data necesaria para llenar los campos base y clasificar las categorías requeridas para que el modelo pueda hacer recomendaciones precisas. Sin esta base de datos, el modelo no tendría información sobre qué recomendar.

---

## 🛠️ Stack Técnico

| Etapa | Herramienta |
|---|---|
| Extracción | Web Scraper (extensión de Chrome), Apify |
| Transformación y limpieza | Power Query |
| Clasificación | Python (pandas, numpy) en Google Colab |
| Entrega | Google Sheets |

---

## 🔄 Proceso Paso a Paso

1. **Extracción inicial** — Se configuró un bot en Web Scraper para extraer el nombre y el link de los restaurantes de los cuatro municipios.
2. **Unificación de fuentes** — Se descargaron los archivos en formato CSV y se unieron en Power Query usando *append* para consolidar los datos de los cuatro municipios en una sola fuente.
3. **Extracción de datos completos** — Se usó Apify con los links recopilados para extraer toda la *raw data* disponible de cada restaurante en TripAdvisor.
4. **Limpieza y estandarización** — Se descargó el archivo en Excel y se usó Power Query para limpiar columnas, estandarizar nombres y dar formato a los datos.
5. **Clasificación con Python** — En un cuaderno de Google Colab se utilizó Python para clasificar las categorías necesarias para el modelo de ML: tipo de establecimiento, especialidad gastronómica y momentos de consumo.
6. **Integración final** — Se descargaron las tablas clasificadas y se realizaron *left joins* en Power Query para consolidar toda la información en una sola tabla.
7. **Entrega** — La base de datos final con 120 registros se subió a Google Sheets para uso del equipo encargado del modelo de Machine Learning.

---

---

## 👩‍💻 Autora

**Camila** — Analista de Datos  
Herramientas: Excel · Power Query · Python · SQL · Power BI
