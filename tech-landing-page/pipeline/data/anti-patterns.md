# Anti-Patterns — Tech Landing Page

## Copy — Nunca Fazer

1. **Headline genérica sem proposta de valor.** "Bem-vindo ao nosso site" ou "Somos a melhor agência" não dizem nada. A headline deve comunicar: para quem + benefício + diferencial em uma frase.

2. **CTA vago ou passivo.** "Saiba mais" e "Clique aqui" não convertem. Use verbos de ação específicos: "Agende sua consultoria gratuita", "Comece seu teste de 7 dias", "Baixe o guia completo".

3. **Paredes de texto sem hierarquia.** Blocos de 5+ linhas sem quebra são ignorados. Máximo 3 linhas por parágrafo. Uma ideia por bloco.

4. **Prometer sem provar.** "Resultados garantidos" sem dados, cases ou depoimentos é ruído. Toda promessa precisa de prova: número, depoimento, logo de cliente, ou estudo de caso.

5. **Ignorar o nível de consciência do público.** Copy de venda direta para público que nem sabe que tem o problema é desperdício. Calibrar a agressividade da mensagem ao awareness level.

6. **Usar jargão técnico com público leigo.** "Otimização de funil multi-touchpoint" não significa nada para o dono de uma clínica. Traduzir em impacto no negócio.

## Design — Nunca Fazer

1. **Glassmorphism sobre fundo sólido preto.** O efeito é praticamente invisível. Precisa de gradientes ambiente com orbs de cor vibrantes atrás do UI.

2. **Mais de 5 cores no design system.** Gera ruído visual. Usar: primary + secondary + accent + background + text. Variações derivadas dessas 5.

3. **Texto sobre imagem sem proteção de contraste.** Texto legível sobre foto ou fundo complexo exige: overlay sólido 60%+, gradiente, ou backdrop-filter blur.

4. **Font-size abaixo de 16px para body text.** No mobile, textos pequenos são ilegíveis. Mínimo 16px body, 24px+ headings, 32px+ hero.

5. **Absolute positioning para layout principal.** Quebra quando o conteúdo varia. Usar CSS Grid ou Flexbox. Absolute só para decoração.

6. **Animações pesadas que bloqueiam scroll.** Parallax excessivo, vídeos autoplay, animações de entrada longas — prejudicam performance e frustram o usuário.

## Técnico — Nunca Fazer

1. **Dependências externas quebráveis.** CDN de framework CSS, JavaScript externo, imagens de terceiros. Tudo que pode ficar offline vai ficar. Self-contained.

2. **Sem meta viewport.** Sem `<meta name="viewport" content="width=device-width, initial-scale=1.0">` o site não é responsivo no mobile.

3. **IDs e classes sem semântica.** `.box1`, `.div-wrapper`, `.section-2` não comunicam nada. Usar `.hero-headline`, `.benefits-grid`, `.testimonial-card`.
