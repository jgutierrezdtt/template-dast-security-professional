# Paso 4. Escaneo autenticado

## Objetivo de aprendizaje

Un escaneo sin autenticación solo ve la superficie pública. Este paso enseña a preparar `zap/config.yaml` para un contexto autenticado sin perder claridad sobre el alcance y el umbral de fallo.

## Que vas a cambiar y por que

Configura el contexto del escaneo con autenticación para que la herramienta pueda acceder a zonas protegidas de la aplicación. Aunque el validador sigue comprobando los mismos marcadores base de `context`, `include`, `authentication`, `scan` y `fail_on_risk: high`, en este paso debes interpretarlos ya como la base de un escaneo con sesión y no como un rastreo anónimo.

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
  method: form
scan:
  fail_on_risk: high
```

## Como adaptarlo correctamente

- Incluye solo las rutas que realmente forman parte del alcance del tutorial.
- Describe o representa el método de autenticación sin exponer credenciales reales.
- Usa `app-context` como nombre reconocible del contexto autenticado.
- Mantén visible `fail_on_risk: high` para que el gate siga siendo entendible mientras amplías cobertura.
- No conviertas el paso en un dump de configuración; céntrate en el contexto y la autenticación.

## Que deberia verse al terminar

- La configuración incluye una sección de `authentication`.
- Se ve un contexto o include claro para el escaneo autenticado.
- El alcance autenticado está separado del escaneo genérico.
- El lector entiende que la autenticación amplía visibilidad, pero no sustituye la necesidad de limitar scope y severidad.

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
