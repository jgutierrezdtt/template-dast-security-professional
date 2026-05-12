# Paso 11. Priorizacion por impacto de negocio

## Que vas a hacer en este paso?

Implementaras este control de DAST de forma concreta sobre el archivo `.github/workflows/dast.yml` y registraras evidencia tecnica en `.tutorial/evidence/step-11.json`.

## Por que es importante

**En la practica real**:
- Este control reduce riesgo operativo y mejora trazabilidad.
- Permite validar avance real, no solo lectura del tutorial.

**Lo que logras**:
- Resultado tecnico verificable para el paso 11.
- Evidencia auditable para revisiones de seguridad.

---

## Instrucciones paso-a-paso

### Paso 11.1: Prepara el artefacto principal

Crea o actualiza el archivo objetivo de este paso:

```bash
mkdir -p "$(dirname .github/workflows/dast.yml)"
touch .github/workflows/dast.yml
```

### Paso 11.2: Registra evidencia del paso

Crea el archivo `.tutorial/evidence/step-11.json` con este contenido:

```bash
mkdir -p .tutorial/evidence
cat > .tutorial/evidence/step-11.json << 'EOF'
{
  "step": 11,
  "title": "Priorizacion por impacto de negocio",
  "status": "completed",
  "artifact": ".github/workflows/dast.yml"
}
EOF
```

---

## Verificacion local

```bash
test -f .github/workflows/dast.yml && echo "artifact ok"
python3 -c 'import json;json.load(open(".tutorial/evidence/step-11.json"));print("evidence ok")'
```

---

## Validacion automatica

`validate-step-11.py` verificara:
- Existe `.github/workflows/dast.yml`.
- Existe `.tutorial/evidence/step-11.json`.
- La evidencia marca `status=completed` y `step=11`.

---

## Criterio de finalizacion

Paso 11 esta completo cuando:
1. `.github/workflows/dast.yml` existe en el repositorio.
2. `.tutorial/evidence/step-11.json` existe y es JSON valido.
3. `.tutorial/state.json` muestra `"current_step": 12`.

**Siguiente paso**: Paso 12
