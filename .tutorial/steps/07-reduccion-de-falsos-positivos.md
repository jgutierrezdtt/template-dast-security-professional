# Paso 7. Reduccion de falsos positivos

## Objetivo de aprendizaje

Configurar el escaneo DAST para que apunte al contexto correcto y produzca señales útiles.

## Archivo y seccion que debes modificar

- Archivo objetivo: `zap/config.yaml`.
- Seccion donde aplicar el cambio: contexto y política del escaneo.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
context:
  name: app-context
  include:
    - https://example.test/.*
authentication:
  method: form
scan:
  fail_on_risk: high
```

## Como adaptarlo correctamente

- Usa expresiones include/exclude coherentes con el alcance real del sistema.
- Solo activa autenticación si el paso realmente la necesita.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-07.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `context:` en `zap/config.yaml`.
- Debe encontrar el marcador `name: app-context` en `zap/config.yaml`.
- Debe encontrar el marcador `include:` en `zap/config.yaml`.
- Debe encontrar el marcador `authentication:` en `zap/config.yaml`.
- Debe encontrar el marcador `scan:` en `zap/config.yaml`.
- Debe encontrar el marcador `fail_on_risk: high` en `zap/config.yaml`.

## Criterio de finalizacion

El paso 7 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 8.
