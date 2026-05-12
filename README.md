# DAST Security Professional

Tutorial profesional de Dynamic Application Security Testing (DAST).

## Objetivo

Aprender a operar un programa DAST profesional: configuración de escaneos, autenticación, gestión de hallazgos, priorización por riesgo, excepciones y reporting operativo.

## Audiencia

Equipos de AppSec, QA de seguridad y DevSecOps que necesiten integrar pruebas dinámicas en el ciclo de entrega continua.

## Requisitos previos

- Conocimientos intermedios de Git y Pull Request.
- Experiencia básica con pipelines CI/CD.
- Nociones de pruebas de seguridad web.

## Herramientas utilizadas

- OWASP ZAP (o equivalente DAST)
- GitHub Actions
- Scripts de validación del curso

## Inicio del tutorial

[Empezar tutorial](https://github.com/new?template_name=template-dast-security-professional&template_owner=jgutierrezdtt)

## Acceso al repositorio

- [Crear mi repositorio desde este template](https://github.com/new?template_name=template-dast-security-professional&template_owner=jgutierrezdtt)
- [Volver al portal general](https://github.com/jgutierrezdtt/security-learning-portal)

## Gestión del progreso

- [Validar progreso](../../actions/workflows/validate.yml)
- [Probar integridad del tutorial](../../actions/workflows/test-tutorial.yml)
- [Ejecutar tests funcionales del tutorial](../../actions/workflows/functional-tests.yml)
- [Reiniciar tutorial](../../actions/workflows/reset-tutorial.yml)
- [Ver pasos del tutorial](./.tutorial/steps/)

## Tabla de pasos

| Paso | Tema |
| --- | --- |
| 0 | Introducción |
| 1 | Aplicación objetivo vulnerable |
| 2 | Primer escaneo DAST |
| 3 | Interpretación de resultados |
| 4 | Escaneo autenticado |
| 5 | Configuración de contexto |
| 6 | Configuración de scope |
| 7 | Reducción de falsos positivos |
| 8 | Excepciones documentadas |
| 9 | Excepciones con caducidad |
| 10 | Priorización por criticidad |
| 11 | Priorización por impacto de negocio |
| 12 | Baseline de hallazgos |
| 13 | Detección de regresiones |
| 14 | Integración en GitHub Actions |
| 15 | Gate no bloqueante |
| 16 | Gate bloqueante por severidad |
| 17 | Política organizativa |
| 18 | Revisión de excepciones vencidas |
| 19 | Métricas de hallazgos |
| 20 | Reporting ejecutivo |
| 21 | Reporting técnico |
| 22 | Afinación de escaneo |
| 23 | Cobertura de rutas críticas |
| 24 | Simulación de auditoría |
| 25 | Medalla final DAST Professional |

## Paso 0

El paso 0 describe el entorno, permisos y limitaciones del laboratorio. No bloquea el flujo: el botón principal abre directamente el paso 1.

## Actualización desde template

Este repositorio incluye `.template-version` y workflow de actualización para revisar cambios del template sin sobrescribir trabajo del usuario.

## Badge final

Al cerrar el curso se generan artefactos de finalización en:

- `.tutorial/badges/completion-badge.md`
- `.tutorial/badges/completion-badge.svg`
- `.tutorial/evidence/completion.json`

## Referencias

- [OWASP ZAP](https://www.zaproxy.org/)
- [GitHub Actions](https://docs.github.com/actions)
