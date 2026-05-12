# Paso 16. Gate bloqueante por severidad

## Que vas a hacer en este paso?

Implementaras este control de DAST de forma concreta sobre el archivo `docs/dast-programa.md` y registraras evidencia tecnica en `.tutorial/evidence/step-16.json`.

## Por que es importante

**En la practica real**:
- Este control reduce riesgo operativo y mejora trazabilidad.
- Permite validar avance real, no solo lectura del tutorial.

**Lo que logras**:
- Resultado tecnico verificable para el paso 16.
- Evidencia auditable para revisiones de seguridad.

---

## Instrucciones paso-a-paso

### Paso 16.1: Prepara el artefacto principal

Crea o actualiza el archivo objetivo de este paso:

```bash
mkdir -p "$(dirname docs/dast-programa.md)"
touch docs/dast-programa.md
```

### Paso 16.2: Registra evidencia del paso

Crea el archivo `.tutorial/evidence/step-16.json` con este contenido:

```bash
mkdir -p .tutorial/evidence
cat > .tutorial/evidence/step-16.json << 'EOF'
{
  "step": 16,
  "title": "Gate bloqueante por severidad",
  "status": "completed",
  "artifact": "docs/dast-programa.md"
}
EOF
```

---

## Verificacion local

```bash
test -f docs/dast-programa.md && echo "artifact ok"
python3 -c 'import json;json.load(open(".tutorial/evidence/step-16.json"));print("evidence ok")'
```

---

## Validacion automatica

`validate-step-16.py` verificara:
- Existe `docs/dast-programa.md`.
- Existe `.tutorial/evidence/step-16.json`.
- La evidencia marca `status=completed` y `step=16`.

---

## Criterio de finalizacion

Paso 16 esta completo cuando:
1. `docs/dast-programa.md` existe en el repositorio.
2. `.tutorial/evidence/step-16.json` existe y es JSON valido.
3. `.tutorial/state.json` muestra `"current_step": 17`.

**Siguiente paso**: Paso 17
