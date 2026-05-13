# Paso 7. Reduccion de falsos positivos

## Objetivo de aprendizaje

Este paso introduce la reducción de falsos positivos en DAST y debe dejar un cambio comprensible en `zap/config.yaml`.

## Que vas a cambiar y por que

Actualiza `zap/config.yaml` para que la reducción de falsos positivos quede explícita y revisable. En esta fase no estás documentando todavía una excepción formal, sino afinando el contexto del escaneo para que el ruido baje desde el origen: alcance correcto, autenticación coherente y un umbral de fallo entendible.

## Archivo y seccion que debes modificar

- Archivo objetivo: `zap/config.yaml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
context:
  name: app-context
include:
  - http://localhost:3000/.*
authentication:
  type: form
scan:
  fail_on_risk: high
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `include:` para evitar rutas que solo generan ruido y no aportan evidencia de riesgo.
- Mantén `authentication:` coherente con la aplicación para no provocar hallazgos falsos por flujos incompletos o respuestas inesperadas.
- Conserva `fail_on_risk: high` como umbral claro mientras afinas la señal del escaneo.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El lector entiende que reducir falsos positivos empieza por configurar bien el escaneo, no solo por ignorar alertas después.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-07.py` comprueba este paso contra el archivo configurado.
- El workflow busca `context:` dentro de `zap/config.yaml`.
- El workflow busca `name: app-context` dentro de `zap/config.yaml`.
- El workflow busca `include:` dentro de `zap/config.yaml`.
- El workflow busca `authentication:` dentro de `zap/config.yaml`.
- El workflow busca `scan:` dentro de `zap/config.yaml`.
- El workflow busca `fail_on_risk: high` dentro de `zap/config.yaml`.

## Criterio de finalizacion

El paso 7 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 8.
