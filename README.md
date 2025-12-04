# Lighthouse Audit Results Dashboard

Este repositorio contiene los resultados de las auditorías de Lighthouse realizadas en diferentes sitios web.

## Estructura

- `index.html` - Dashboard principal con todos los dominios analizados
- Cada directorio contiene los resultados de un dominio específico:
  - `audit.json` - Datos completos de la auditoría en formato JSON
  - `index.html` - Informe detallado HTML de Lighthouse
  - `report.xlsx` - Informe Excel con múltiples hojas
  - `site-info.json` - Información básica del sitio auditado

## Despliegue en GitHub Pages

### Configuración (MUY SIMPLE)

1. Ve a la configuración del repositorio en GitHub:
   - https://github.com/ixtia/lighthouse-audit-results/settings/pages

2. En la sección "Source":
   - Selecciona **Branch**: `main`
   - Selecciona **Folder**: `/` (root)
   - Haz clic en **Save**

3. ¡Listo! En unos minutos el sitio estará disponible en:
   - `https://ixtia.github.io/lighthouse-audit-results/`

El archivo `.nojekyll` asegura que GitHub Pages sirva los archivos estáticos sin procesamiento de Jekyll.

### Actualización automática

Para actualizar los resultados automáticamente después de cada auditoría:

1. Ejecuta el script de generación de índice desde el proyecto principal:
   ```bash
   node lib/generate-index.js ./output
   ```

2. Haz commit y push de los cambios:
   ```bash
   cd output
   git add .
   git commit -m "Update audit results"
   git push origin main
   ```

GitHub Pages se actualizará automáticamente en 1-2 minutos.

## Acceso

Una vez desplegado, el dashboard estará disponible en:
- `https://ixtia.github.io/lighthouse-audit-results/`

## API de Datos

Los datos JSON están disponibles directamente vía GitHub Raw:
- `https://raw.githubusercontent.com/ixtia/lighthouse-audit-results/main/{directorio}/audit.json`
- `https://raw.githubusercontent.com/ixtia/lighthouse-audit-results/main/{directorio}/site-info.json`

Esto permite que LLMs y otras herramientas accedan a los datos directamente.

## Repositorio

**URL:** https://github.com/ixtia/lighthouse-audit-results

