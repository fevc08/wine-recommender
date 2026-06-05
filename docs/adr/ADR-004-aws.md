# ADR-004: AWS como plataforma de deploy

## Estado
Aceptado

## Fecha
2026-06-05

## Contexto
Necesitamos una plataforma para desplegar la aplicación 
en producción, accesible públicamente y con capacidad 
de escalar.

## Opciones consideradas
1. **AWS** — líder del mercado en cloud
2. **Google Cloud Platform** — alternativa sólida
3. **Railway** — plataforma simplificada
4. **Render** — usado en versión anterior

## Decisión
Usamos **AWS** (EC2 + RDS + S3).

## Razones
- Estándar de la industria — experiencia transferible
- Compatible con beca Talento Digital (Arquitectura Cloud)
- EC2 para la aplicación, RDS para PostgreSQL, 
  S3 para imágenes de vinos
- Free tier disponible para MVP
- Experiencia en AWS es altamente valorada en el mercado

## Por qué no las otras
- GCP: válida alternativa, pero AWS tiene mayor adopción 
  en Chile
- Railway/Render: excelentes para prototipo, limitados 
  para producción real

## Consecuencias
- Mayor curva de aprendizaje que Railway o Render
- Requiere configuración de IAM, VPC, Security Groups
- Costo potencial si se supera el free tier
- La beca de Arquitectura Cloud ayudará con este aprendizaje
