# Construir com IA — Stack + Prompts por Fase

Como tocar o desenvolvimento pedindo pra IA (Claude Code, etc.) sem se perder. A regra de ouro: **uma fase por vez, commit no fim de cada uma.**

---

## Stack recomendada (MVP barato e rápido)

- **Astro** + **Tailwind CSS** — ótimo pra site de conteúdo, gera site estático rápido, fácil de manter componentes (header/footer sem repetir). Funciona perfeito no Netlify.
- **Hospedagem:** Netlify (grátis)
- **Cursos:** vitrine no site → checkout no **Hotmart/Kiwify** (eles cuidam de pagamento e entrega)
- **Agendamento:** link direto de **WhatsApp**

> Se preferir não usar framework, dá pra fazer em **HTML/CSS/JS puro** (igual o briefing). Mais simples de começar, mas você repete header/footer em toda página.
>
> Opção portfólio: se quiser usar isso como peça de **.NET** pro seu currículo, a área de aluno (fase 4) pode virar uma API ASP.NET Core. Só faça isso se a Brenda topar prazo maior — pro MVP, mantenha simples.

---

## Fases (ordem de construção)

### Fase 0 — Setup
Estrutura do projeto, deploy contínuo no Netlify, layout base (header, footer, cores, fontes).

### Fase 1 — Site da clínica (entrega valor rápido)
Home + Sobre + Procedimentos + Contato/WhatsApp. **Já dá pra mostrar pra Brenda e pôr no ar.**

### Fase 2 — Catálogo de cursos (vitrine)
Lista de cursos + página de cada curso com botão de compra (link Hotmart/Kiwify).

### Fase 3 — Material de apoio
Biblioteca de apostilas por tema. (Acesso conforme decisão da reunião.)

### Fase 4 — Área de aluno (opcional / só se necessário)
Login + conteúdo restrito. Só entra se a Brenda quiser plataforma própria.

### Fase 5 — Refino
SEO, performance, analytics, polish visual, revisão no celular.

---

## Prompts prontos (cola na IA)

> Sempre comece a sessão dando contexto: *"Estou construindo um site para uma biomédica esteta (clínica + cursos). Leia os arquivos em /docs antes de começar."*

**Fase 0 — Setup**
```
Crie a base de um site em Astro + Tailwind para uma clínica de biomedicina
estética que também vende cursos. Configure: estrutura de pastas, layout base
com header e footer reutilizáveis, paleta de cores [COLOQUE AS CORES DA BRENDA],
fonte elegante, e deixe pronto pra deploy no Netlify. Site em português.
```

**Fase 1 — Site da clínica**
```
Crie as páginas: Home, Sobre, Procedimentos e Contato.
- Home: hero com nome da Brenda, destaque de 3 procedimentos, CTA "Agendar pelo WhatsApp".
- Sobre: trajetória, CRBM, diferencial.
- Procedimentos: lista em cards [com/sem preço — ver decisão].
- Contato: botão grande de WhatsApp (link wa.me) + redes sociais + localização.
Tudo responsivo, mobile-first.
```

**Fase 2 — Catálogo de cursos**
```
Crie a seção de cursos:
- Página /cursos: grid de cards, um por curso, agrupados por tema.
- Página de cada curso: descrição, público-alvo, carga horária, preço e
  botão "Comprar" que aponta pra um link externo (Hotmart/Kiwify).
Os dados dos cursos devem ficar num arquivo de conteúdo fácil de editar.
```

**Fase 3 — Material de apoio**
```
Crie a biblioteca de apostilas:
- Página que lista apostilas agrupadas por tema.
- Cada item: título, tema, e link pra abrir/baixar o material.
[Acesso: público / com senha / restrito — conforme a decisão da reunião]
```

**Fase 5 — Refino**
```
Faça um passe de qualidade: meta tags de SEO em todas as páginas, otimização
de imagens, checagem de performance, revisão de responsividade no celular,
e acessibilidade básica (alt, contraste, foco de teclado).
```

---

## Checklist antes de entregar pra Brenda

- [ ] Funciona bem no celular
- [ ] Botão de WhatsApp testado (abre no número certo)
- [ ] Links de compra dos cursos funcionando
- [ ] Material de apoio acessível conforme combinado
- [ ] Nome, CRBM e contatos corretos
- [ ] Aparece no Google buscando o nome dela
- [ ] Nenhum texto "lorem ipsum" / foto placeholder esquecida
