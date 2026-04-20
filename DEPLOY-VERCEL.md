# 🚀 Deploy no Vercel — Passo a Passo

Este projeto está pronto para deploy. Escolha um dos 3 caminhos abaixo.

## Estrutura do projeto

```
lc-intercambio-site/
├── index.html              ← Hub principal (lista todas as propostas)
├── vercel.json             ← Configuração (cache, URLs limpas)
└── sydney-ingles/
    └── index.html          ← Proposta Sydney (acessível em /sydney-ingles)
```

---

## ⚡ MÉTODO 1 — Deploy via Drag & Drop (mais rápido, 2 minutos)

1. Acesse https://vercel.com/new
2. Faça login (pode usar GitHub, Google ou e-mail)
3. Role a página até "Deploy Templates" → procure o link **"Import a third-party Git Repository"** ou vá direto em https://vercel.com/new/clone
4. No painel, clique em **"Add New... → Project"**
5. Em vez de importar um repositório, clique em **"Import Third-Party Git Repository"** OU use a opção **"Upload"** (arrastar pasta)
6. Arraste a pasta `lc-intercambio-site` inteira
7. Deixe tudo no padrão e clique em **Deploy**

**Pronto!** Você receberá uma URL tipo `lc-intercambio-site.vercel.app`

> 💡 **Dica:** Em "Project Settings" → "Domains", você pode apontar seu domínio próprio (ex: `lceducationandmigration.com`).

---

## ⚡ MÉTODO 2 — Vercel CLI (recomendado para deploys futuros)

No seu terminal (Mac/Linux/Windows):

```bash
# 1. Instalar o Vercel CLI (uma única vez)
npm install -g vercel

# 2. Entrar na pasta do projeto
cd caminho/para/lc-intercambio-site

# 3. Fazer deploy (primeira vez ele pede login)
vercel

# Respostas sugeridas quando perguntado:
# ? Set up and deploy? → Y
# ? Which scope? → sua conta
# ? Link to existing project? → N
# ? Project name? → lc-intercambio (ou o que preferir)
# ? Directory? → ./
# ? Override settings? → N

# 4. Para fazer deploy em produção:
vercel --prod
```

---

## ⚡ MÉTODO 3 — GitHub + Vercel (melhor para longo prazo)

1. Crie um repositório no GitHub chamado `lc-intercambio-site`
2. Faça upload da pasta inteira para o repositório
3. Em https://vercel.com/new → selecione o repositório → **Deploy**

**Vantagem:** toda vez que você atualizar o GitHub, o Vercel faz deploy automático. Perfeito para quando você adicionar novas propostas.

---

## ➕ Adicionando novas propostas no futuro

Para cada nova proposta que o Claudio criar, basta:

1. Criar uma nova pasta dentro de `lc-intercambio-site/`, ex: `melbourne-ingles/`
2. Colocar o `index.html` dentro dela
3. Editar o `index.html` principal (da raiz) para trocar um dos cards "Em breve" por um link ativo:

```html
<a href="/melbourne-ingles" class="card">
  ...
</a>
```

4. Fazer novo deploy (via CLI `vercel --prod` ou push no GitHub)

---

## 🌐 URLs geradas

Após o deploy, suas páginas ficarão assim:

- `seusite.vercel.app/` → Hub com todas as propostas
- `seusite.vercel.app/sydney-ingles` → Proposta Sydney
- `seusite.vercel.app/melbourne-ingles` → (quando criar)

## 🆘 Se der qualquer erro

Me chame de volta com o print do erro ou a mensagem do terminal que eu te ajudo a resolver.
