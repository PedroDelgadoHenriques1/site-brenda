# Site da Brenda — Clínica de Biomedicina Estética + Cursos

Projeto de site duplo: **vitrine da clínica** (procedimentos estéticos) + **plataforma de cursos** (material de apoio / apostilas para os alunos estudarem).

> **Status:** briefing pronto + site Fase 1 esboçado. Aguardando respostas da Brenda pra começar a construção pra valer.
> **Cliente:** Brenda — biomédica esteta, faz procedimentos e ministra cursos.

## 🔗 Links

| O quê | Onde |
|------|------|
| Repositório | https://github.com/PedroDelgadoHenriques1/site-brenda |
| Preview do site (GitHub Pages) | https://pedrodelgadohenriques1.github.io/site-brenda/ |
| Briefing (o que a Brenda preenche) | https://briefing-brenda.netlify.app/ |

## 🗺️ Próximos passos

> Ordem do que fazer. Marque `[x]` conforme for andando.

1. [ ] **Re-deploy do briefing v2 no Netlify** — arrastar `briefing/index.html` pra faixa de deploy do site `briefing-brenda`.
2. [ ] **Mandar o briefing pra Brenda** preencher → https://briefing-brenda.netlify.app/
3. [ ] **Reunião com a Brenda** (`docs/REUNIAO-BRENDA.md`) — fechar a **decisão crítica**: como o aluno acessa as apostilas (plataforma externa tipo Hotmart/Kiwify ⭐ vs área de membros própria vs senha). Isso trava toda a arquitetura.
4. [ ] **Coletar os arquivos dela** — apostilas (PDF/Word), fotos, logo (ver checklist abaixo).
5. [ ] **Definir a stack final** (Astro+Tailwind vs HTML puro) conforme a decisão de acesso ao material.
6. [ ] **Construir por fase** (`docs/CONSTRUIR-COM-IA.md`):
   - Fase 1 — site da clínica (já esboçado em `site/`, falta conteúdo real da Brenda)
   - Fase 2 — catálogo de cursos
   - Fase 3 — biblioteca de apostilas (**o coração do projeto**)
7. [ ] **Domínio próprio** (opcional) — ex: `brendaestetica.com.br`.

---

## 📁 O que tem nesse repositório

```
brenda-site/
├── README.md                  ← você está aqui
├── index.html                 ← redireciona pra site/ (raiz do GitHub Pages)
├── docs/
│   ├── DOCUMENTACAO.md         ← resumo do projeto + requisitos essenciais
│   ├── REUNIAO-BRENDA.md       ← perguntas pra reunião (as decisões que travam tudo)
│   └── CONSTRUIR-COM-IA.md     ← stack escolhida + prompts prontos por fase
├── briefing/
│   └── index.html              ← formulário de briefing (deploy no Netlify)
└── site/                       ← o site em si (a ser construído por fase)
    ├── index.html
    └── assets/ (css, js, img)
```

## 🚦 Como usar esse repo

1. **Leia `docs/DOCUMENTACAO.md`** — entenda o escopo real (o que precisa existir).
2. **Faça a reunião com a Brenda** usando `docs/REUNIAO-BRENDA.md`. Sem essas respostas, dá pra começar, mas você vai retrabalhar.
3. **Construa por fase** seguindo `docs/CONSTRUIR-COM-IA.md` — tem prompt pronto pra colar na IA em cada etapa.
4. **Commit a cada fase entregue.** Não tenta fazer tudo de uma vez.

## ✅ Checklist de dados — garantir que nada falte

O **briefing já coleta** o cadastro essencial pra uma plataforma de cursos (bloco 9): **WhatsApp, e-mail, CRBM, CNPJ e redes sociais**. Use a lista abaixo só pra conferir o que chegou e cobrar o que falta.

**Já vem no briefing (bloco 9):**
- [ ] WhatsApp · E-mail · **CRBM** (obrigatório no site — profissão regulada) · CNPJ (se vender curso) · redes sociais

**Confirmar à parte (não estão no formulário):**
- [ ] Plataforma de venda dos cursos (Hotmart / Kiwify / etc.) + link — define toda a arquitetura
- [ ] Quer domínio próprio? Quem registra e paga (~R$40/ano)
- [ ] Endereço / horários — **só se também atender presencial** (plataforma de curso não precisa)

**Arquivos que ELA precisa entregar (senão o site fica vazio):**
- [ ] Fotos (dela, clínica, procedimentos, antes/depois **com autorização escrita** da cliente)
- [ ] Os arquivos das **apostilas** (PDF/Word) — é o produto, sem isso não tem o que proteger nem vender
- [ ] Logo / manual de marca, se tiver

## 🔒 Segurança (detalhar pra IA na hora de construir)

> Esboço inicial — Pedro detalha conforme as decisões da reunião. O nível depende **principalmente** de como o aluno acessa o material (ver `docs/DOCUMENTACAO.md` §3).

- **Proteger o material de apoio (prioridade nº1).** As apostilas são o produto; não podem ficar expostas (link público indexável no Google, pasta aberta).
  - *Plataforma externa (Hotmart/Kiwify)* → eles cuidam de login e entrega. **Não construir auth.** Mais seguro e menos trabalho. ⭐
  - *Área de membros própria* → autenticação de verdade (senha com hash, sessão segura), acesso liberado só por compra. Não confiar em "link escondido".
  - *Download com senha* → senha vaza fácil; no mínimo não deixar PDF em URL adivinhável e trocar a senha de tempos em tempos.
- **Pagamento:** NUNCA processar cartão direto no site. Sempre via gateway/plataforma (Hotmart, Kiwify, Mercado Pago, Stripe). O risco de cartão fica com eles.
- **Formulários (briefing, contato, agendamento):** anti-spam (honeypot — já tem no briefing), validação de entrada, e não expor e-mail em texto puro no HTML.
- **HTTPS obrigatório** (Netlify já dá de graça) — forçar redirecionamento http → https.
- **LGPD:** se coletar dado de cliente/aluno (nome, e-mail, CPF), ter política de privacidade + consentimento, e coletar só o mínimo necessário.
- **Headers de segurança:** CSP, X-Frame-Options, etc. (no Netlify, via arquivo `_headers`).
- **Painel de edição** (se a Brenda for atualizar sozinha): proteger com senha forte e, se possível, 2FA.
- **Dependências:** manter atualizadas; cuidado com biblioteca de terceiro desconhecida.

## 🌐 Briefing online

O formulário em `briefing/index.html` é o que a Brenda preenche. Sobe no Netlify (drag & drop ou via Git), e as respostas chegam no e-mail / aba **Forms** do painel.
URL atual: https://briefing-brenda.netlify.app/
