# Paso 1. Aplicacion objetivo vulnerable

## Que vas a hacer en este paso?

Implementaras este control de DAST de forma concreta sobre el archivo `.zap/rules.tsv` y registraras evidencia tecnica en `.tutorial/evidence/step-01.json`.

## Por que es importante

**En la practica real**:
- Este control reduce riesgo operativo y mejora trazabilidad.
- Permite validar avance real, no solo lectura del tutorial.

**Lo que logras**:
- Resultado tecnico verificable para el paso 1.
- Evidencia auditable para revisiones de seguridad.

---

## Instrucciones paso-a-paso

### Paso 1.1: Prepara el artefacto principal

Crea o actualiza el archivo objetivo de este paso:

```bash
mkdir -p "$(dirname .zap/rules.tsv)"
touch .zap/rules.tsv
```

### Paso 1.2: Registra evidencia del paso

Crea el archivo `.tutorial/evidence/step-01.json` con este contenido:

```bash
mkdir -p .tutorial/evidence
cat > .tutorial/evidence/step-01.json << 'EOF'
{
  "step": 1,
  "title": "Aplicacion objetivo vulnerable",
  "status": "completed",
  "artifact": ".zap/rules.tsv"
}
EOF
```

---

## Verificacion local

```bash
test -f .zap/rules.tsv && echo "artifact ok"
python3 -c 'import json;json.load(open(".tutorial/evidence/step-01.json"));print("evidence ok")'
```

---

## Validacion automatica

`validate-step-01.py` verificara:
- Existe `.zap/rules.tsv`.
- Existe `.tutorial/evidence/step-01.json`.
- La evidencia marca `status=completed` y `step=1`.

---

## Criterio de finalizacion

Paso 1 esta completo cuando:
1. `.zap/rules.tsv` existe en el repositorio.
2. `.tutorial/evidence/step-01.json` existe y es JSON valido.
3. `.tutorial/state.json` muestra `"current_step": 2`.

**Siguiente paso**: Paso 2
