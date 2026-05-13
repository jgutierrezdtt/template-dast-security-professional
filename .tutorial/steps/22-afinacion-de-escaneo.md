# Paso 22. Afinacion de escaneo

## Objetivo de aprendizaje

Este paso introduce la afinación de escaneo en DAST y debe dejar un cambio comprensible en `zap/config.yaml`.

## Que vas a cambiar y por que

Actualiza `zap/config.yaml` para que la afinación del escaneo quede explícita y revisable. Aquí el foco está en usar la misma base de contexto, alcance, autenticación y severidad para mostrar que un buen escaneo no depende solo de ejecutarse, sino de estar calibrado para producir señal útil.

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
- Usa `include:` y `authentication:` para reflejar una configuración afinada y coherente con el objetivo.
- Conserva `fail_on_risk: high` para que la afinación siga conectada con un criterio operativo claro.
- Piensa la afinación como ajuste de precisión y cobertura, no como simple aumento de volumen de pruebas.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende que el escaneo está mejor calibrado para generar hallazgos útiles.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-22.py` comprueba este paso contra el archivo configurado.
- El workflow busca `context:` dentro de `zap/config.yaml`.
- El workflow busca `name: app-context` dentro de `zap/config.yaml`.
- El workflow busca `include:` dentro de `zap/config.yaml`.
- El workflow busca `authentication:` dentro de `zap/config.yaml`.
- El workflow busca `scan:` dentro de `zap/config.yaml`.
- El workflow busca `fail_on_risk: high` dentro de `zap/config.yaml`.

## Criterio de finalizacion

El paso 22 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 23.
