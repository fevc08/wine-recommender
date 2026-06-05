# ADR-005: Wine Reviews (Kaggle) como dataset base

## Estado
Aceptado

## Fecha
2026-06-05

## Contexto
Necesitamos datos de vinos con características suficientes 
para entrenar un modelo de recomendación por maridaje.
La versión anterior del proyecto usó web scraping de CAV 
con joins artificiales para generar el dataset.

## Opciones consideradas
1. **Wine Reviews (Kaggle/Wine Enthusiast)** — 130K reseñas
2. **Scraping de CAV** — usado en versión anterior
3. **Vivino API** — datos de usuarios reales
4. **Dataset propio construido manualmente**

## Decisión
Usamos **Wine Reviews de Kaggle** como dataset base.

## Razones
- 130.000 reseñas reales de sommeliers profesionales
- Contiene: variedad, país, región, precio, puntuación, 
  descripción textual
- Las descripciones permiten inferir maridajes con NLP
- Público, gratuito y legal
- No depende de scraping que puede romperse o 
  generar problemas legales

## Problemas con la versión anterior
- Dataset inflado artificialmente con joins de género 
  y edad (variables irrelevantes para maridaje)
- Maridajes asignados manualmente desde libro, 
  no aprendidos de datos reales
- Dependencia de scraping de sitio de tercero (CAV)

## Plan de migración a datos reales
En versiones futuras, el sistema puede conectarse a 
la API de CAV o similares para mostrar vinos 
disponibles en Chile con precios actualizados.
El modelo de recomendación permanece independiente 
de la fuente de datos.

## Consecuencias
- Dataset en inglés — requiere traducción o mapeo 
  para interfaz en español
- No incluye vinos chilenos específicamente
- Las recomendaciones serán por variedad y 
  características, no por marca específica chilena
