---
execution: inline
agent: designer
inputFile: squads/tech-landing-page/output/copy-output.md
outputFile: squads/tech-landing-page/output/landing-page.html
---

# Step 07: Design da Landing Page

## Context Loading

Load these files before executing:
- `squads/tech-landing-page/output/copy-output.md` — Copy aprovada organizada por seção
- `pipeline/data/output-examples.md` — Exemplos de design system e HTML de referência
- `pipeline/data/anti-patterns.md` — Erros de design a evitar
- `squads/tech-landing-page/_investigations/pinkplus/raw-content.md` — Padrões visuais pinkplus
- `squads/tech-landing-page/_investigations/agenciasetup/raw-content.md` — Padrões visuais agenciasetup

## Instructions

### Process
1. **Ler a copy aprovada.** Extrair todo o texto por seção. Contar seções e mapear o conteúdo.
2. **Definir o design system.** Documentar com valores exatos antes de codar:
   - Cores: background (#0A-#14 range com tom azulado/roxo), surface, glass, primary, secondary, text, muted
   - Gradient orbs: posições, cores (roxo, cyan, magenta), opacidade
   - Tipografia: Inter ou Poppins, scale com clamp(), weights 400-800
   - Espaçamento: base unit, section padding com clamp(), container max-width 1200px
   - Componentes: glass card, CTA button, hover states
3. **Criar o HTML/CSS responsivo.** Arquivo único self-contained com:
   - Custom properties CSS para todo o design system
   - Layout com CSS Grid e Flexbox
   - Media queries: 375px (mobile), 768px (tablet), 1440px (desktop)
   - Glassmorphism em cards e elementos-chave (backdrop-filter blur)
   - Gradient orbs com radial-gradient no body::before
   - Animações sutis (transitions, hover effects)
   - HTML semântico (header, nav, main, section, footer)
4. **Implementar toda a copy.** Cada seção com hierarquia visual clara. Nenhum texto da copy pode faltar.
5. **Verificar acessibilidade.** Contraste WCAG AA (4.5:1 body, 3:1 large text). Texto branco sobre dark.
6. **Salvar como landing-page.html.** Pronto para abrir no navegador.

## Output Format

Arquivo HTML completo self-contained com todas as seções da copy implementadas. O arquivo deve funcionar abrindo diretamente no navegador (sem servidor).

Estrutura mínima:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{título}</title>
  <meta name="description" content="{meta description}">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');
    :root { /* design system */ }
    /* CSS completo com media queries */
  </style>
</head>
<body>
  <header><!-- nav + logo --></header>
  <main>
    <section class="hero"><!-- headline + CTA --></section>
    <!-- demais seções da copy -->
  </main>
  <footer><!-- dados legais --></footer>
  <script>/* JS mínimo para interações: FAQ accordion, smooth scroll */</script>
</body>
</html>
```

## Output Example

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechFlow — Automação que converte</title>
  <meta name="description" content="Automatize seu follow-up de leads em 15 minutos. Sem código. Teste grátis.">
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
      --section-pad: clamp(60px, 8vw, 120px);
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Inter', sans-serif;
      line-height: 1.6;
      overflow-x: hidden;
    }
    body::before {
      content: '';
      position: fixed; inset: 0;
      background:
        radial-gradient(circle at 20% 30%, rgba(108,92,231,0.12), transparent 50%),
        radial-gradient(circle at 80% 70%, rgba(0,210,255,0.08), transparent 50%);
      pointer-events: none;
    }
    .container { max-width: var(--container); margin: 0 auto; padding: 0 24px; position: relative; }
    .hero {
      min-height: 90vh; display: flex; flex-direction: column;
      justify-content: center; align-items: center; text-align: center;
      padding: var(--section-pad) 24px;
    }
    .hero h1 { font-size: clamp(32px, 5vw, 64px); font-weight: 800; line-height: 1.1; max-width: 800px; }
    .hero h1 span { color: var(--secondary); }
    .hero p { font-size: clamp(16px, 1.5vw, 20px); color: var(--muted); max-width: 600px; margin-top: 24px; }
    .btn-primary {
      display: inline-flex; align-items: center; gap: 8px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: #fff; border: none; border-radius: 12px;
      padding: 16px 32px; font-size: 16px; font-weight: 600;
      cursor: pointer; margin-top: 32px; text-decoration: none;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .btn-primary:hover { transform: scale(1.03); box-shadow: 0 0 30px rgba(108,92,231,0.4); }
    .glass-card {
      background: var(--glass); border: 1px solid var(--glass-border);
      border-radius: var(--radius); backdrop-filter: blur(20px); padding: 32px;
    }
    section { padding: var(--section-pad) 0; }
    @media (max-width: 768px) {
      .benefits-grid { grid-template-columns: 1fr !important; }
    }
  </style>
</head>
<body>
  <main>
    <section class="hero">
      <div class="container">
        <h1>Pare de perder leads por falta de <span>follow-up automatizado.</span></h1>
        <p>Conecte CRM, e-mail e WhatsApp em um fluxo que nunca esquece. Sem código. 15 minutos.</p>
        <a href="#" class="btn-primary">Teste grátis por 14 dias →</a>
      </div>
    </section>
  </main>
</body>
</html>
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. HTML tem dependências externas (CDN, framework CSS, JS externo, imagens de terceiros)
2. Background usa #000000 ou não tem gradient orbs para profundidade do glassmorphism

## Quality Criteria

- [ ] Design system documentado com valores exatos
- [ ] HTML self-contained (apenas Google Fonts externo)
- [ ] Dark mode com tom de cor (não pure black)
- [ ] Glassmorphism em cards/elementos-chave
- [ ] Gradient orbs no background
- [ ] Responsivo (375px, 768px, 1440px)
- [ ] Custom properties CSS
- [ ] HTML semântico
- [ ] Contraste WCAG AA
- [ ] Toda copy aprovada implementada
