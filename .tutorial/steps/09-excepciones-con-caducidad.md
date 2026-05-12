# Paso 9. Excepciones con caducidad

## Objetivo de aprendizaje

Documentar hallazgos aceptados temporalmente o excluidos del escaneo.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/dast-exceptions.yml`.
- Seccion donde aplicar el cambio: registro de exclusiones y excepciones.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
exceptions:
  - alert: 10011
    path: /health
    reason: "endpoint controlado sin datos sensibles"
    expires_on: "2026-12-31"
```

## Como adaptarlo correctamente

- Vincula cada excepción a una alerta y a una ruta.
- No uses exclusiones amplias si basta con una ruta concreta.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-09.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `exceptions:` en `docs/dast-exceptions.yml`.
- Debe encontrar el marcador `alert:` en `docs/dast-exceptions.yml`.
- Debe encontrar el marcador `path:` en `docs/dast-exceptions.yml`.
- Debe encontrar el marcador `reason:` en `docs/dast-exceptions.yml`.
- Debe encontrar el marcador `expires_on:` en `docs/dast-exceptions.yml`.

## Criterio de finalizacion

El paso 9 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 10.
