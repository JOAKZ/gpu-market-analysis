# Main Street vs. Wall Street: The GPU Market Disconnect (2022-2024)

## Resumen del Proyecto
Este proyecto de análisis de datos explora la relación estadística entre el mercado financiero corporativo y el mercado físico de hardware de consumo. 

Tras eventos macroeconómicos disruptivos como el fin de la minería de Ethereum ("The Merge") y el boom de la Inteligencia Artificial, existe la creencia popular de que Wall Street dicta los precios de los componentes tecnológicos en tiempo real. A través de pruebas de correlación cruzada (*Cross-Correlation*) y análisis de volatilidad, este proyecto desmitifica esa causalidad directa y demuestra cómo los mercados operan mediante **rezagos estructurales (lags)** e indicadores adelantados.

👉 **[Ver Dashboard Interactivo en Tableau](https://public.tableau.com/app/profile/joaquin.carnota/viz/MainStreetvs_WallStreetTheGPUMarketDisconnect2022-2024/Title)**

## Herramientas y Tecnologías Utilizadas
* **Lenguaje:** Python
* **Procesamiento y Análisis:** Pandas, SciPy (Estadística inferencial, Pearson r, p-values)
* **Base de Datos:** PostgreSQL (SQLAlchemy)
* **Visualización:** Tableau Public
* **Entorno:** Jupyter Notebook

## Hallazgos Clave

1. **NVIDIA (Inercia corporativa e IA):** Su valoración en bolsa funciona como un **indicador adelantado de 3 meses** para los precios *retail* de la línea GeForce. Se mueven en tándem no por causalidad directa, sino por el impulso macroeconómico de la IA y la inercia de la cadena de suministro.
2. **AMD (Desacople y "Efecto Resaca"):** Totalmente desacoplada de la bolsa. Su cotización depende de la oferta y demanda del consumidor final. Sufrió un colapso de precios con **2 meses de retraso** frente a la caída de Ethereum, producto de la liquidación masiva de inventario post-minería.
3. **La Brecha de Volatilidad:** Mientras los activos especulativos (ETH y acciones) sufrieron fluctuaciones extremas (CV > 60%), el mercado físico secundario de NVIDIA funcionó como un ancla de estabilidad, siendo casi 10 veces menos volátil que Ethereum.

## Estructura del Repositorio
* `data_clean.ipynb`: Pipeline de extracción, limpieza, normalización de datos y carga a PostgreSQL.
* `data_gpus_market_analysis.ipynb`: Análisis estadístico, pruebas de hipótesis (P-values), aplicación de *lags* temporales y cálculo de Coeficiente de Variación (CV).
* `/assets`: Capturas de pantalla de los dashboards generados en Tableau.
* Archivos `.csv`: Datasets limpios generados para la ingesta en Tableau.