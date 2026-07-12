# proyecto_etl_delivery
## 📌 Contexto del Proyecto

El CEO de la startup requiere información clave antes de invertir en la expansión. Este proyecto responde a las siguientes interrogantes sobre los competidores existentes:
* ¿Dónde hay mayor penetración de mercado (más restaurantes)?
* ¿El mercado es tan caro como se cree?
* ¿Un precio más alto significa realmente mejor calidad?

## 🛠️ Tecnologías y Herramientas

* **Python:** Pandas, Glob
* **Base de Datos:** SQLite, SQLAlchemy
* **Visualización de Datos:** Matplotlib, Seaborn
* **Entorno:** Jupyter Notebook

## ⚙️ Arquitectura del Pipeline ETL

El proyecto se estructura en un pipeline completo:

1.  **Extract (Extracción):** Lectura de un catálogo maestro de restaurantes y carga dinámica de más de 800,000 ítems de menú particionados en múltiples archivos mediante `glob`.
2.  **Transform (Transformación):** * Mapeo y traducción de categorías de precio.
    * Ingeniería de características: Separación de direcciones complejas en calle, ciudad y código postal.
    * Limpieza y conversión de tipos de datos (precios textuales a numéricos).
    * Filtro de calidad: Selección de restaurantes "consolidados" (más de 100 reseñas) para optimizar memoria y análisis.
3.  **Load (Carga):** Almacenamiento del conjunto de datos procesado y unificado en una base de datos local SQLite, dejándola disponible para analistas.
4.  **Business Intelligence (Análisis):** Ejecución de consultas SQL y generación de visualizaciones para entregar *insights* accionables al CEO.

## ✅ Resultados y Conclusiones

* **Integración Exitosa:** Se consolidaron exitosamente dos fuentes crudas de datos en un único *master dataset* en SQL.
* **Optimización:** El filtrado inteligente redujo la carga de procesamiento enfocándose solo en restaurantes establecidos.
* **Insights Geográficos:** Se identificaron las 5 ciudades con mayor concentración de competencia (ej. Milwaukee y Seattle).
* **Análisis de Precios:** Se desmintió la percepción de un mercado excesivamente costoso; la gran mayoría de la oferta se concentra en el segmento "Económico".
