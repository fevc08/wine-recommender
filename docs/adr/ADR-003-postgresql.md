# ADR-003: PostgreSQL como base de datos

## Estado
Aceptado

## Fecha
2026-06-05

## Contexto
Necesitamos almacenar el catálogo de vinos, maridajes 
y recomendaciones de forma persistente y consultable.

## Opciones consideradas
1. **PostgreSQL** — base de datos relacional robusta
2. **SQLite** — base de datos embebida, sin servidor
3. **MongoDB** — base de datos documental NoSQL
4. **MySQL** — base de datos relacional alternativa

## Decisión
Usamos **PostgreSQL**.

## Razones
- Estándar de la industria para aplicaciones en producción
- Soporte nativo en AWS RDS
- Excelente soporte para datos JSON (útil para atributos 
  de vinos variables)
- Compatible con SQLAlchemy (ORM de FastAPI)
- Free tier disponible en Railway y Supabase para desarrollo

## Por qué no las otras
- SQLite: no apto para producción con múltiples usuarios
- MongoDB: el esquema de vinos es relacional por naturaleza
- MySQL: PostgreSQL tiene mejor soporte en el ecosistema 
  Python/FastAPI

## Consecuencias
- Requiere servidor PostgreSQL en desarrollo y producción
- Docker Compose para desarrollo local
- AWS RDS en producción (costo adicional)
