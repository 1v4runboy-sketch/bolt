
# Polus Eletrotécnica — Catálogo Técnico

Next.js 14 (App Router) + TypeScript + Tailwind CSS. Sem libs externas de UI.

## Rodando localmente

```bash
npm install
npm run dev
# produção
npm run build
npm run start
```

## Estrutura

```
/app
  layout.tsx, page.tsx, ...
/components
  (UI, carrosséis, etc.)
/lib
  site.ts, products.ts, brands.ts, reviews.ts, budgetList.ts
/public
  (imagens dos produtos, marcas, reviews, loja, ícones)
/styles
  globals.css
```

## Variáveis de ambiente

Crie `.env.local` (já incluso) com:

```
NEXT_PUBLIC_WHATSAPP_NUMBER=+551135992935
NEXT_PUBLIC_MAPS_EMBED_URL=https://www.google.com/maps?q=-23.516861,-46.770811&z=16&output=embed
```

## Atualizando produtos

Edite `lib/products.ts`. Cada produto segue o schema:

```ts
export type Product = {
  id: string;
  slug: string;
  title: string;
  brand?: string;
  category: string;
  subcategory?: string;
  shortDescription?: string;
  images: { src: string; alt: string }[];
  techSpecs?: [string, string][];
};
```

Imagens ficam em `public/produtos/imagens/...`. Use caminhos com prefixo `/produtos/...`.

## Onde colocar as imagens

- Produtos: `public/produtos/imagens/...`
- Marcas: `public/marcas/...`
- Reviews (avatares): `public/reviews/...`
- Loja (fachada): `public/loja/...`
- Ícones: `public/polus-logo.svg`, `app/icon.png`, `public/favicon.ico`

## Notas

- Efeitos respeitam `prefers-reduced-motion`.
- Carrosséis com autoplay, pause no hover, swipe, setas e indicadores.
- Header usa cor média do hero via `HeroColorSync`.
- Carrinho/orçamento em `localStorage`.
