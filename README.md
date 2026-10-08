# Módulo 8 - Cloud: GitHub Pages con GitHub Actions

App Vite + React + TypeScript desplegada automáticamente en GitHub Pages con GitHub Actions.

## Enlace

- **App desplegada:** https://danivegi.github.io/modulo08-cloud-gh-pages-auto/

## Cómo se despliega

Cada merge a `main` ejecuta el workflow `.github/workflows/deploy.yml`, que tiene dos jobs:

1. **build:** instala dependencias con `npm ci`, ejecuta `npm run build` y sube la carpeta `dist` como artifact de Pages.
2. **deploy:** publica ese artifact en GitHub Pages con `actions/deploy-pages`.

GitHub Pages está configurado con la fuente "GitHub Actions" (Settings → Pages). `vite.config.ts` usa `base: './'` porque la app se sirve en una subcarpeta.

El historial de ejecuciones puede verse en la pestaña Actions.