---
task: "Pesquisa de Referências e Estrutura"
order: 1
input: |
  - research_focus: Briefing do projeto com cliente, produto, público, objetivo e nicho
output: |
  - research_output: Brief de pesquisa com referências, insights de concorrentes e estrutura recomendada
---

# Pesquisa de Referências e Estrutura

Pesquisa referências visuais no nicho do cliente, analisa concorrentes diretos e define a arquitetura de informação recomendada para a landing page.

## Process

1. **Ler o briefing do projeto** em `research-focus.md`. Extrair: nome do cliente, produto/serviço, público-alvo, objetivo da LP, nicho de mercado.
2. **Pesquisar 3-5 landing pages de concorrentes** no mesmo nicho. Usar `web_search` com termos como "{nicho} landing page", "{concorrente} site". Para cada referência, documentar: URL, estrutura de seções, padrões visuais, copy patterns, CTAs usados.
3. **Pesquisar tendências de LP no nicho.** Buscar "landing page {nicho} best practices" e "high converting {nicho} website". Extrair frameworks e padrões de conversão relevantes.
4. **Definir a estrutura recomendada de seções.** Com base nas referências e no briefing, definir: quais seções incluir, em que ordem, e o que cada seção deve conter. Justificar cada decisão.
5. **Compilar o research output.** Organizar em formato estruturado com: Referências Analisadas, Insights de Mercado, Estrutura Recomendada, e Gaps.

## Output Format

```yaml
brief:
  cliente: "Nome do cliente"
  produto: "Produto/serviço"
  publico: "Público-alvo"
  objetivo: "Objetivo da LP"
  nicho: "Nicho de mercado"

referencias:
  - url: "https://..."
    nome: "Nome/Descrição"
    insights: "O que funciona, o que copiar, o que evitar"

estrutura_recomendada:
  - secao: "Hero"
    conteudo: "Headline + subtítulo + CTA principal"
    justificativa: "Porque esta seção vem primeiro"
  - secao: "..."

insights_mercado:
  - "Insight 1 com fonte"
  - "Insight 2 com fonte"

gaps:
  - "O que não foi encontrado"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
RESEARCH BRIEF — Construtora Horizonte
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

BRIEFING:
Cliente: Construtora Horizonte
Produto: Construção residencial personalizada
Público: Famílias classe A/B buscando casa própria
Objetivo: Agendamento de visita ao showroom
Nicho: Construção civil residencial

REFERÊNCIAS ANALISADAS:

1. pacaembu.com.br
   - Hero com vídeo de fundo + headline emocional
   - Seção de empreendimentos com filtro por região
   - Prova social: 40 anos, 15.000 unidades entregues
   - CTA principal: "Fale com um consultor"
   - Insight: números grandes geram confiança imediata

2. tenda.com
   - Simulador de financiamento integrado na LP
   - FAQ focado em dúvidas de primeiro imóvel
   - Chat ao vivo no canto inferior
   - Insight: ferramentas interativas aumentam tempo na página

3. mrvengenharia.com.br
   - Grid de fotos do acabamento
   - Timeline do processo de construção
   - Depoimentos em vídeo de moradores
   - Insight: depoimentos em vídeo convertem 35% mais que texto

ESTRUTURA RECOMENDADA:

1. Hero — Headline emocional + foto de alta qualidade do melhor projeto + CTA "Agende uma visita"
   Justificativa: construção é emocional. Mostrar o produto final com foto profissional gera desejo imediato.

2. Números/Credibilidade — "200+ imóveis | 18 anos | 4.9/5 Google"
   Justificativa: prova social imediata reduz ansiedade de compra de alto valor.

3. Diferenciais — 3-4 cards com ícones (acabamento premium, prazo garantido, transparência, etc.)
   Justificativa: diferenciação rápida dos concorrentes sem texto longo.

4. Como funciona — 4 passos do processo (consulta → projeto → construção → entrega)
   Justificativa: desmistifica o processo e reduz objeção de complexidade.

5. Galeria — Fotos dos projetos realizados
   Justificativa: prova visual do trabalho. Construção é produto visual.

6. Depoimentos — 2-3 depoimentos com nome, foto e resultado
   Justificativa: prova social de terceiros é mais credível que auto-promoção.

7. FAQ — 5-6 perguntas mais comuns
   Justificativa: neutraliza objeções antes do CTA final.

8. CTA Final — "Agende sua visita ao showroom — gratuito e sem compromisso"
   Justificativa: repetir CTA com neutralizador de objeção (gratuito, sem compromisso).

GAPS:
- Não encontrei dados de conversão específicos para LPs de construção civil no Brasil
- Simuladores de financiamento podem ser diferenciais mas exigem integração com banco
```

## Quality Criteria

- [ ] Briefing do projeto lido e resumido corretamente
- [ ] Pelo menos 3 referências do nicho com URL e insights específicos
- [ ] Estrutura de seções definida com ordem, conteúdo e justificativa
- [ ] Insights de mercado documentados com fontes
- [ ] Gaps identificados
- [ ] Output segue formato estruturado

## Veto Conditions

Rejeitar e refazer se:
1. Nenhuma referência real do nicho foi analisada (só referências genéricas)
2. Estrutura recomendada não tem justificativa para a ordem das seções
