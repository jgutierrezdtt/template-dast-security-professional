# Paso 4. Escaneo autenticado

## Objetivo de aprendizaje

Un escaneo sin autenticación solo ve la superficie pública. Este paso enseña a ampliar la visibilidad hacia rutas que requieren sesión.

## Que vas a cambiar y por que

Configura el contexto del escaneo con autenticación para que la herramienta pueda acceder a zonas protegidas de la aplicación.

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
    - https://example.test/.*
authentication:
  method: form
scan:
  fail_on_risk: high
```

## Como adaptarlo correctamente

- Incluye solo las rutas que realmente forman parte del alcance del tutorial.
- Describe o representa el método de autenticación sin exponer credenciales reales.
- No conviertas el paso en un dump de configuración; céntrate en el contexto y la autenticación.

## Que deberia verse al terminar

- La configuración incluye una sección de `authentication`.
- Se ve un contexto o include claro para el escaneo autenticado.
- El alcance autenticado está separado del escaneo genérico.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-04.py` comprueba este paso contra el archivo configurado.
- El workflow busca `context:` dentro de `zap/config.yaml`.
- El workflow busca `name: app-context` dentro de `zap/config.yaml`.
- El workflow busca `include:` dentro de `zap/config.yaml`.
- El workflow busca `authentication:` dentro de `zap/config.yaml`.
- El workflow busca `scan:` dentro de `zap/config.yaml`.
- El workflow busca `fail_on_risk: high` dentro de `zap/config.yaml`.

## Criterio de finalizacion

El paso 4 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 5.
