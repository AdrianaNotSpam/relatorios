# notspam.studio · relatórios

Repositório que aloja os relatórios mensais HTML dos clientes do estúdio notspam.studio, publicados via GitHub Pages.

## Site público

- Raiz (neutra): https://adriananotspam.github.io/relatorios/
- Relatório por cliente: https://adriananotspam.github.io/relatorios/<slug>/

## Estrutura

```
/
├── index.html         # página raiz neutra
├── robots.txt         # bloqueia indexação
├── <slug-cliente>/
│   └── index.html     # relatório actual do cliente
└── README.md
```

Cada cliente tem 1 URL fixo. O HTML actualiza todos os meses (com abas internas para histórico de meses).

## Como adicionar um novo cliente

1. Criar pasta `<slug>/` (minúsculas, hífenes, sem acentos)
2. Colocar `index.html` dentro
3. Garantir que tem `<meta name="robots" content="noindex, nofollow" />` no head
4. Commit + push

## Como actualizar um relatório

1. Substituir o `<slug>/index.html` pelo HTML novo
2. Commit + push (mensagem: `feat: adiciona <mês> ao relatório <Cliente>`)

Em automação futura, isto é feito por uma skill que lê o Google Sheet do cliente e actualiza o HTML via GitHub Contents API. Ver plano em `IA/relatorios/plano-arquitectura.md` no vault.

## Privacidade

- Repo é público (requisito do GitHub Pages grátis)
- Os HTML têm `noindex` (não aparecem no Google)
- `robots.txt` bloqueia todos os crawlers
- Página raiz não expõe a lista de clientes
