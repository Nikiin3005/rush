---
execution: subagent
agent: researcher
inputFile: squads/tech-landing-page/output/research-focus.md
outputFile: squads/tech-landing-page/output/research-output.md
model_tier: powerful
---

# Step 03: Pesquisa de Referências e Estrutura

## Context Loading

Load these files before executing:
- `squads/tech-landing-page/output/research-focus.md` — Foco de pesquisa e briefing do cliente
- `pipeline/data/research-brief.md` — Compilação de pesquisa de tendências e frameworks de LP
- `squads/tech-landing-page/_investigations/pinkplus/raw-content.md` — Análise de referência: pinkplus.com.br
- `squads/tech-landing-page/_investigations/agenciasetup/raw-content.md` — Análise de referência: agenciasetup.com.br

## Instructions

### Process
1. **Ler o foco de pesquisa** do arquivo research-focus.md. Identificar o nicho, cliente e objetivo.
2. **Pesquisar 3-5 landing pages de concorrentes** no nicho do cliente usando web_search. Para cada uma, documentar: URL, estrutura de seções, padrões visuais, copy patterns e CTAs.
3. **Cruzar com as investigações** de pinkplus e agenciasetup para identificar padrões de sucesso aplicáveis.
4. **Definir a estrutura recomendada** de seções da LP com ordem, conteúdo esperado e justificativa para cada seção.
5. **Compilar o research output** no formato estruturado.

## Output Format

```
RESEARCH BRIEF — {Nome do Cliente}
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

BRIEFING:
Cliente: {nome}
Produto: {produto/serviço}
Público: {público-alvo}
Objetivo: {ação desejada}
Nicho: {nicho de mercado}

REFERÊNCIAS ANALISADAS:
1. {url} — {insights}
2. {url} — {insights}
3. {url} — {insights}

ESTRUTURA RECOMENDADA:
1. {Seção} — {conteúdo} | Justificativa: {porque}
2. {Seção} — {conteúdo} | Justificativa: {porque}
...

INSIGHTS DE MERCADO:
- {insight com fonte}

GAPS:
- {o que não foi encontrado}
```

## Output Example

```
RESEARCH BRIEF — TechFlow
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

BRIEFING:
Cliente: TechFlow
Produto: Plataforma de automação de marketing B2B
Público: PMEs com time de vendas de 3-20 pessoas
Objetivo: Trial gratuito de 14 dias
Nicho: SaaS B2B / MarTech

REFERÊNCIAS ANALISADAS:

1. activecampaign.com/br
   - Hero com headline de benefício direto + vídeo demo
   - Seção de integrações com grid de logos
   - Pricing com 3 tiers + destaque no plano do meio
   - CTA "Teste grátis" repetido 4x na página
   - Insight: repetição do CTA aumenta conversão em LPs longas

2. rdstation.com
   - Hero com formulário de cadastro embutido
   - Prova social: "40.000 empresas usam"
   - Seção de cases com resultados numéricos
   - Insight: número de clientes no hero gera credibilidade instantânea

3. leadlovers.com
   - Vídeo explicativo no hero
   - Seção "antes vs depois" com comparação visual
   - FAQ extenso (12 perguntas)
   - Insight: seção antes/depois é poderosa para automação

ESTRUTURA RECOMENDADA:

1. Hero — Headline de benefício + subtítulo + CTA "Teste grátis"
   Justificativa: capturar atenção e comunicar proposta em 5 segundos

2. Problema/Dor — Cenário sem automação com dados
   Justificativa: gerar identificação antes de apresentar a solução

3. Solução — O que o TechFlow faz em 1 parágrafo
   Justificativa: resposta direta à dor apresentada

4. Benefícios — 3 cards glass com ícone + título + descrição
   Justificativa: benefícios tangíveis em formato escaneável

5. Como funciona — 4 passos visuais com timeline
   Justificativa: reduz objeção de complexidade ("parece difícil")

6. Prova social — Depoimentos + logos de clientes
   Justificativa: credibilidade de terceiros vale mais que auto-promoção

7. FAQ — 5-6 perguntas sobre trial, preço, integração
   Justificativa: neutralizar objeções antes do CTA final

8. CTA Final — Repetir oferta com neutralizador
   Justificativa: última chance de conversão com friction removal

INSIGHTS DE MERCADO:
- 73% dos SaaS B2B brasileiros usam trial gratuito como CTA principal (fonte: SaaS Brasil 2025)
- LPs com prova social numérica convertem 35% mais que sem (fonte: Unbounce)

GAPS:
- Não encontrei benchmarks de conversão específicos para automação B2B no Brasil
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Nenhuma referência real do nicho do cliente foi pesquisada (apenas referências genéricas)
2. Estrutura recomendada não inclui justificativa para cada seção

## Quality Criteria

- [ ] Pelo menos 3 referências do nicho analisadas com insights específicos
- [ ] Estrutura de seções com ordem, conteúdo e justificativa
- [ ] Todas as fontes incluem URL
- [ ] Gaps documentados
- [ ] Output segue o formato estruturado
