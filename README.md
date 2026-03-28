# soul-surf

Site institucional do Projeto Soul Surf, com páginas HTML e build via Vite.

## Requisitos

- Node.js 18+
- npm 9+

## Como rodar o projeto

1. Entre na pasta do site:

```bash
cd site
```

2. Instale as dependências:

```bash
npm install
```

3. Rode em modo desenvolvimento:

```bash
npm run dev
```

4. Abra no navegador a URL mostrada no terminal (normalmente `http://localhost:5173`).

## Como gerar build de produção

```bash
cd site
npm run build
```

Os arquivos finais serão gerados em `site/dist/`.

## Como testar o build localmente

```bash
cd site
npm run preview
```

## Estrutura principal

- `site/index.html`: página inicial
- `site/apoie-o-soul-surf.html`: página de apoio
- `site/destinacao-criancas-irpf-soul-surf.html`: página de destinação IRPF
- `site/vagas-em-aberto.html`: página de vagas
- `site/artigos/`: páginas de artigos
- `site/fotos/`: fotos centralizadas do projeto
