# ADR-001: FastAPI como framework backend

## Estado
Aceptado

## Fecha
2026-06-05

## Contexto
Necesitamos un framework Python para exponer el modelo 
de recomendación de vinos como API REST, consumible 
desde un frontend React y potencialmente desde 
sistemas externos (ej: CAV u otras viñas).

## Opciones consideradas
1. **FastAPI** — framework moderno, async, tipado
2. **Flask** — framework minimalista, ampliamente usado
3. **Django REST Framework** — framework completo, más pesado
4. **Streamlit** — usado en versión anterior del proyecto

## Decisión
Usamos **FastAPI**.

## Razones
- Performance superior gracias a async/await nativo
- Documentación automática (Swagger UI en /docs)
- Validación de datos con Pydantic integrada
- Tipado estático reduce errores en producción
- Curva de aprendizaje menor que Django
- Ideal para servir modelos de ML como microservicio

## Por qué no las otras
- Flask: requiere más configuración manual para validación
- Django: demasiado pesado para una API de ML
- Streamlit: no es una API REST, no es consumible 
  por otros sistemas

## Consecuencias
- El equipo necesita aprender FastAPI y Pydantic
- Menos "batteries-included" que Django
- Excelente para escalar como microservicio en el futuro
