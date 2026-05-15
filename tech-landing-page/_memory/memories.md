# Squad Memory: Tech Landing Page

## Estilo de Escrita
- Tom aprovado: Mix Tech Confiante + Premium Sofisticado + Acessível
- Framework preferido: BAB (Before-After-Bridge)
- Frases curtas e impactantes funcionam melhor que parágrafos longos
- Headline ideal: < 10 palavras com verbo de impacto ou benefício emocional
- Neutralizadores de objeção antes do CTA final aumentam conversão percebida

## Design Visual
- Paleta base: dark navy (#08081A) + roxo vibrante (#7B2FBE / #A855F7 / #C084FC) + branco (#F0F0F5)
- Glassmorphism como acento, não como linguagem inteira (blur 20px, rgba borders 0.08)
- Gradient orbs no body::before criam profundidade atmosférica sem pesar
- Hero glow com radial-gradient blur(80px) cria foco visual
- Background-clip gradient text para highlight de palavras-chave
- Design system com custom properties é essencial para manutenção
- --muted precisa ser pelo menos #8A8AA5 para WCAG AA compliance (ratio 5.2:1+)

## Estrutura de Conteúdo
- Estrutura aprovada: Hero → Portfólio → Serviços → Sobre → Números → Processo → CTA → Footer
- Portfólio cedo (antes de serviços) funciona melhor para produtoras — o trabalho é o produto
- Seção de processo em 4 passos reduz objeção de complexidade
- Nav fixa com glass blur + CTA na nav é padrão eficaz

## Proibições Explícitas
- NUNCA usar true black (#000000) como fundo
- NUNCA exagerar no glassmorphism — legibilidade primeiro
- NUNCA omitir neutralizador de objeção antes do CTA principal
- NUNCA usar --muted abaixo de #8A8AA5 (falha WCAG AA)

## Técnico (específico do squad)
- Self-contained HTML: única dependência externa permitida = Google Fonts
- IntersectionObserver para animações de scroll (fade-in + translateY)
- Fonts: Playfair Display (headings) + Inter (body) — combinação aprovada
- clamp() para tipografia responsiva é obrigatório
- Breakpoints: 768px (tablet) e 480px (mobile) como mínimo
- Sugestão para futuro: adicionar breakpoint 1024px e prefers-reduced-motion
