# Repositorio .github de la Organización

Este repositorio contiene los workflow templates de seguridad para toda la organización **BeaverSolucionesDigitales**.

## 📁 Estructura

```
.github/                          ← Repositorio: BeaverSolucionesDigitales/.github
└── workflow-templates/
    ├── trivy-security.yml
    ├── trivy-security.properties.json
    ├── semgrep-security.yml
    └── semgrep-security.properties.json
```

## 🚀 Configuración

### Paso 1: Crear el repositorio

1. Ve a GitHub → Tu organización → New repository
2. Nombre del repositorio: **`.github`** (exactamente así, con el punto)
3. Hazlo **público** (requerido para que los templates sean visibles)
4. Crea el repositorio

### Paso 2: Subir los archivos

```bash
# Clonar el nuevo repositorio
git clone https://github.com/BeaverSolucionesDigitales/.github.git
cd .github

# Crear la estructura
mkdir -p workflow-templates

# Copiar los archivos de workflow-templates/ a esta carpeta
# (los 4 archivos .yml y .properties.json)

# Commit y push
git add .
git commit -m "feat: add security workflow templates for organization"
git push origin main
```

### Paso 3: Verificar

1. Ve a cualquier repositorio de la organización
2. Actions → New workflow
3. Deberías ver los templates "Trivy Security Scan" y "Semgrep Security Audit" en la sección "By BeaverSolucionesDigitales"

## 📋 Workflow Templates Incluidos

### Trivy Security Scan
- **Función**: Escaneo de vulnerabilidades y secretos
- **Severidad**: HIGH y CRITICAL
- **Trigger**: Pull Request a la rama por defecto

### Semgrep Security Audit
- **Función**: Análisis estático de seguridad (SAST)
- **Reglas**: p/security-audit
- **Trigger**: Pull Request a la rama por defecto

## 🔧 Personalización

Los templates usan `$default-branch` que se reemplaza automáticamente por la rama principal de cada repo (main, master, etc.).

Para agregar más templates, crea:
1. `workflow-templates/nombre-workflow.yml` - El workflow
2. `workflow-templates/nombre-workflow.properties.json` - Los metadatos

## ⚠️ Notas Importantes

- El repositorio `.github` **debe ser público** para que los templates sean visibles en otros repos de la organización
- Los templates son **copias iniciales**, no se actualizan automáticamente
- Cada repo puede modificar su copia del template después de agregarlo
