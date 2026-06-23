# Documentação do Projeto — Site da Brenda

Resumo direto do que o projeto **precisa ser**. Sem enrolação.

---

## 1. O que é

Um site com **dois lados** que vivem juntos:

| Lado | Pra quê | Quem usa |
|------|---------|----------|
| **Clínica** | Mostrar procedimentos, gerar autoridade, captar paciente | Quem quer fazer procedimento |
| **Cursos** | Vender cursos e entregar material de estudo (apostilas, conteúdo) | Aluno que comprou o curso |

O erro a evitar: tratar como "só um site institucional". O coração do projeto é a **parte de cursos + material de apoio**.

---

## 2. Requisitos essenciais (o mínimo que precisa existir)

### Lado clínica (mais simples)
- **Home** — quem é a Brenda, destaque dos procedimentos, CTA de WhatsApp
- **Sobre** — trajetória, CRBM, diferencial
- **Procedimentos** — lista dos serviços (com ou sem preço — decisão da reunião)
- **Contato / Agendamento** — botão de WhatsApp (jeito mais simples e que ela já usa)

### Lado cursos (o foco — mais trabalho)
- **Catálogo de cursos** — lista de cursos por tema/categoria
- **Página de cada curso** — descrição, público-alvo, carga horária, preço, botão de compra
- **Material de apoio / apostilas** — várias apostilas, vários temas; o aluno acessa o conteúdo pra estudar
- **Controle de acesso ao material** — quem pode ver o quê (essa é a decisão crítica, ver abaixo)

### Transversal (vale pros dois)
- Responsivo (funciona bem no celular — maioria do público vem de Instagram)
- Identidade visual coerente (cores, logo)
- SEO básico (título, descrição, aparecer no Google pelo nome dela)
- Carregar rápido

---

## 3. A decisão que muda TODO o projeto

**Como o aluno acessa o material de apoio?** Existem 3 caminhos, do mais simples ao mais complexo:

1. **Vende por plataforma externa (Hotmart / Kiwify)** — ⭐ recomendado pra começar
   A plataforma cuida do pagamento, login do aluno e entrega do material. O site vira só a **vitrine** que manda pro checkout. Você **não constrói login nem área de membros** — economiza semanas.

2. **Material com senha / link protegido** — meio-termo
   Site estático, material liberado por senha. Simples, mas controle fraco (senha vaza).

3. **Área de aluno própria (login + conteúdo restrito)** — mais complexo
   Você constrói autenticação, banco, área logada. Vira um sisteminha de verdade. Só vale se ela quiser plataforma própria de longo prazo (e pagar por isso).

> **Antes de codar qualquer coisa de curso, decida isso com a Brenda.** É a pergunta nº1 da reunião.

---

## 4. Fora de escopo (por enquanto)

Pra não inflar o projeto e nunca entregar:
- App de celular
- Sistema de pagamento próprio (use Hotmart/Kiwify/Pix manual)
- Agendamento com calendário automático (WhatsApp resolve no MVP)
- Emissão automática de certificado (pode ser manual no início)

Essas coisas entram numa **fase 2**, se o projeto crescer.

---

## 5. Premissas atuais (confirmar na reunião)

- Hospedagem: **Netlify** (grátis, já em uso pro briefing)
- Domínio próprio: a confirmar (ex: brendaestetica.com.br ~ R$40/ano)
- Agendamento: **WhatsApp** (link direto)
- Conteúdo (textos/fotos): a definir quem produz
- Venda de curso: a definir (plataforma externa vs própria)
