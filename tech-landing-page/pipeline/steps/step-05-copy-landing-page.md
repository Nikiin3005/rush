---
execution: inline
agent: copywriter
inputFile: squads/tech-landing-page/output/research-output.md
outputFile: squads/tech-landing-page/output/copy-output.md
---

# Step 05: Copy da Landing Page

## Context Loading

Load these files before executing:
- `squads/tech-landing-page/output/research-output.md` — Research brief com estrutura aprovada
- `pipeline/data/tone-of-voice.md` — 6 opções de tom de voz
- `pipeline/data/research-brief.md` — Tendências e frameworks de LP
- `pipeline/data/anti-patterns.md` — Erros de copy a evitar

## Instructions

### Process
1. **Ler o research output aprovado.** Extrair estrutura de seções, insights e briefing do cliente.
2. **Seleção de tom de voz.** Ler tone-of-voice.md, recomendar o tom mais adequado ao cliente/público. Apresentar as 6 opções ao usuário e aguardar escolha.
3. **Diagnóstico de copy.** Identificar awareness level, sofisticação de mercado, Big Idea (inimigo + mecanismo + promessa), driver psicológico dominante, e framework (PAS/AIDA/4Ps/BAB).
4. **Criar 3 opções de headline.** Cada uma com ângulo emocional e estrutura diferentes. Incluir rationale. Apresentar ao usuário e aguardar escolha.
5. **Escrever copy completa.** Seguindo a estrutura aprovada e headline escolhida. Cada seção com: título, body, CTA (quando aplicável). Incluir: benefícios, prova social, FAQ, microcopy.
6. **Copy stress test.** Antes de entregar: cético test, prova check, inflação check, friction check. Reduzir word count em 15-25%.

## Output Format

```
DIAGNÓSTICO
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Awareness level: {nível}
Market sophistication: {stage}
Big Idea: Inimigo: {x} | Mecanismo: {x} | Promessa: {x}
Driver psicológico: {driver}
Framework: {PAS | AIDA | 4Ps | BAB}
Tom selecionado: {tom}

COPY COMPLETA
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

HERO:
Headline: {headline}
Subtítulo: {subtítulo}
CTA: {cta}

SEÇÃO {NOME}:
Título: {título}
Body: {texto}

[... demais seções ...]

CTA FINAL:
Título: {título}
Subtítulo: {neutralizador}
Botão: {cta}

MICROCOPY:
Botões: [lista]
Labels: [lista]
```

## Output Example

```
DIAGNÓSTICO
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Awareness level: Solution Aware
Market sophistication: Stage 3
Big Idea: Inimigo: ferramentas complexas | Mecanismo: setup em 15 min sem código | Promessa: 3x mais conversão
Driver psicológico: Controle
Framework: PAS
Tom selecionado: Tech Confiante

COPY COMPLETA
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

HERO:
Headline: Pare de perder leads por falta de follow-up automatizado.
Subtítulo: TechFlow conecta seu CRM, e-mail e WhatsApp em um fluxo que nunca esquece. Sem código. Em 15 minutos.
CTA: Teste grátis por 14 dias →

SEÇÃO DOR:
Título: Seu time de vendas está perdendo dinheiro todo dia.
Body: Cada lead que não recebe follow-up em 5 minutos tem 80% menos chance de converter.

Seu CRM está cheio de oportunidades paradas.

Sua equipe gasta 3 horas por dia em tarefas manuais que uma automação resolve em segundos.

SEÇÃO SOLUÇÃO:
Título: Automação inteligente que trabalha enquanto seu time vende.
Body: TechFlow conecta suas ferramentas em fluxos automáticos. Captura, qualifica e nutre leads 24/7.

Sem trocar de plataforma. Sem contratar desenvolvedor.

BENEFÍCIOS:
1. Follow-up automático em < 2 min → "Nunca mais perca um lead quente"
2. Dashboard unificado → "Todas as métricas em um lugar"
3. 50+ integrações → "Conecta com o que você já usa"

PROVA SOCIAL:
- "Triplicamos nossa conversão em 60 dias." — CEO, Construtora Horizonte
- "+340% de leads qualificados." — CMO, Casa Verde

COMO FUNCIONA:
1. Conecte suas ferramentas (2 min)
2. Escolha um template (5 min)
3. Personalize (8 min)
4. Ative e acompanhe (tempo real)

FAQ:
P: Preciso saber programar?
R: Não. 100% visual, arrasta e solta.

P: Funciona com meu CRM?
R: Sim. HubSpot, Pipedrive, RD Station e +47 ferramentas.

CTA FINAL:
Título: Pronto para parar de perder leads?
Subtítulo: Sem cartão de crédito. Setup em 15 minutos.
Botão: Começar teste gratuito →

MICROCOPY:
Botões: ["Teste grátis →", "Ver demo", "WhatsApp"]
Labels: ["Sem cartão", "Cancele quando quiser", "15 min setup"]
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Copy foi escrita sem diagnóstico de awareness level e sofisticação
2. Headlines não foram apresentadas como 3 opções para escolha do usuário

## Quality Criteria

- [ ] Diagnóstico completo documentado
- [ ] 3 opções de headline com ângulos diferentes
- [ ] Tom de voz selecionado e aplicado
- [ ] Copy organizada por seção
- [ ] CTAs específicos e ativos
- [ ] Pelo menos 1 neutralizador de objeção
- [ ] Nenhum parágrafo > 3 linhas
