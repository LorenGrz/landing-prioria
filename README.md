# landing-prioria

Sitio estático de portfolio para Prioria — una app Android de priorización de notificaciones con IA.

No tiene servidor ni llamadas a API. Todo el contenido es una recreación estática de los mockups de la app para mostrar el proyecto en el portfolio.

## Stack

- Next.js 16 (App Router, `output: 'export'`)
- Tailwind CSS
- TypeScript

## Desarrollo local

```bash
npm install
npm run dev
# http://localhost:3000
```

## Build y deploy (GitHub Pages)

Deploy automático: cada push a `master` dispara `.github/workflows/` (build + `actions/deploy-pages`). No hace falta build ni sync manual.

```bash
npm run build   # genera ./out — solo para probar el build localmente
```

**URL en vivo:** https://lorengrz.github.io/landing-prioria/

## Contenido

- Hero con descripción del proyecto y links al repo/app
- Galería de 3 phone-frames (Inicio, Historial, Entrenar) recreados como componentes React estáticos
- Sección de features, stack tecnológico y footer

## Proyecto relacionado

- El código de la app (y su backend serverless en AWS SAM) es privado. El APK se publica en los releases de este repo: https://github.com/LorenGrz/landing-prioria/releases/latest/download/prioria.apk

## Versión mínima de la app (`public/version.json`)

La app de Prioria consulta `https://lorengrz.github.io/landing-prioria/version.json` para saber si la instalación está desactualizada. Solo lleva números (la URL de descarga está fija en la app):

```json
{ "minVersionCode": 30, "latestVersionCode": 30 }
```

- `latestVersionCode`: subirlo después de publicar cada APK nuevo (el `versionCode` es el `run_number` de GitHub Actions, o sea el `N` de `v1.0.N`). Las versiones menores ven un aviso opcional.
- `minVersionCode`: subirlo solo cuando una versión vieja tiene que dejar de funcionar. Las versiones menores quedan bloqueadas con una pantalla de "Actualizá Prioria".
- Push a `master` para publicarlo.
