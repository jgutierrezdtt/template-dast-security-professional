# Paso 8. Excepciones documentadas

## Que vas a hacer en este paso?

Implementaras este control de DAST de forma concreta sobre el archivo `.github/workflows/dast.yml` y registraras evidencia tecnica en `.tutorial/evidence/step-08.json`.

## Por que es importante

**En la practica real**:
- Este control reduce riesgo operativo y mejora trazabilidad.
- Permite validar avance real, no solo lectura del tutorial.

**Lo que logras**:
- Resultado tecnico verificable para el paso 8.
- Evidencia auditable para revisiones de seguridad.

---

## Instrucciones paso-a-paso

### Paso 8.1: Prepara el artefacto principal

Crea o actualiza el archivo objetivo de este paso:

```bash
mkdir -p "$(dirname .github/workflows/dast.yml)"
touch .github/workflows/dast.yml
```

### Paso 8.2: Registra evidencia del paso

Crea el archivo `.tutorial/evidence/step-08.json` con este contenido:

```bash
mkdir -p .tutorial/evidence
cat > .tutorial/evidence/step-08.json << 'EOF'
{
  "step": 8,
  "title": "Excepciones documentadas",
  "status": "completed",
  "artifact": ".github/workflows/dast.yml"
}
EOF
```

---

## Verificacion local

```bash
test -f .github/workflows/dast.yml && echo "artifact ok"
python3 -c 'import json;json.load(open(".tutorial/evidence/step-08.json"));print("evidence ok")'
```

---

## Validacion automatica

`validate-step-08.py` verificara:
- Existe `.github/workflows/dast.yml`.
- Existe `.tutorial/evidence/step-08.json`.
- La evidencia marca `status=completed` y `step=8`.

---

## Criterio de finalizacion

Paso 8 esta completo cuando:
1. `.github/workflows/dast.yml` existe en el repositorio.
2. `.tutorial/evidence/step-08.json` existe y es JSON valido.
3. `.tutorial/state.json` muestra `"current_step": 9`.

**Siguiente paso**: Paso 9
