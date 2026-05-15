---
task: "Review Completo da Landing Page"
order: 1
input: |
  - landing_page: Arquivo HTML da landing page
  - quality_criteria: Critérios de qualidade documentados
output: |
  - review_output: Review estruturado com scoring, feedback e veredito APPROVE/REJECT
---

# Review Completo da Landing Page

Avalia a landing page completa (copy + design + técnico) contra os critérios de qualidade definidos. Produz review estruturado com veredito final.

## Process

1. **Carregar critérios.** Ler `pipeline/data/quality-criteria.md` para entender os parâmetros de avaliação. Ler também `pipeline/data/anti-patterns.md` para verificar violações.
2. **Ler o HTML completo.** Ler o arquivo landing-page.html de ponta a ponta. Notar impressões iniciais mas não pontuar ainda.
3. **Avaliar critérios de Copy.** Pontuar cada critério da seção Copy (headline impact, clareza da proposta, CTA effectiveness, persuasão, prova social, objeção handling, tom de voz).
4. **Avaliar critérios de Design.** Pontuar cada critério da seção Design (visual hierarchy, dark mode quality, glassmorphism, responsividade, tipografia, contraste WCAG, consistência visual, animações).
5. **Avaliar critérios Técnicos.** Pontuar cada critério da seção Técnico (HTML semântico, CSS moderno, self-contained, performance, SEO básico).
6. **Compilar veredito.** Calcular score geral. Aplicar regras de decisão: APPROVE (>= 7.0, nenhum < 4/10), REJECT (< 7.0 ou qualquer < 4/10). Listar required changes e suggestions.

## Output Format

```
==============================
 REVIEW VERDICT: {APPROVE | CONDITIONAL APPROVE | REJECT}
==============================

Landing Page: {nome do cliente}
Review Date: {data}
Revision: {N} de 3

------------------------------
 SCORING TABLE
------------------------------
| Critério              | Score  | Resumo                              |
|------------------------|--------|-------------------------------------|
| {critério}             | X/10   | {justificativa de 1 frase}          |
------------------------------
 OVERALL: X.X/10
------------------------------

DETAILED FEEDBACK:

Strength: {observação positiva específica}

Required change: {o que corrigir, onde, e como}

Suggestion (non-blocking): {melhoria opcional}

PATH TO APPROVAL: (apenas em REJECT)
1. {correção necessária}
2. {correção necessária}

VERDICT: {APPROVE | REJECT} — {resumo de 1 frase}
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
==============================
 REVIEW VERDICT: CONDITIONAL APPROVE
==============================

Landing Page: TechFlow — Automação B2B
Review Date: 2026-05-14
Revision: 1 de 3

------------------------------
 SCORING TABLE
------------------------------
| Critério                  | Score  | Resumo                                          |
|---------------------------|--------|-------------------------------------------------|
| Headline Impact           | 9/10   | Headline direta com benefício claro e dor        |
| Clareza da Proposta       | 8/10   | Proposta entendida em < 5 segundos               |
| CTA Effectiveness         | 8/10   | CTAs específicos com voz ativa em todas seções   |
| Persuasão                 | 8/10   | Framework PAS bem executado                      |
| Prova Social              | 7/10   | 2 depoimentos com resultado, faltam logos        |
| Objeção Handling          | 7/10   | FAQ cobre objeções principais                    |
| Tom de Voz                | 9/10   | Tech Confiante consistente em toda a copy        |
| Visual Hierarchy          | 8/10   | Olho segue caminho claro hero → seções → CTA    |
| Dark Mode Quality         | 9/10   | Fundo #0A0A0F com gradient orbs, excelente       |
| Glassmorphism             | 8/10   | Glass cards nos benefícios, sutil e eficaz       |
| Responsividade            | 6/10   | Cards se sobrepõem em 375px                      |
| Tipografia                | 8/10   | Hierarquia clara, clamp() para responsividade    |
| Contraste WCAG            | 8/10   | Texto #F0F0F5 sobre #0A0A0F = ratio 17.4:1      |
| Consistência Visual       | 9/10   | Design system aplicado uniformemente             |
| Animações                 | 7/10   | Hover sutil nos CTAs, faltam fade-in no scroll   |
| HTML Semântico            | 8/10   | header, main, section, footer presentes          |
| CSS Moderno               | 9/10   | Custom properties, Grid, clamp() usados          |
| Self-Contained            | 10/10  | Sem dependências externas, apenas Google Fonts   |
| Performance               | 8/10   | CSS eficiente, sem JS pesado                     |
| SEO Básico                | 5/10   | Falta meta description e alt texts               |
------------------------------
 OVERALL: 7.9/10
------------------------------

DETAILED FEEDBACK:

Strength: O design system é excepcionalmente consistente. As custom properties
CSS garantem que cores e espaçamentos são uniformes em toda a página. O gradient
orb background cria profundidade real sem poluir visualmente.

Strength: A copy segue o framework PAS com precisão. A seção de dor é empática
sem ser dramática, e a solução se conecta diretamente à dor apresentada.

Required change: Na resolução 375px, os cards de benefícios se sobrepõem.
Adicionar media query: @media (max-width: 480px) { .benefits-grid { grid-template-columns: 1fr; gap: 16px; } }

Suggestion (non-blocking): Adicionar meta description no <head> para SEO:
<meta name="description" content="TechFlow automatiza seu follow-up de leads
em 15 minutos. Sem código. Teste grátis por 14 dias.">

Suggestion (non-blocking): Adicionar animação de fade-in nos elementos ao
scroll usando CSS @keyframes e IntersectionObserver leve.

VERDICT: CONDITIONAL APPROVE — Landing page de alta qualidade com 1 correção
necessária (responsividade mobile nos cards) e 2 sugestões opcionais.
```

## Quality Criteria

- [ ] Todos os critérios de quality-criteria.md avaliados e pontuados
- [ ] Cada score tem justificativa de pelo menos 1 frase
- [ ] Critérios rejeitados têm "Required change:" com instrução específica
- [ ] Pelo menos 1 "Strength:" presente
- [ ] Veredito coerente com os scores
- [ ] Feedback inclui localização exata (seção, elemento, CSS property)

## Veto Conditions

Rejeitar e refazer se:
1. Review não avaliou pelo menos 15 critérios individuais
2. Scores não têm justificativa escrita (números soltos sem "porque")
