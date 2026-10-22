# Landing page · Rota do Cálculo (DestravaObra)

Projeto Vite + React + TypeScript (o mesmo formato da Lovable).

## Rodar localmente

```bash
npm install
npm run dev
```

## Publicar na Lovable

1. Suba esta pasta `landing/` para um repositório no GitHub (a raiz do repositório deve conter `package.json`, `index.html`, `src/` e `public/`).
2. Na Lovable: **Settings → GitHub → Connect** e conecte o repositório (ou crie o projeto e sincronize com ele).
3. Clique em **Publish**. Para domínio próprio: **Settings → Domains**.

## Onde mudar cada coisa

| O quê | Arquivo |
|---|---|
| Links de checkout, preços, garantia, redes sociais | `src/config.ts` |
| Pixel da Meta (código base + PageView) | `index.html` (no `<head>`) |
| Eventos de compra do pixel (InitiateCheckout, ViewContent) | `src/pixel.ts` |
| Textos e seções | `src/App.tsx` |
| Cores, animações e CSS que esconde a marca d'água da Lovable | `src/index.css` |
| Imagens (mockups, páginas do guia, depoimentos) | `public/` |

## Pixel

- `PageView`: em todas as visitas (index.html).
- `ViewContent`: quando a pessoa chega na seção de preço, e quando o pop-up do PRO aparece.
- `InitiateCheckout`: em todo botão de compra, com valor e moeda (BRL). O clique espera 300 ms para o evento sair e leva as UTMs/fbclid da página para o checkout.
- `Purchase`: deve ser disparado pela Cakto. Cadastre o pixel `1645983383835511` no produto, em **Cakto → Produto → Pixels**.

## Pop-up do upsell (Rota do Cálculo PRO)

Aparece uma vez por sessão: ao tentar sair da página (desktop), ao rolar rápido para cima depois de ver a oferta (celular) ou após 60 segundos.
