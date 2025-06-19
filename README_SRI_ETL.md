
# Proyecto ETL y Visualización: Datos de Ventas del SRI 🇪🇨

Este proyecto realiza la recolección, limpieza, consolidación, análisis y visualización de datos económicos publicados por el Servicio de Rentas Internas (SRI) de Ecuador.

---

## 🧩 Estructura del proceso

### 1. Extracción automática con Selenium
- Se usa Selenium para automatizar la navegación en el sitio oficial del SRI.
- Se extraen todos los enlaces `.csv` desde la sección de datos abiertos.
- Solo se descargan archivos que inician con `sri_ventas`.
- Los archivos se guardan en la carpeta `/data`.

### 2. Unificación de archivos CSV
- Todos los archivos `sri_ventas*.csv` son leídos y unificados en un solo DataFrame.
- El archivo combinado se guarda como `sri_ventas_unido.csv` en la carpeta `/CSV_unido`.

### 3. Limpieza del archivo unificado
- Se detectó que el separador correcto es `|` y el encoding es `latin1`.
- Se seleccionan las columnas válidas (ventas, compras, exportaciones, etc.).
- Se convierten las columnas numéricas de texto a tipo `float`.
- Se crea una columna `FECHA` usando las columnas `AÑO` y `MES`.

### 4. Exploración de datos
- Se analiza estructura del DataFrame: tipos de datos, valores únicos.
- Se identifican problemas de parsing y se limpian filas erróneas.

### 5. Visualizaciones generadas
- Gráfico de ventas totales por año.
- Mapa de calor de ventas por provincia y mes.
- Comparativa anual de compras vs ventas.
- Top 10 provincias por exportaciones.

---

## ▶️ Cómo ejecutar este proyecto en Google Colab

1. **Sube el notebook `.ipynb`** que generamos (por ejemplo: `SRI_Extractor_Modular.ipynb`).
2. **Ejecuta las celdas en orden:**
   - Montaje de Drive (opcional)
   - Instalación de Selenium
   - Extracción de enlaces
   - Descarga de archivos CSV
   - Limpieza y unión de datos
   - Visualización de resultados

3. **Requisitos:**
   - Navegador Chrome en modo headless ya configurado por Colab
   - Conexión a internet para scraping y descarga
   - Archivo CSV limpio para análisis

---

## 🌱 Posibles mejoras

- Incorporar control de versiones por año en los archivos descargados.
- Subida automática a Google BigQuery con `pandas-gbq`.
- Paneles interactivos con `plotly` o `dash`.
- Detección de outliers y validación estadística.

---

**Creado por:** [Tu Nombre o Equipo]  
**Fecha:** Junio 2025  
