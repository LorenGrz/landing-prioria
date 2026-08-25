# landing-prioria

Sitio estático de portfolio para [Prioria](https://github.com/LorenGrz/Prioria) — una app Android de priorización de notificaciones con IA.

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

- App principal: [LorenGrz/Prioria](https://github.com/LorenGrz/Prioria)
- Backend serverless: `Prioria/backend/` (AWS SAM — Lambda, Cognito, DynamoDB, Bedrock)
