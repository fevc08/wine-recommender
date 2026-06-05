# ADR-002: KNN como algoritmo de recomendación

## Estado
Aceptado

## Fecha
2026-06-05

## Contexto
Necesitamos un algoritmo para recomendar vinos según 
las preferencias del usuario (tipo de comida, precio, 
categoría de vino). El sistema debe ser explicable 
y mantenible.

## Opciones consideradas
1. **KNN (K-Nearest Neighbors)** — basado en similitud
2. **Random Forest** — ensemble de árboles de decisión
3. **Filtrado colaborativo** — basado en usuarios similares
4. **Reglas expertas** — sin ML, solo lógica de negocio

## Decisión
Usamos **KNN con StandardScaler**.

## Razones
- Explicable: "te recomendamos este vino porque es 
  similar a estos otros que coinciden con tu búsqueda"
- No requiere grandes volúmenes de datos de usuarios
- Fácil de actualizar cuando llegan nuevos vinos
- El dominio (vinos) se presta para similitud por 
  características: variedad, precio, región, puntuación
- StandardScaler necesario para que precio no domine 
  sobre otras variables

## Por qué no las otras
- Random Forest: menos explicable para el usuario final
- Filtrado colaborativo: requiere historial de usuarios, 
  no disponible en MVP
- Reglas expertas: no escala con nuevas variedades

## Consecuencias
- K óptimo debe determinarse con cross-validation
- El modelo debe reentrenarse cuando se agregan vinos
- Performance puede degradarse con datasets muy grandes
  (considerar Approximate KNN en versiones futuras)
