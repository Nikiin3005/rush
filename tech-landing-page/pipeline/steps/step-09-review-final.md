---
execution: inline
agent: reviewer
inputFile: squads/tech-landing-page/output/landing-page.html
outputFile: squads/tech-landing-page/output/review-output.md
---

# Step 09: Review Final

## Context Loading

Load these files before executing:
- `squads/tech-landing-page/output/landing-page.html` — Landing page HTML para review
- `pipeline/data/quality-criteria.md` — Critérios de qualidade com scoring
- `pipeline/data/anti-patterns.md` — Erros a verificar
- `squads/tech-landing-page/output/copy-output.md` — Copy original para verificar implementação

## Instructions

### Process
1. **Carregar critérios de qualidade.** Ler quality-criteria.md e anti-patterns.md para ter os parâmetros de avaliação.
2. **Ler o HTML completo.** Ler landing-page.html de ponta a ponta. Notar impressões iniciais mas não pontuar ainda.
3. **Avaliar critérios de Copy (peso 40%).** Pontuar: headline impact, clareza da proposta, CTA effectiveness, persuasão, prova social, objeção handling, tom de voz.
4. **Avaliar critérios de Design (peso 40%).** Pontuar: visual hierarchy, dark mode quality, glassmorphism, responsividade, tipografia, contraste WCAG, consistência visual, animações.
5. **Avaliar critérios Técnicos (peso 20%).** Pontuar: HTML semântico, CSS moderno, self-contained, performance, SEO básico.
6. **Verificar copy completa.** Comparar com copy-output.md para garantir que todo texto foi implementado.
7. **Compilar veredito.** Score geral, required changes, suggestions, strengths. Aplicar regras: APPROVE >= 7.0 sem nenhum < 4, REJECT < 7.0 ou qualquer < 4.

## Output Format

```
==============================
 REVIEW VERDICT: {APPROVE | CONDITIONAL APPROVE | REJECT}
==============================

Landing Page: {nome}
Review Date: {data}
Revision: {N} de 3

------------------------------
 SCORING TABLE
------------------------------
| Critério              | Score  | Resumo                              |
|------------------------|--------|-------------------------------------|
| {critério}             | X/10   | {justificativa}                     |
------------------------------
 OVERALL: X.X/10
------------------------------

DETAILED FEEDBACK:

Strength: {positivo específico}
Required change: {o que, onde, como corrigir}
Suggestion (non-blocking): {melhoria opcional}

PATH TO APPROVAL: (se REJECT)
1. {correção}

VERDICT: {APPROVE | REJECT} — {resumo}
```

## Output Example

```
==============================
 REVIEW VERDICT: APPROVE
==============================

Landing Page: TechFlow — Automação B2B
Review Date: 2026-05-14
Revision: 1 de 3

------------------------------
 SCORING TABLE
------------------------------
| Critério                  | Score  | Resumo                                          |
|---------------------------|--------|-------------------------------------------------|
| Headline Impact           | 9/10   | Headline direta com dor + benefício              |
| Clareza da Proposta       | 9/10   | Proposta entendida em < 3 segundos               |
| CTA Effectiveness         | 8/10   | CTAs específicos com voz ativa                   |
| Persuasão                 | 8/10   | PAS bem executado com dados                      |
| Prova Social              | 8/10   | Depoimentos com resultado + logos                |
| Objeção Handling          | 8/10   | FAQ cobre 5 objeções principais                  |
| Tom de Voz                | 9/10   | Tech Confiante uniforme                          |
| Visual Hierarchy          | 9/10   | Caminho claro hero → seções → CTA               |
| Dark Mode Quality         | 9/10   | #0A0A0F com gradient orbs, profissional          |
| Glassmorphism             | 8/10   | Glass cards nos benefícios e FAQ                 |
| Responsividade            | 8/10   | Funcional em 375px, 768px e 1440px               |
| Tipografia                | 8/10   | Hierarquia clara com clamp()                     |
| Contraste WCAG            | 9/10   | Ratio 17.4:1 corpo, 12.1:1 muted                |
| Consistência Visual       | 9/10   | Design system uniforme                           |
| Animações                 | 7/10   | Hover nos CTAs, smooth scroll                    |
| HTML Semântico            | 8/10   | header, main, section, footer                    |
| CSS Moderno               | 9/10   | Custom properties, Grid, clamp()                 |
| Self-Contained            | 10/10  | Apenas Google Fonts externo                      |
| Performance               | 8/10   | CSS eficiente, JS mínimo                         |
| SEO Básico                | 7/10   | Title e meta description presentes               |
------------------------------
 OVERALL: 8.5/10
------------------------------

Strength: Design system excepcionalmente consistente com custom properties.
Gradient orbs criam profundidade real sem poluição visual.

Strength: Framework PAS executado com precisão. Transição dor → solução é empática e convincente.

Suggestion (non-blocking): Considerar adicionar fade-in animations nos elementos ao scroll para maior sofisticação.

Suggestion (non-blocking): Adicionar aria-labels nos botões para melhorar acessibilidade.

VERDICT: APPROVE — Landing page de alta qualidade. Visual dark premium com glassmorphism sutil, copy persuasiva e tecnicamente sólida. Pronta para deploy.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Review não avaliou pelo menos 15 critérios individuais
2. Scores não têm justificativa (números sem "porque")

## Quality Criteria

- [ ] Todos os critérios avaliados e pontuados
- [ ] Cada score com justificativa
- [ ] Required changes com instrução específica
- [ ] Pelo menos 1 Strength
- [ ] Veredito coerente com scores
- [ ] Feedback inclui localização exata
