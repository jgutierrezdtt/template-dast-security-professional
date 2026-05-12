# Paso 15. Gate no bloqueante

## Objetivo de aprendizaje

Ejecutar el escaneo automáticamente y decidir si bloquea el cambio según el riesgo.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/workflows/dast.yml`.
- Seccion donde aplicar el cambio: workflow del escaneo DAST.
- Resultado esperado: el repositorio incorpora el control de este paso de forma legible y revisable.

## Cambio que debes introducir

Copia este bloque como base y adáptalo al contexto real del repositorio:

```yaml
name: DAST
on:
  pull_request:
  push:
jobs:
  zap-scan:
    runs-on: ubuntu-latest
```

## Como adaptarlo correctamente

- Usa gate no bloqueante durante la afinación inicial.
- Activa bloqueo cuando el baseline y el ruido estén controlados.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-15.py` comprueba el archivo y los marcadores esperados de este paso.
- Debe encontrar el marcador `name: DAST` en `.github/workflows/dast.yml`.
- Debe encontrar el marcador `pull_request:` en `.github/workflows/dast.yml`.
- Debe encontrar el marcador `push:` en `.github/workflows/dast.yml`.
- Debe encontrar el marcador `zap-scan:` en `.github/workflows/dast.yml`.

## Criterio de finalizacion

El paso 15 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 16.
