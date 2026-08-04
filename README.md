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

## Build y deploy (S3 + CloudFront)

```bash
npm run build   # genera ./out
aws s3 sync out/ s3://prioria-landing-493735739644 --delete
aws cloudfront create-invalidation --distribution-id E27GXNA3NNHD70 --paths "/*"
```

**URL en vivo:** https://d1c6xk2jegfebf.cloudfront.net

## Contenido

- Hero con descripción del proyecto y links al repo/app
- Galería de 3 phone-frames (Inicio, Historial, Entrenar) recreados como componentes React estáticos
- Sección de features, stack tecnológico y footer

## Proyecto relacionado

- App principal: [LorenGrz/Prioria](https://github.com/LorenGrz/Prioria)
- Backend serverless: `Prioria/backend/` (AWS SAM — Lambda, Cognito, DynamoDB, Bedrock)
