# Paso 9. Excepciones con caducidad

## Objetivo de aprendizaje

Este paso introduce las excepciones con caducidad en DAST y debe dejar un cambio comprensible en `docs/dast-exceptions.yml`.

## Que vas a cambiar y por que

Actualiza `docs/dast-exceptions.yml` para que las excepciones no queden abiertas indefinidamente. La diferencia clave de este paso es que `expires_on:` deja de ser un dato decorativo y pasa a representar una fecha real de revisión o retirada de la aceptación temporal del riesgo.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dast-exceptions.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
exceptions:
  - alert: Missing Anti-CSRF Tokens
    path: /profile
    reason: Mitigacion parcial en curso
    expires_on: 2026-12-31
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `expires_on:` con una fecha concreta y revisable, no con un texto abierto o indefinido.
- Mantén `reason:` conectado con una situación temporal: deuda aceptada, mitigación parcial o corrección planificada.
- Evita que `path:` y `alert:` definan una excepción demasiado amplia, porque eso hace irrelevante la fecha de caducidad.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La excepción ya obliga a una revisión futura en lugar de convertirse en una aceptación permanente.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-09.py` comprueba este paso contra el archivo configurado.
- El workflow busca `exceptions:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `alert:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `path:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `reason:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `expires_on:` dentro de `docs/dast-exceptions.yml`.

## Criterio de finalizacion

El paso 9 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 10.
