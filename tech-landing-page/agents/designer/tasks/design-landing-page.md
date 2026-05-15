---
task: "Design e Desenvolvimento da Landing Page"
order: 1
input: |
  - copy_output: Copy completa aprovada organizada por seção
  - design_references: Output examples e investigation data para referência visual
output: |
  - landing_page: Arquivo HTML self-contained com CSS inline e JS responsivo
---

# Design e Desenvolvimento da Landing Page

Cria o HTML/CSS/JS responsivo completo da landing page com estética dark mode premium + glassmorphism futurista, usando a copy aprovada.

## Process

1. **Ler a copy aprovada.** Extrair todo o texto por seção: headlines, subtítulos, body, CTAs, microcopy, benefícios, depoimentos, FAQ. Ler também `pipeline/data/output-examples.md` para referência de design system.
2. **Definir o design system.** Documentar antes de codar:
   - **Cores**: Background (#0A-#14 range), Surface, Glass, Primary (roxo/cyan/magenta), Secondary, Text (#F0F0F5), Muted
   - **Tipografia**: Font family (Inter ou Poppins), size scale com clamp(), weight scale
   - **Espaçamento**: Base unit, section padding, container max-width, grid gap
   - **Componentes**: Glass card (backdrop-filter, border, radius), CTA button (gradient, radius, padding), hover states
   - **Gradient orbs**: Posição, cor, opacidade dos orbs de background
3. **Desenvolver o HTML/CSS.** Criar um arquivo HTML self-contained com:
   - CSS inline com custom properties
   - Layout responsivo com CSS Grid/Flexbox
   - Media queries para 375px, 768px e 1440px
   - Glassmorphism em cards e elementos-chave
   - Gradient orbs posicionados no background
   - Animações sutis (fade-in, hover transitions)
   - HTML semântico (header, nav, main, section, footer)
4. **Implementar cada seção.** Seguir a ordem da copy aprovada. Cada seção com hierarquia visual clara: título → body → CTA (quando aplicável).
5. **Revisar responsividade.** Mentalmente testar cada breakpoint. Verificar que textos não ficam cortados, cards se empilham corretamente e CTAs estão acessíveis no mobile.
6. **Entregar o HTML final.** Arquivo único, pronto para abrir no navegador.

## Output Format

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{Título da página}</title>
  <meta name="description" content="{Meta description}">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');
    :root {
      --bg: #0A0A0F;
      --surface: #14141F;
      --glass: rgba(255,255,255,0.05);
      --glass-border: rgba(255,255,255,0.08);
      --primary: #6C5CE7;
      --secondary: #00D2FF;
      --text: #F0F0F5;
      --muted: #6B6B80;
      /* ... spacing, radius, etc */
    }
    /* ... CSS completo */
  </style>
</head>
<body>
  <header><!-- nav --></header>
  <main>
    <section class="hero"><!-- ... --></section>
    <section class="pain"><!-- ... --></section>
    <!-- demais seções -->
  </main>
  <footer><!-- ... --></footer>
</body>
</html>
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechFlow — Automação que converte</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');
    :root {
      --bg: #0A0A0F;
      --surface: #14141F;
      --glass: rgba(255,255,255,0.05);
      --glass-border: rgba(255,255,255,0.08);
      --primary: #6C5CE7;
      --secondary: #00D2FF;
      --text: #F0F0F5;
      --muted: #6B6B80;
      --radius: 16px;
      --container: 1200px;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Inter', sans-serif;
      font-weight: 400;
      line-height: 1.6;
      overflow-x: hidden;
    }
    body::before {
      content: '';
      position: fixed; top: 0; left: 0;
      width: 100%; height: 100%;
      background:
        radial-gradient(circle at 20% 30%, rgba(108,92,231,0.12), transparent 50%),
        radial-gradient(circle at 80% 70%, rgba(0,210,255,0.08), transparent 50%);
      pointer-events: none; z-index: 0;
    }
    .container { max-width: var(--container); margin: 0 auto; padding: 0 24px; position: relative; z-index: 1; }
    .hero {
      min-height: 90vh;
      display: flex; flex-direction: column;
      justify-content: center; align-items: center;
      text-align: center;
      padding: clamp(60px, 10vw, 120px) 24px;
    }
    .hero h1 {
      font-size: clamp(32px, 5vw, 64px);
      font-weight: 800;
      line-height: 1.1;
      max-width: 800px;
    }
    .hero h1 span { color: var(--secondary); }
    .hero p {
      font-size: clamp(16px, 1.5vw, 20px);
      color: var(--muted);
      max-width: 600px;
      margin-top: 24px;
    }
    .btn-primary {
      display: inline-flex; align-items: center; gap: 8px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: #fff; border: none; border-radius: 12px;
      padding: 16px 32px; font-size: 16px; font-weight: 600;
      cursor: pointer; margin-top: 32px;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .btn-primary:hover {
      transform: scale(1.03);
      box-shadow: 0 0 30px rgba(108,92,231,0.4);
    }
    .glass-card {
      background: var(--glass);
      border: 1px solid var(--glass-border);
      border-radius: var(--radius);
      backdrop-filter: blur(20px);
      padding: 32px;
    }
  </style>
</head>
<body>
  <main>
    <section class="hero">
      <div class="container">
        <h1>Pare de perder leads por falta de <span>follow-up automatizado.</span></h1>
        <p>TechFlow conecta seu CRM, e-mail e WhatsApp em um fluxo que nunca esquece. Sem código. Em 15 minutos.</p>
        <button class="btn-primary">Teste grátis por 14 dias →</button>
      </div>
    </section>
  </main>
</body>
</html>
```

## Quality Criteria

- [ ] Design system documentado com valores exatos (hex, px, rem)
- [ ] HTML self-contained (sem dependências externas exceto Google Fonts)
- [ ] Background usa quase-preto com tom de cor (não #000)
- [ ] Glassmorphism em cards/elementos-chave com backdrop-filter blur
- [ ] Gradient orbs no background (radial-gradient com cores vibrantes)
- [ ] Responsivo com clamp() e media queries (375px, 768px, 1440px)
- [ ] Custom properties CSS para cores e espaçamentos
- [ ] HTML semântico (header, main, section, footer)
- [ ] Contraste WCAG AA verificado
- [ ] Toda copy aprovada implementada (nenhum texto faltando)

## Veto Conditions

Rejeitar e refazer se:
1. HTML tem dependências externas (CDN de framework, JavaScript externo, imagens de terceiros)
2. Background usa #000000 puro ou não tem gradient orbs para dar profundidade ao glassmorphism
