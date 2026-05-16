# Business Analytics — Retail Sales (Forecast + Promo Impact)

Proyecto final de Business Analytics orientado a retail: análisis exploratorio, modelado predictivo y propuesta de experimento para validar el impacto de promociones en ventas semanales.

## Objetivo
- Analizar qué factores influyen en las ventas semanales y construir un modelo de regresión para estimarlas.
- Traducir hallazgos analíticos a decisiones de negocio (planificación, promociones, inventario).

> Dataset simulado con foco en Walmart (45 tiendas) e indicadores contextuales (macro + comerciales).  
> Se incorpora dependencia temporal vía ventas rezagadas (ventas_lag_1).  
> El modelo lineal alcanza R² ≈ 0.90. 

## Enfoque
1. **EDA**
   - Distribución de ventas, faltantes (NaN en descuentos interpretados como ausencia de promo → imputación 0).
   - Correlaciones y chequeo de multicolinealidad.
2. **Feature engineering**
   - Estacionalidad (mes/semana) + feature temporal **ventas_lag_1**.
3. **Modelo**
   - Regresión lineal para estimar ventas semanales.
   - Insights: persistencia temporal fuerte y efecto positivo de promociones/descuentos. 
4. **Causalidad**
   - Diseño de experimento A/B (grupo control vs tratamiento) para validar impacto real de promociones. 

## Resultados (resumen)
- **R²: 0.9021** (mejora significativa al incluir ventas_lag_1).
- El modelo tiende a subestimar ventas muy altas (limitación típica de linealidad / outliers).
- Conclusión ejecutiva: ventas impulsadas principalmente por dinámica histórica + acciones promocionales. 

## Contenido del repo
- `notebooks/`: notebook reproducible del análisis.
- `docs/`: presentación final (deck) + graficos en Power BI.
- `src/`: CSVs en formato original para la preparación de datos, features y entrenamiento.

## Cómo correr
### Opción 1 — pip
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
