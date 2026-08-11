# Template odontológico white-label

Landing page institucional reutilizável para clínicas odontológicas, baseada no modelo visual aprovado da 101 Sorrisos.

## Personalização atual

Esta cópia está preparada como primeira versão da **Glória Odontologia**.
A identidade visual, a hero e a galeria usam os arquivos enviados pelo cliente.

Os dados de contato, unidades, endereços, cidade, perguntas frequentes e
procedimentos ainda são os conteúdos provisórios do template. Antes de publicar
o endereço definitivo, substitua esses dados em `src/config/clinic.ts` e informe
o domínio correto em `seo.canonicalUrl`.

## Criar um novo site

1. Execute `npm install`.
2. Edite apenas `src/config/clinic.ts`.
3. Substitua os arquivos dentro de `public/brand/`.
4. Ative ou desative seções em `featureFlags`.
5. Execute `npm run lint`.
6. Execute `npm run build`.

## GitHub e Vercel

Envie todo o conteúdo desta pasta para a raiz do repositório. Na Vercel,
importe o repositório usando o preset **Next.js**; não são necessárias
variáveis de ambiente para o conteúdo atual.

## Assets fixos

- `public/brand/logo.webp`
- `public/brand/hero.webp`
- `public/brand/og-image.webp`
- `public/brand/gallery/`
- `public/brand/procedimentos/`

O layout, os componentes e as animações não precisam ser alterados durante uma troca de cliente.

Consulte `CLIENTE-EXEMPLO.md` para o checklist de materiais e `AGENTS.md` para as regras permanentes do projeto.
Para publicar pelo celular usando Codespaces, siga `PUBLICAR-NO-GITHUB.md`.
