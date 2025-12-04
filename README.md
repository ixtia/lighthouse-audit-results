# Lighthouse Audit Results Dashboard

Este repositorio contiene los resultados de las auditorías de Lighthouse realizadas en diferentes sitios web.

## Estructura

- `index.html` - Dashboard principal con todos los dominios analizados
- Cada directorio contiene los resultados de un dominio específico:
  - `audit.json` - Datos completos de la auditoría en formato JSON
  - `index.html` - Informe detallado HTML de Lighthouse
  - `report.xlsx` - Informe Excel con múltiples hojas
  - `site-info.json` - Información básica del sitio auditado

## Despliegue en Cloudflare Pages

### Configuración IMPORTANTE

1. Conecta este repositorio a Cloudflare Pages
2. **Configuración de build (CRÍTICO):**
   - **Framework preset**: `None` o `Other`
   - **Build command**: **DEJAR COMPLETAMENTE VACÍO** (no poner nada, ni siquiera espacios)
   - **Build output directory**: `/` (raíz del repositorio)
   - **Root directory**: `/` (raíz del repositorio)
   - **Deploy command**: **DEJAR COMPLETAMENTE VACÍO** (no usar `wrangler deploy`)

⚠️ **IMPORTANTE**: Si ves un error sobre `wrangler deploy`, significa que hay un comando de deploy configurado. Debe estar **vacío** para archivos estáticos.

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

Cloudflare Pages se actualizará automáticamente.

## Acceso

Una vez desplegado, el dashboard estará disponible en:
- `https://lighthouse-audit-results.pages.dev` (o tu dominio personalizado)

## API de Datos

Los datos JSON están disponibles directamente vía GitHub Raw:
- `https://raw.githubusercontent.com/ixtia/lighthouse-audit-results/main/{directorio}/audit.json`
- `https://raw.githubusercontent.com/ixtia/lighthouse-audit-results/main/{directorio}/site-info.json`

Esto permite que LLMs y otras herramientas accedan a los datos directamente.

## Repositorio

**URL:** https://github.com/ixtia/lighthouse-audit-results

