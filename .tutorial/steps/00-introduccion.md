# Paso 0. Introducción

Este laboratorio está pensado para practicar DAST desde una perspectiva profesional. No se trata solo de lanzar un escaneo contra una aplicación, sino de aprender a configurar contexto, autenticación, alcance, priorización y reporting para que el resultado sea operable por un equipo real.

## Qué vas a trabajar

Durante el recorrido vas a pasar por varias decisiones que suelen marcar la diferencia entre un escaneo puntual y un programa DAST útil:

- definición de la aplicación objetivo y su superficie de ataque
- primer escaneo y lectura crítica de resultados
- configuración de contexto, autenticación y scope
- gestión de falsos positivos y excepciones
- uso de hallazgos para priorización, baseline, regresiones y gates
- reporting técnico y ejecutivo según audiencia

## Qué problema intenta resolver este laboratorio

DAST suele degradarse cuando se usa sin criterio operativo. Los problemas más comunes son:

- escaneos demasiado amplios o mal autenticados
- mucho ruido y poca capacidad de priorización
- excepciones abiertas sin seguimiento
- gates mal calibrados que o bien no sirven o bien bloquean de más
- reporting que no ayuda a decidir qué corregir primero

Este tutorial está orientado precisamente a corregir esas prácticas.

## Cómo se recorre el tutorial

El orden del recorrido importa. Primero construyes una base de escaneo comprensible, luego mejoras profundidad y precisión, después gestionas excepciones y priorización, y finalmente conviertes el programa en algo gobernable con métricas, reporting y revisión de calidad.

## Qué conviene tener claro antes de empezar

- un escaneo más grande no implica un escaneo mejor
- autenticación y scope definen buena parte de la calidad del resultado
- un hallazgo sin contexto rara vez se traduce en remediación efectiva
- DAST profesional requiere decidir qué hallazgos bloquean, cuáles se aceptan temporalmente y cuáles solo informan

## Siguiente paso

El botón **Empezar tutorial** abre directamente el paso 1.
