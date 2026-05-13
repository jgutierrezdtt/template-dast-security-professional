# Paso 23. Cobertura de rutas criticas

## Objetivo de aprendizaje

Este paso introduce la cobertura de rutas críticas en DAST y debe dejar un cambio comprensible en `zap/config.yaml`.

## Que vas a cambiar y por que

Actualiza `zap/config.yaml` para que la cobertura de rutas críticas quede explícita y revisable. El punto importante del paso es que `include:` represente de verdad los flujos más sensibles de la aplicación y que autenticación y severidad acompañen ese foco, en lugar de dejar el escaneo repartido sobre rutas menos relevantes.

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
- Usa `include:` para reflejar rutas que realmente importan para autenticación, datos o transacciones.
- Mantén `authentication:` porque muchas rutas críticas solo aparecen dentro de sesión.
- Conserva `fail_on_risk: high` para que la cobertura ampliada siga vinculada a una respuesta operativa clara.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende que el escaneo está orientado a las rutas con mayor valor o riesgo.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-23.py` comprueba este paso contra el archivo configurado.
- El workflow busca `context:` dentro de `zap/config.yaml`.
- El workflow busca `name: app-context` dentro de `zap/config.yaml`.
- El workflow busca `include:` dentro de `zap/config.yaml`.
- El workflow busca `authentication:` dentro de `zap/config.yaml`.
- El workflow busca `scan:` dentro de `zap/config.yaml`.
- El workflow busca `fail_on_risk: high` dentro de `zap/config.yaml`.

## Criterio de finalizacion

El paso 23 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 24.
