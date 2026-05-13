# Paso 8. Excepciones documentadas

## Objetivo de aprendizaje

Este paso introduce las excepciones documentadas en DAST y debe dejar un cambio comprensible en `docs/dast-exceptions.yml`.

## Que vas a cambiar y por que

Actualiza `docs/dast-exceptions.yml` para que una excepción quede explícita, trazable y revisable. En un programa DAST serio no basta con ignorar una alerta: necesitas dejar claro qué alerta se acepta temporalmente, en qué ruta aparece, por qué se acepta y hasta cuándo.

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
- Usa `alert:` para identificar el hallazgo aceptado y no una categoría ambigua.
- Usa `path:` para limitar la excepción a la superficie concreta afectada.
- Haz que `reason:` explique la decisión temporal y que `expires_on:` fuerce revisión posterior.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La excepción parece gobernada y revisable, no escondida.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-08.py` comprueba este paso contra el archivo configurado.
- El workflow busca `exceptions:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `alert:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `path:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `reason:` dentro de `docs/dast-exceptions.yml`.
- El workflow busca `expires_on:` dentro de `docs/dast-exceptions.yml`.

## Criterio de finalizacion

El paso 8 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 9.
