---
task: "Copy Completa da Landing Page"
order: 1
input: |
  - research_output: Brief de pesquisa com estrutura recomendada
  - tone_of_voice: Tom de voz selecionado pelo usuário
output: |
  - copy_output: Copy completa organizada por seção com headlines, body, CTAs e microcopy
---

# Copy Completa da Landing Page

Escreve toda a copy da landing page seguindo a estrutura de pesquisa aprovada e o tom de voz selecionado. Inclui headlines, subtítulos, body text, CTAs, microcopy e prova social.

## Process

1. **Ler o research output aprovado.** Extrair: estrutura de seções, insights de mercado, referências. Ler também o briefing original para contexto do cliente.
2. **Seleção de tom de voz.** Ler `pipeline/data/tone-of-voice.md`. Recomendar o tom mais adequado ao cliente e público. Apresentar as 6 opções e aguardar escolha do usuário.
3. **Diagnóstico de copy.** Identificar: awareness level do público, sofisticação de mercado, Big Idea (inimigo + mecanismo único + promessa), driver psicológico dominante.
4. **Criar 3 opções de headline.** Cada uma com ângulo emocional e estrutura diferentes. Incluir rationale de 1 linha para cada. Apresentar ao usuário e aguardar escolha.
5. **Escrever copy por seção.** Seguindo a estrutura aprovada e a headline escolhida, escrever: headline, subtítulo, body de cada seção, benefícios, prova social, FAQ, CTAs. Aplicar o framework de persuasão escolhido (PAS, AIDA, 4Ps ou BAB).
6. **Copy stress test.** Antes de entregar: teste do cético, verificação de provas, checagem de inflação, verificação de fricção, redução de 15-25% do word count.

## Output Format

```yaml
diagnostico:
  awareness_level: "..."
  market_sophistication: "..."
  big_idea:
    inimigo: "..."
    mecanismo_unico: "..."
    promessa: "..."
  driver_psicologico: "..."
  framework: "PAS | AIDA | 4Ps | BAB"
  tom_selecionado: "..."

copy:
  hero:
    headline: "..."
    subtitulo: "..."
    cta_principal: "..."
  secao_dor:
    titulo: "..."
    body: "..."
  secao_solucao:
    titulo: "..."
    body: "..."
  beneficios:
    - titulo: "..."
      descricao: "..."
  prova_social:
    - depoimento/numero/logo
  como_funciona:
    - passo: "..."
  faq:
    - pergunta: "..."
      resposta: "..."
  cta_final:
    titulo: "..."
    subtitulo: "..."
    botao: "..."
  microcopy:
    botoes: ["..."]
    labels: ["..."]
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
DIAGNÓSTICO
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Awareness level: Solution Aware (sabe que precisa de automação, não conhece TechFlow)
Market sophistication: Stage 3 (mercado competitivo, precisa de mecanismo diferenciador)
Big Idea:
  Inimigo: Ferramentas complexas que exigem desenvolvedor
  Mecanismo único: Setup em 15 minutos sem código
  Promessa: Triplicar conversão com automação que qualquer pessoa configura
Driver psicológico: Controle (recuperar poder sobre a operação)
Framework: PAS (Problem-Agitate-Solution)
Tom selecionado: Tech Confiante

COPY COMPLETA
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

HERO:
Headline: Pare de perder leads por falta de follow-up automatizado.
Subtítulo: TechFlow conecta seu CRM, e-mail e WhatsApp em um fluxo que nunca esquece de fazer follow-up. Sem código. Em 15 minutos.
CTA: Teste grátis por 14 dias →

SEÇÃO DOR:
Título: Seu time de vendas está perdendo dinheiro todo dia.
Body: Cada lead que não recebe follow-up em 5 minutos tem 80% menos chance de converter.

Seu CRM está cheio de oportunidades paradas.

Sua equipe gasta 3 horas por dia em tarefas manuais que uma automação resolve em segundos.

SEÇÃO SOLUÇÃO:
Título: Automação inteligente que trabalha enquanto seu time vende.
Body: TechFlow conecta suas ferramentas em fluxos automáticos que capturam, qualificam e nutrem leads 24/7.

Sem trocar de plataforma. Sem contratar desenvolvedor. Sem perder mais um lead.

BENEFÍCIOS:
1. Follow-up automático em < 2 min → "Nunca mais perca um lead quente"
2. Dashboard unificado → "Todas as métricas em um lugar"
3. 50+ integrações nativas → "Conecta com o que você já usa"

PROVA SOCIAL:
- "Triplicamos nossa taxa de conversão em 60 dias." — CEO, Construtora Horizonte
- "+340% de leads qualificados no primeiro mês." — CMO, Casa Verde

COMO FUNCIONA:
1. Conecte suas ferramentas (2 minutos)
2. Escolha um template de fluxo (5 minutos)
3. Personalize para seu processo (8 minutos)
4. Ative e acompanhe os resultados (tempo real)

FAQ:
P: Preciso saber programar?
R: Não. O TechFlow é 100% visual, arrasta e solta.

P: Funciona com meu CRM atual?
R: Sim. Integramos com HubSpot, Pipedrive, RD Station e mais 47 ferramentas.

P: Posso cancelar a qualquer momento?
R: Sim. Sem multa, sem burocracia. Cancela em 2 cliques.

CTA FINAL:
Título: Pronto para parar de perder leads?
Subtítulo: Comece grátis. Sem cartão de crédito. Setup em 15 minutos.
Botão: Começar teste gratuito →

MICROCOPY:
Botões: ["Teste grátis →", "Ver demonstração", "Fale no WhatsApp"]
Labels: ["Sem cartão de crédito", "Cancele quando quiser", "Setup em 15 min"]
```

## Quality Criteria

- [ ] Diagnóstico completo (awareness, sofisticação, Big Idea, driver, framework)
- [ ] 3 opções de headline apresentadas com ângulos diferentes
- [ ] Tom de voz selecionado e aplicado consistentemente
- [ ] Copy organizada por seção seguindo estrutura aprovada
- [ ] CTAs específicos e ativos em todas as seções relevantes
- [ ] Pelo menos 1 neutralizador de objeção antes do CTA final
- [ ] Nenhum parágrafo com mais de 3 linhas
- [ ] Copy stress test executado (cético, provas, inflação, fricção)

## Veto Conditions

Rejeitar e refazer se:
1. Copy foi escrita sem diagnóstico de awareness level e sofisticação de mercado
2. Headlines não foram apresentadas como 3 opções para o usuário escolher
