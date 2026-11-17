Abaixo está uma versão completa em **um único arquivo**, sem dividir. Salve como `index.html` e abra no navegador.

```html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Devil May Cry — Trabalho Escolar</title>

  <meta
    name="description"
    content="Site escolar informativo sobre Devil May Cry, sua história, personagens, jogabilidade e legado."
  />

  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />

  <link
    href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;600;700;800;900&family=Inter:wght@300;400;500;600;700&display=swap"
    rel="stylesheet"
  />

  <style>
    :root {
      --background: #06080d;
      --surface: #0a0d14;
      --surface-light: #10141e;
      --red: #ff314f;
      --red-light: #ff7187;
      --blue: #5185ff;
      --white: #ffffff;
      --muted: rgba(255, 255, 255, 0.55);
      --border: rgba(255, 255, 255, 0.12);
      --display: "Cinzel", serif;
      --sans: "Inter", sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      background: var(--background);
    }

    body {
      overflow-x: hidden;
      background: var(--background);
      color: var(--white);
      font-family: var(--sans);
    }

    button,
    a {
      color: inherit;
      font: inherit;
    }

    button {
      border: 0;
      cursor: pointer;
    }

    a {
      text-decoration: none;
    }

    img {
      display: block;
      max-width: 100%;
    }

    ::selection {
      color: white;
      background: var(--red);
    }

    .container {
      width: min(1180px, calc(100% - 40px));
      margin-inline: auto;
    }

    .section {
      padding-block: 120px;
    }

    .eyebrow {
      color: rgba(255, 255, 255, 0.4);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.25em;
      text-transform: uppercase;
    }

    .section-title {
      margin-top: 18px;
      font-family: var(--display);
      font-size: clamp(2.3rem, 6vw, 4.8rem);
      line-height: 1;
      letter-spacing: -0.04em;
      text-transform: uppercase;
    }

    .section-title em {
      color: var(--red);
      font-weight: 500;
    }

    .button {
      display: inline-flex;
      min-height: 50px;
      align-items: center;
      justify-content: center;
      padding-inline: 22px;
      border: 1px solid var(--border);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      transition: 0.25s ease;
    }

    .button-primary {
      border-color: var(--red);
      background: #df1d42;
      box-shadow: 0 14px 40px rgba(223, 29, 66, 0.25);
    }

    .button:hover {
      border-color: rgba(255, 255, 255, 0.5);
      color: white;
      transform: translateY(-2px);
    }

    .header {
      position: fixed;
      z-index: 100;
      top: 0;
      right: 0;
      left: 0;
      border-bottom: 1px solid var(--border);
      background: rgba(7, 9, 14, 0.84);
      backdrop-filter: blur(18px);
    }

    .header-content {
      display: flex;
      min-height: 72px;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 13px;
      font-family: var(--display);
      font-size: 14px;
      font-weight: 800;
      letter-spacing: 0.14em;
      text-transform: uppercase;
    }

    .logo-mark {
      display: grid;
      width: 37px;
      height: 37px;
      place-items: center;
      border: 1px solid var(--red);
      color: var(--red-light);
      font-size: 19px;
      transform: rotate(45deg);
    }

    .logo-mark span {
      transform: rotate(-45deg);
    }

    .logo-red {
      color: var(--red);
    }

    .logo small {
      display: block;
      margin-top: 4px;
      color: rgba(255, 255, 255, 0.35);
      font-family: var(--sans);
      font-size: 7px;
      letter-spacing: 0.3em;
    }

    .navigation {
      display: flex;
      align-items: center;
      gap: 28px;
    }

    .navigation a {
      color: rgba(255, 255, 255, 0.6);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.13em;
      text-transform: uppercase;
      transition: color 0.2s ease;
    }

    .navigation a:hover {
      color: white;
    }

    .menu-button {
      display: none;
      width: 42px;
      height: 42px;
      border: 1px solid var(--border);
      background: transparent;
      color: white;
      font-size: 22px;
    }

    .hero {
      position: relative;
      display: flex;
      min-height: 100vh;
      align-items: flex-end;
      padding-block: 160px 90px;
      background:
        linear-gradient(90deg, rgba(5, 7, 12, 0.97), rgba(5, 7, 12, 0.74) 48%, rgba(5, 7, 12, 0.2)),
        linear-gradient(0deg, #06080d, transparent 38%),
        url("https://images.unsplash.com/photo-1671393332989-fb0ea854a6ed?auto=format&fit=crop&w=2000&q=90")
        center / cover;
    }

    .hero::before {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(255, 255, 255, 0.07) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.07) 1px, transparent 1px);
      background-size: 80px 80px;
      content: "";
      mask-image: linear-gradient(to right, black, transparent 65%);
    }

    .hero-content {
      position: relative;
      z-index: 2;
    }

    .hero-label {
      display: flex;
      align-items: center;
      gap: 12px;
      color: var(--red-light);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.26em;
      text-transform: uppercase;
    }

    .hero-label::before {
      width: 44px;
      height: 1px;
      background: var(--red);
      content: "";
    }

    .hero h1 {
      margin-top: 25px;
      font-family: var(--display);
      font-size: clamp(4rem, 11vw, 9rem);
      font-weight: 900;
      line-height: 0.78;
      letter-spacing: -0.06em;
      text-transform: uppercase;
    }

    .outlined {
      display: block;
      color: transparent;
      -webkit-text-stroke: 1px rgba(255, 255, 255, 0.75);
    }

    .hero-description {
      max-width: 690px;
      margin-top: 35px;
      padding-left: 20px;
      border-left: 1px solid var(--red);
      color: rgba(255, 255, 255, 0.65);
      font-size: 18px;
      line-height: 1.7;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 34px;
    }

    .universe-grid {
      display: grid;
      grid-template-columns: 0.75fr 1.25fr;
      gap: 80px;
    }

    .universe-intro {
      color: rgba(255, 255, 255, 0.78);
      font-size: clamp(1.5rem, 3vw, 2rem);
      font-weight: 300;
      line-height: 1.65;
    }

    .universe-intro strong {
      color: white;
      font-weight: 500;
    }

    .text-columns {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 35px;
      margin-top: 40px;
      padding-top: 35px;
      border-top: 1px solid var(--border);
    }

    .body-text {
      color: rgba(255, 255, 255, 0.48);
      font-size: 14px;
      line-height: 1.8;
    }

    .quote {
      margin-top: 45px;
      padding-block: 28px;
      border-block: 1px solid var(--border);
      color: #93b9ff;
      font-family: var(--display);
      font-size: clamp(1.3rem, 3vw, 2rem);
      font-style: italic;
      line-height: 1.5;
    }

    .story {
      border-block: 1px solid var(--border);
      background:
        linear-gradient(90deg, rgba(6, 8, 13, 0.98), rgba(6, 8, 13, 0.87)),
        url("https://images.unsplash.com/photo-1719042948053-eafa289f90fb?auto=format&fit=crop&w=1800&q=80")
        center / cover;
    }

    .story-grid {
      display: grid;
      grid-template-columns: 0.7fr 1.3fr;
      gap: 70px;
    }

    .story-summary {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.8;
    }

    .chapters {
      border-top: 1px solid var(--border);
    }

    .chapter {
      display: grid;
      grid-template-columns: 70px 1fr;
      gap: 24px;
      padding-block: 34px;
      border-bottom: 1px solid var(--border);
    }

    .chapter-number {
      color: transparent;
      font-family: var(--display);
      font-size: 35px;
      font-weight: 800;
      -webkit-text-stroke: 1px rgba(132, 169, 255, 0.6);
    }

    .chapter-era {
      color: var(--red-light);
      font-size: 9px;
      font-weight: 700;
      letter-spacing: 0.2em;
      text-transform: uppercase;
    }

    .chapter h3 {
      margin-top: 8px;
      font-family: var(--display);
      font-size: 27px;
      text-transform: uppercase;
    }

    .chapter p:last-child {
      margin-top: 14px;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    .characters {
      background: var(--surface);
    }

    .section-heading {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 30px;
      margin-bottom: 55px;
    }

    .section-heading > p {
      max-width: 400px;
      color: var(--muted);
      font-size: 14px;
      line-height: 1.7;
    }

    .character-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
    }

    .character-card {
      position: relative;
      min-height: 680px;
      overflow: hidden;
      padding: 25px;
      border: 1px solid var(--border);
      background: linear-gradient(145deg, rgba(255, 255, 255, 0.05), transparent);
      transition: 0.35s ease;
    }

    .character-card:hover {
      border-color: rgba(255, 255, 255, 0.3);
      transform: translateY(-8px);
    }

    .character-card img {
      position: absolute;
      top: 8px;
      left: 50%;
      width: auto;
      height: 72%;
      max-width: none;
      object-fit: contain;
      transform: translateX(-50%);
      filter: saturate(0.8);
    }

    .character-card::after {
      position: absolute;
      z-index: 1;
      inset: 0;
      background: linear-gradient(to bottom, transparent 25%, rgba(9, 12, 19, 0.2) 46%, #090c13 70%);
      content: "";
    }

    .character-content {
      position: relative;
      z-index: 2;
      display: flex;
      min-height: 625px;
      flex-direction: column;
      justify-content: flex-end;
    }

    .character-role {
      margin-bottom: 8px;
      color: rgba(255, 255, 255, 0.5);
      font-size: 9px;
      font-weight: 700;
      letter-spacing: 0.18em;
      text-transform: uppercase;
    }

    .character-card h3 {
      font-family: var(--display);
      font-size: 43px;
      text-transform: uppercase;
    }

    .character-description {
      margin-top: 18px;
      color: rgba(255, 255, 255, 0.58);
      font-size: 13px;
      line-height: 1.75;
    }

    .character-info {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 18px;
      margin-top: 24px;
      padding-top: 18px;
      border-top: 1px solid var(--border);
    }

    .character-info small {
      display: block;
      color: rgba(255, 255, 255, 0.34);
      font-size: 8px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .character-info strong {
      display: block;
      margin-top: 8px;
      font-size: 10px;
      line-height: 1.5;
      text-transform: uppercase;
    }

    .supporting-title {
      display: flex;
      align-items: center;
      gap: 20px;
      margin-top: 90px;
      margin-bottom: 30px;
      font-family: var(--display);
      font-size: 23px;
      text-transform: uppercase;
    }

    .supporting-title::after {
      height: 1px;
      flex: 1;
      background: var(--border);
      content: "";
    }

    .supporting-grid,
    .extras-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      border-top: 1px solid var(--border);
      border-left: 1px solid var(--border);
    }

    .supporting-card,
    .extra-card {
      min-height: 220px;
      padding: 27px;
      border-right: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      background: rgba(255, 255, 255, 0.015);
    }

    .supporting-card small,
    .extra-tag {
      color: var(--red-light);
      font-size: 8px;
      font-weight: 700;
      letter-spacing: 0.16em;
      text-transform: uppercase;
    }

    .supporting-card h4,
    .extra-card h3 {
      margin-top: 10px;
      font-family: var(--display);
      font-size: 21px;
      text-transform: uppercase;
    }

    .supporting-card p,
    .extra-card p {
      margin-top: 15px;
      color: rgba(255, 255, 255, 0.46);
      font-size: 12px;
      line-height: 1.75;
    }

    .gameplay {
      position: relative;
      background:
        linear-gradient(110deg, #07090f 10%, rgba(7, 9, 15, 0.94) 50%, rgba(7, 9, 15, 0.55)),
        url("https://images.unsplash.com/photo-1511200903586-f88075762629?auto=format&fit=crop&w=1800&q=85")
        center / cover;
    }

    .gameplay-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 70px;
      margin-top: 25px;
    }

    .gameplay-description {
      max-width: 570px;
      margin-top: 28px;
      color: var(--muted);
      font-size: 15px;
      line-height: 1.8;
    }

    .gameplay-item {
      display: grid;
      grid-template-columns: 45px 1fr;
      gap: 15px;
      margin-bottom: 12px;
      padding: 20px;
      border: 1px solid var(--border);
      background: rgba(8, 10, 16, 0.68);
      backdrop-filter: blur(12px);
    }

    .gameplay-number {
      color: var(--red);
      font-family: var(--display);
    }

    .gameplay-item h3 {
      font-family: var(--display);
      font-size: 20px;
      text-transform: uppercase;
    }

    .gameplay-item p {
      margin-top: 6px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.7;
    }

    .rank-strip {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      margin-top: 60px;
      border-block: 1px solid var(--border);
    }

    .rank-strip span {
      padding-block: 22px;
      border-right: 1px solid var(--border);
      color: rgba(255, 255, 255, 0.16);
      font-family: var(--display);
      font-size: clamp(1rem, 3vw, 2.3rem);
      font-weight: 800;
      text-align: center;
    }

    .rank-strip span:nth-last-child(-n + 3) {
      color: var(--red);
    }

    .extras {
      background:
        radial-gradient(circle at 80% 20%, rgba(62, 100, 255, 0.12), transparent 30%),
        #07090e;
    }

    .extra-card {
      min-height: 245px;
    }

    .extra-tag {
      display: inline-block;
      padding: 6px 9px;
      border: 1px solid rgba(255, 73, 100, 0.35);
    }

    .glossary-quiz {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 45px;
      margin-top: 70px;
    }

    .glossary-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      margin-top: 25px;
      border-top: 1px solid var(--border);
      border-left: 1px solid var(--border);
    }

    .glossary-item {
      min-height: 145px;
      padding: 22px;
      border-right: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .glossary-item dt {
      font-family: var(--display);
      font-size: 12px;
      font-weight: 700;
      text-transform: uppercase;
    }

    .glossary-item dd {
      margin-top: 10px;
      color: rgba(255, 255, 255, 0.45);
      font-size: 11px;
      line-height: 1.7;
    }

    .quiz {
      align-self: start;
      padding: 32px;
      border: 1px solid rgba(255, 73, 100, 0.25);
      background: linear-gradient(145deg, rgba(223, 29, 66, 0.1), transparent);
    }

    .quiz h3 {
      margin-top: 18px;
      font-family: var(--display);
      font-size: 25px;
      text-transform: uppercase;
    }

    .quiz > p {
      margin-top: 12px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.7;
    }

    .quiz-options {
      display: grid;
      gap: 8px;
      margin-top: 25px;
    }

    .quiz-option {
      display: flex;
      min-height: 50px;
      align-items: center;
      justify-content: space-between;
      padding-inline: 17px;
      border: 1px solid var(--border);
      background: transparent;
      color: var(--muted);
      font-family: var(--display);
      font-size: 11px;
      text-transform: uppercase;
      transition: 0.2s ease;
    }

    .quiz-option:hover,
    .quiz-option.selected {
      border-color: rgba(255, 255, 255, 0.4);
      background: rgba(255, 255, 255, 0.06);
      color: white;
    }

    .quiz-result {
      display: none;
      margin-top: 16px;
      padding: 15px;
      border-left: 2px solid var(--red);
      background: rgba(223, 29, 66, 0.08);
      color: rgba(255, 210, 216, 0.8);
      font-size: 11px;
      line-height: 1.7;
    }

    .quiz-result.correct {
      border-color: #79d8b0;
      background: rgba(62, 183, 133, 0.08);
      color: rgba(193, 255, 229, 0.8);
    }

    .timeline-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 40px;
      margin-top: 50px;
    }

    .timeline-tabs {
      border-top: 1px solid var(--border);
    }

    .timeline-button {
      display: grid;
      width: 100%;
      min-height: 76px;
      grid-template-columns: 65px 1fr 25px;
      align-items: center;
      padding-inline: 0;
      border-bottom: 1px solid var(--border);
      background: transparent;
      color: rgba(255, 255, 255, 0.38);
      text-align: left;
      transition: 0.2s ease;
    }

    .timeline-button:hover,
    .timeline-button.active {
      padding-left: 13px;
      background: linear-gradient(90deg, rgba(223, 29, 66, 0.14), transparent);
      color: white;
    }

    .timeline-button span {
      color: var(--red);
      font-family: var(--display);
      font-size: 12px;
    }

    .timeline-button strong {
      font-family: var(--display);
      font-size: 12px;
      text-transform: uppercase;
    }

    .timeline-feature {
      position: relative;
      display: flex;
      min-height: 470px;
      align-items: flex-end;
      overflow: hidden;
      padding: 45px;
      border: 1px solid var(--border);
      background:
        linear-gradient(to top, #0b0e15, transparent),
        url("https://images.unsplash.com/photo-1671393332989-fb0ea854a6ed?auto=format&fit=crop&w=1400&q=85")
        center / cover;
    }

    .timeline-year {
      color: rgba(255, 255, 255, 0.15);
      font-family: var(--display);
      font-size: clamp(4rem, 10vw, 8rem);
      font-weight: 900;
    }

    .timeline-feature h3 {
      margin-top: 8px;
      font-family: var(--display);
      font-size: clamp(1.8rem, 4vw, 3rem);
      text-transform: uppercase;
    }

    .timeline-feature p {
      max-width: 600px;
      margin-top: 15px;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    .legacy {
      border-block: 1px solid var(--border);
      background: radial-gradient(circle, rgba(45, 91, 255, 0.15), transparent 55%);
      text-align: center;
    }

    .legacy h2 {
      margin-top: 20px;
      font-family: var(--display);
      font-size: clamp(2rem, 5vw, 3.5rem);
      text-transform: uppercase;
    }

    .legacy h2 span {
      color: var(--red);
    }

    .legacy p {
      max-width: 700px;
      margin: 25px auto 0;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    footer {
      padding-block: 45px;
      background: #05070b;
    }

    .footer-content {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 30px;
    }

    .footer-logo {
      font-family: var(--display);
      font-weight: 800;
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    .footer-text {
      max-width: 700px;
      margin-top: 12px;
      color: rgba(255, 255, 255, 0.3);
      font-size: 10px;
      line-height: 1.7;
    }

    @media (max-width: 900px) {
      .navigation {
        position: absolute;
        top: 72px;
        right: 0;
        left: 0;
        display: none;
        flex-direction: column;
        align-items: stretch;
        gap: 0;
        padding: 15px 20px;
        border-bottom: 1px solid var(--border);
        background: #07090e;
      }

      .navigation.open {
        display: flex;
      }

      .navigation a {
        padding-block: 15px;
        border-bottom: 1px solid var(--border);
      }

      .menu-button {
        display: block;
      }

      .universe-grid,
      .story-grid,
      .gameplay-grid,
      .glossary-quiz,
      .timeline-grid {
        grid-template-columns: 1fr;
      }

      .character-grid,
      .supporting-grid,
      .extras-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 620px) {
      .section {
        padding-block: 85px;
      }

      .hero {
        min-height: 760px;
        background-position: 63% center;
      }

      .hero-description {
        font-size: 15px;
      }

      .section-heading {
        align-items: flex-start;
        flex-direction: column;
      }

      .text-columns,
      .character-grid,
      .supporting-grid,
      .extras-grid,
      .glossary-grid {
        grid-template-columns: 1fr;
      }

      .chapter {
        grid-template-columns: 42px 1fr;
        gap: 12px;
      }

      .character-card {
        min-height: 650px;
      }

      .rank-strip span {
        padding-block: 16px;
        font-size: 14px;
      }

      .timeline-feature {
        min-height: 420px;
        padding: 25px;
      }

      .footer-content {
        align-items: flex-start;
        flex-direction: column;
      }
    }
  </style>
</head>

<body>
  <header class="header">
    <div class="container header-content">
      <a href="#inicio" class="logo">
        <span class="logo-mark"><span>D</span></span>

        <span>
          Devil <span class="logo-red">May Cry</span>
          <small>ARQUIVO ESCOLAR</small>
        </span>
      </a>

      <nav class="navigation" id="navigation">
        <a href="#universo">Universo</a>
        <a href="#historia">História</a>
        <a href="#personagens">Personagens</a>
        <a href="#jogabilidade">Jogabilidade</a>
        <a href="#extras">Extras</a>
      </nav>

      <button class="menu-button" id="menuButton" aria-label="Abrir menu">☰</button>
    </div>
  </header>

  <main>
    <section class="hero" id="inicio">
      <div class="container hero-content">
        <p class="hero-label">Capcom · 2001 — presente</p>

        <h1>
          Devil
          <span class="outlined">May Cry</span>
        </h1>

        <p class="hero-description">
          Uma jornada pelo universo, pelos personagens e pela revolução no
          gênero de ação que transformou cada batalha em uma forma de expressão.
        </p>

        <div class="hero-buttons">
          <a href="#universo" class="button button-primary">Explorar o universo</a>
          <a href="#cronologia" class="button">Ver cronologia</a>
        </div>
      </div>
    </section>

    <section class="section" id="universo">
      <div class="container universe-grid">
        <div>
          <p class="eyebrow">01 / O UNIVERSO</p>

          <h2 class="section-title">
            Entre o mundo<br />
            humano e o<br />
            <em>demoníaco.</em>
          </h2>
        </div>

        <div>
          <p class="universe-intro">
            No centro da saga está o legado de <strong>Sparda</strong>, um
            demônio que se rebelou contra sua própria espécie para proteger a
            humanidade.
          </p>

          <div class="text-columns">
            <p class="body-text">
              Séculos depois, seus filhos gêmeos, Dante e Vergil, seguem
              caminhos opostos. Um abraça sua humanidade; o outro busca cada vez
              mais poder demoníaco.
            </p>

            <p class="body-text">
              Essa rivalidade familiar move uma narrativa sobre identidade,
              perda, escolhas e a pergunta central da série: o que realmente
              torna alguém humano?
            </p>
          </div>

          <blockquote class="quote">
            “Força sem um coração não basta. É a humanidade que dá sentido ao poder.”
          </blockquote>
        </div>
      </div>
    </section>

    <section class="section story" id="historia">
      <div class="container story-grid">
        <div>
          <p class="eyebrow">02 / A HISTÓRIA</p>

          <h2 class="section-title">
            Uma família.<br />
            Dois mundos.<br />
            <em>Um legado.</em>
          </h2>

          <p class="story-summary">
            A trama de Devil May Cry não é apenas uma guerra entre humanos e
            demônios. É uma história familiar sobre trauma, poder,
            responsabilidade e reconciliação.
          </p>
        </div>

        <div class="chapters">
          <article class="chapter">
            <span class="chapter-number">I</span>

            <div>
              <p class="chapter-era">Há 2.000 anos</p>
              <h3>A rebelião de Sparda</h3>

              <p>
                Mundus, imperador do mundo demoníaco, planejava invadir o mundo
                humano. Sparda, um de seus cavaleiros mais poderosos, despertou
                para a justiça, derrotou o exército demoníaco e selou a
                passagem entre os dois mundos.
              </p>
            </div>
          </article>

          <article class="chapter">
            <span class="chapter-number">II</span>

            <div>
              <p class="chapter-era">A tragédia da família</p>
              <h3>Dante e Vergil</h3>

              <p>
                Sparda se uniu à humana Eva e teve os gêmeos Dante e Vergil.
                Após o desaparecimento do pai, demônios atacaram a família. Eva
                morreu protegendo os filhos.
              </p>
            </div>
          </article>

          <article class="chapter">
            <span class="chapter-number">III</span>

            <div>
              <p class="chapter-era">O despertar do poder</p>
              <h3>A rivalidade dos irmãos</h3>

              <p>
                Em Devil May Cry 3, Vergil tenta abrir o portal demoníaco usando
                a torre Temen-ni-gru. Dante o enfrenta e aceita sua
                responsabilidade como filho de Sparda.
              </p>
            </div>
          </article>

          <article class="chapter">
            <span class="chapter-number">IV</span>

            <div>
              <p class="chapter-era">Uma nova geração</p>
              <h3>Nero muda o destino</h3>

              <p>
                Em Devil May Cry 5, Nero descobre ser filho de Vergil. Ao
                despertar seu verdadeiro poder, impede o duelo final entre o
                pai e Dante e rompe o ciclo de rivalidade da família.
              </p>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="section characters" id="personagens">
      <div class="container">
        <div class="section-heading">
          <div>
            <p class="eyebrow">03 / PERSONAGENS</p>
            <h2 class="section-title">Sangue de <em>Sparda.</em></h2>
          </div>

          <p>
            Três gerações, três maneiras de lutar e diferentes respostas para o
            mesmo legado.
          </p>
        </div>

        <div class="character-grid">
          <article class="character-card">
            <img
              src="https://static.wikia.nocookie.net/devilmaycry/images/c/c2/Dante_DMC5.png/revision/latest"
              alt="Dante em Devil May Cry 5"
            />

            <div class="character-content">
              <p class="character-role">O caçador lendário</p>
              <h3>Dante</h3>

              <p class="character-description">
                Filho de Sparda e Eva, Dante perdeu a mãe ainda criança. Ele
                criou a agência Devil May Cry e passou a caçar demônios,
                escondendo sua dor atrás do humor e da irreverência.
              </p>

              <div class="character-info">
                <div>
                  <small>Armas</small>
                  <strong>Rebellion e Ebony & Ivory</strong>
                </div>

                <div>
                  <small>Poder</small>
                  <strong>Sin Devil Trigger</strong>
                </div>
              </div>
            </div>
          </article>

          <article class="character-card">
            <img
              src="https://static.wikia.nocookie.net/devilmaycry/images/4/4e/Vergil_DMC5.png/revision/latest"
              alt="Vergil em Devil May Cry 5"
            />

            <div class="character-content">
              <p class="character-role">O rival implacável</p>
              <h3>Vergil</h3>

              <p class="character-description">
                Traumatizado por não conseguir se proteger quando criança,
                Vergil passou a acreditar que tudo poderia ser resolvido com
                poder. Sua busca o coloca diversas vezes contra Dante.
              </p>

              <div class="character-info">
                <div>
                  <small>Arma</small>
                  <strong>Yamato</strong>
                </div>

                <div>
                  <small>Relação</small>
                  <strong>Pai de Nero</strong>
                </div>
              </div>
            </div>
          </article>

          <article class="character-card">
            <img
              src="https://static.wikia.nocookie.net/devilmaycry/images/9/9f/Nero_DMC5.png/revision/latest"
              alt="Nero em Devil May Cry 5"
            />

            <div class="character-content">
              <p class="character-role">A nova geração</p>
              <h3>Nero</h3>

              <p class="character-description">
                Criado na cidade de Fortuna, Nero descobre aos poucos sua
                ligação com a família de Sparda. Impulsivo e humano, ele
                amadurece ao lutar para proteger as pessoas que ama.
              </p>

              <div class="character-info">
                <div>
                  <small>Armas</small>
                  <strong>Red Queen e Blue Rose</strong>
                </div>

                <div>
                  <small>Poder</small>
                  <strong>Devil Breakers</strong>
                </div>
              </div>
            </div>
          </article>
        </div>

        <h3 class="supporting-title">Outros nomes importantes</h3>

        <div class="supporting-grid">
          <article class="supporting-card">
            <small>Caçadora humana</small>
            <h4>Lady</h4>
            <p>
              Especialista em armas de fogo. Sua história prova que coragem e
              determinação podem enfrentar demônios poderosos.
            </p>
          </article>

          <article class="supporting-card">
            <small>Demônio aliada</small>
            <h4>Trish</h4>
            <p>
              Criada por Mundus com a aparência de Eva. Ela rompe com seu
              criador e passa a lutar ao lado dos humanos.
            </p>
          </article>

          <article class="supporting-card">
            <small>Metade humana</small>
            <h4>V</h4>
            <p>
              Parte humana separada de Vergil. Combate usando os familiares
              Shadow, Griffon e Nightmare.
            </p>
          </article>

          <article class="supporting-card">
            <small>Engenheira</small>
            <h4>Nico</h4>
            <p>
              Constrói os Devil Breakers de Nero e acompanha suas missões em uma
              oficina móvel.
            </p>
          </article>

          <article class="supporting-card">
            <small>O cavaleiro sombrio</small>
            <h4>Sparda</h4>
            <p>
              Pai de Dante e Vergil. Sua rebelião contra os demônios salvou a
              humanidade.
            </p>
          </article>

          <article class="supporting-card">
            <small>Imperador demoníaco</small>
            <h4>Mundus</h4>
            <p>
              Principal inimigo do primeiro jogo. Foi derrotado por Sparda e
              retorna em busca de vingança.
            </p>
          </article>
        </div>
      </div>
    </section>

    <section class="section gameplay" id="jogabilidade">
      <div class="container">
        <p class="eyebrow">04 / JOGABILIDADE</p>

        <div class="gameplay-grid">
          <div>
            <h2 class="section-title">
              Vencer não basta.<br />
              <em>É preciso estilo.</em>
            </h2>

            <p class="gameplay-description">
              O sistema de ranking avalia o desempenho em tempo real. Repetir
              golpes reduz a nota; variar ataques, desviar no momento certo e
              manter o combo faz o medidor subir.
            </p>
          </div>

          <div>
            <article class="gameplay-item">
              <span class="gameplay-number">01</span>

              <div>
                <h3>Combos</h3>
                <p>
                  Golpes terrestres e aéreos podem ser conectados de inúmeras formas.
                </p>
              </div>
            </article>

            <article class="gameplay-item">
              <span class="gameplay-number">02</span>

              <div>
                <h3>Estilo</h3>
                <p>
                  O jogo recompensa variedade, precisão e criatividade, não apenas vencer.
                </p>
              </div>
            </article>

            <article class="gameplay-item">
              <span class="gameplay-number">03</span>

              <div>
                <h3>Arsenal</h3>
                <p>
                  Espadas, armas de fogo e poderes demoníacos mudam o ritmo das batalhas.
                </p>
              </div>
            </article>
          </div>
        </div>

        <div class="rank-strip">
          <span>D</span>
          <span>C</span>
          <span>B</span>
          <span>A</span>
          <span>S</span>
          <span>SS</span>
          <span>SSS</span>
        </div>
      </div>
    </section>

    <section class="section extras" id="extras">
      <div class="container">
        <div class="section-heading">
          <div>
            <p class="eyebrow">05 / ALÉM DA CAMPANHA</p>

            <h2 class="section-title">
              Detalhes que fazem<br />
              a saga ser <em>única.</em>
            </h2>
          </div>

          <p>
            Da origem como protótipo de outro jogo às referências literárias,
            Devil May Cry construiu uma identidade que combina cultura pop,
            música e domínio técnico.
          </p>
        </div>

        <div class="extras-grid">
          <article class="extra-card">
            <span class="extra-tag">Origem</span>
            <h3>Começou como Resident Evil</h3>
            <p>
              O projeto nasceu durante o desenvolvimento de Resident Evil 4.
              Como a ação ficou distante do terror tradicional, tornou-se uma
              franquia própria.
            </p>
          </article>

          <article class="extra-card">
            <span class="extra-tag">Literatura</span>
            <h3>O nome de Dante</h3>
            <p>
              Dante e Vergil fazem referência a Dante Alighieri e Virgílio,
              figuras centrais da Divina Comédia.
            </p>
          </article>

          <article class="extra-card">
            <span class="extra-tag">Música</span>
            <h3>A trilha reage ao jogador</h3>
            <p>
              Em Devil May Cry 5, a música ganha intensidade conforme o ranking
              de estilo aumenta.
            </p>
          </article>

          <article class="extra-card">
            <span class="extra-tag">Desafio</span>
            <h3>Bloody Palace</h3>
            <p>
              O modo coloca o jogador em uma sequência de arenas com dificuldade
              crescente.
            </p>
          </article>

          <article class="extra-card">
            <span class="extra-tag">Outras mídias</span>
            <h3>Além dos videogames</h3>
            <p>
              A saga recebeu romances, mangás, séries animadas e participações
              em outros jogos.
            </p>
          </article>

          <article class="extra-card">
            <span class="extra-tag">Identidade</span>
            <h3>Cores que contam histórias</h3>
            <p>
              Vermelho representa Dante, azul representa Vergil e tons de azul e
              roxo acompanham Nero.
            </p>
          </article>
        </div>

        <div class="glossary-quiz">
          <div>
            <h3 class="supporting-title" style="margin-top: 0">
              Glossário do caçador
            </h3>

            <dl class="glossary-grid">
              <div class="glossary-item">
                <dt>Devil Trigger</dt>
                <dd>
                  Transformação que libera o poder demoníaco e aumenta força,
                  velocidade e recuperação.
                </dd>
              </div>

              <div class="glossary-item">
                <dt>Devil Arms</dt>
                <dd>
                  Armas demoníacas geralmente obtidas após derrotar seres poderosos.
                </dd>
              </div>

              <div class="glossary-item">
                <dt>Stylish Rank</dt>
                <dd>
                  Nota que cresce com variedade, risco e domínio técnico durante o combate.
                </dd>
              </div>

              <div class="glossary-item">
                <dt>Devil Breaker</dt>
                <dd>
                  Braços mecânicos criados por Nico para Nero, cada um com uma habilidade.
                </dd>
              </div>

              <div class="glossary-item">
                <dt>Jackpot</dt>
                <dd>
                  Expressão marcante usada em momentos decisivos da franquia.
                </dd>
              </div>

              <div class="glossary-item">
                <dt>Hack and slash</dt>
                <dd>
                  Gênero de ação focado em combate corpo a corpo e sequências de golpes.
                </dd>
              </div>
            </dl>
          </div>

          <aside class="quiz">
            <span class="eyebrow" style="color: var(--red-light)">
              Quiz relâmpago
            </span>

            <h3>Quem é o pai de Nero?</h3>

            <p>
              Teste se você prestou atenção à história da família de Sparda.
            </p>

            <div class="quiz-options">
              <button class="quiz-option" data-answer="Dante">
                <span>Dante</span>
                <span>+</span>
              </button>

              <button class="quiz-option" data-answer="Vergil">
                <span>Vergil</span>
                <span>+</span>
              </button>

              <button class="quiz-option" data-answer="Sparda">
                <span>Sparda</span>
                <span>+</span>
              </button>
            </div>

            <div class="quiz-result" id="quizResult"></div>
          </aside>
        </div>
      </div>
    </section>

    <section class="section" id="cronologia">
      <div class="container">
        <p class="eyebrow">06 / LINHA DO TEMPO</p>
        <h2 class="section-title">Duas décadas de <em>ação.</em></h2>

        <div class="timeline-grid">
          <div class="timeline-tabs">
            <button
              class="timeline-button"
              data-year="2001"
              data-title="Devil May Cry"
              data-text="Dante chega à Ilha Mallet e apresenta ao mundo um combate rápido, técnico e cheio de estilo."
            >
              <span>2001</span>
              <strong>Devil May Cry</strong>
              <b>→</b>
            </button>

            <button
              class="timeline-button"
              data-year="2003"
              data-title="Devil May Cry 2"
              data-text="A sequência amplia os cenários e introduz Lucia como personagem jogável."
            >
              <span>2003</span>
              <strong>Devil May Cry 2</strong>
              <b>→</b>
            </button>

            <button
              class="timeline-button"
              data-year="2005"
              data-title="Devil May Cry 3"
              data-text="Um prelúdio que explora a rivalidade entre Dante e Vergil e consolida os estilos de combate."
            >
              <span>2005</span>
              <strong>Devil May Cry 3</strong>
              <b>→</b>
            </button>

            <button
              class="timeline-button"
              data-year="2008"
              data-title="Devil May Cry 4"
              data-text="Nero entra em cena com o Devil Bringer, enquanto Dante retorna em uma campanha compartilhada."
            >
              <span>2008</span>
              <strong>Devil May Cry 4</strong>
              <b>→</b>
            </button>

            <button
              class="timeline-button active"
              data-year="2019"
              data-title="Devil May Cry 5"
              data-text="Dante, Nero e V unem forças em Red Grave City no capítulo mais moderno da saga principal."
            >
              <span>2019</span>
              <strong>Devil May Cry 5</strong>
              <b>→</b>
            </button>
          </div>

          <article class="timeline-feature">
            <div>
              <span class="timeline-year" id="timelineYear">2019</span>
              <h3 id="timelineTitle">Devil May Cry 5</h3>

              <p id="timelineText">
                Dante, Nero e V unem forças em Red Grave City no capítulo mais
                moderno da saga principal.
              </p>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="section legacy">
      <div class="container">
        <p class="eyebrow">Legado cultural</p>

        <h2>
          Um jogo que transformou<br />
          combate em <span>performance.</span>
        </h2>

        <p>
          Devil May Cry ajudou a definir o hack and slash moderno. Sua influência
          aparece em dezenas de jogos que valorizam velocidade, domínio técnico
          e liberdade criativa.
        </p>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-content">
      <div>
        <p class="footer-logo">
          Devil <span class="logo-red">May Cry</span>
        </p>

        <p class="footer-text">
          Projeto escolar de caráter informativo e não oficial. Devil May Cry,
          suas artes e personagens pertencem à Capcom. Imagens arquitetônicas
          utilizadas por meio do Unsplash.
        </p>
      </div>

      <a href="#inicio" class="button">Voltar ao topo</a>
    </div>
  </footer>

  <script>
    const menuButton = document.querySelector("#menuButton");
    const navigation = document.querySelector("#navigation");

    menuButton.addEventListener("click", () => {
      navigation.classList.toggle("open");
      menuButton.textContent = navigation.classList.contains("open") ? "×" : "☰";
    });

    navigation.querySelectorAll("a").forEach((link) => {
      link.addEventListener("click", () => {
        navigation.classList.remove("open");
        menuButton.textContent = "☰";
      });
    });

    const quizOptions = document.querySelectorAll(".quiz-option");
    const quizResult = document.querySelector("#quizResult");

    quizOptions.forEach((button) => {
      button.addEventListener("click", () => {
        quizOptions.forEach((option) => {
          option.classList.remove("selected");
          option.querySelector("span:last-child").textContent = "+";
        });

        button.classList.add("selected");
        button.querySelector("span:last-child").textContent = "—";

        const selectedAnswer = button.dataset.answer;
        const isCorrect = selectedAnswer === "Vergil";

        quizResult.style.display = "block";
        quizResult.classList.toggle("correct", isCorrect);

        if (isCorrect) {
          quizResult.innerHTML =
            "<strong>Resposta certa.</strong> Vergil é o pai de Nero. A relação é revelada definitivamente em Devil May Cry 5.";
        } else {
          quizResult.innerHTML =
            "<strong>Quase.</strong> O pai de Nero é Vergil, irmão gêmeo de Dante.";
        }
      });
    });

    const timelineButtons = document.querySelectorAll(".timeline-button");
    const timelineYear = document.querySelector("#timelineYear");
    const timelineTitle = document.querySelector("#timelineTitle");
    const timelineText = document.querySelector("#timelineText");

    timelineButtons.forEach((button) => {
      button.addEventListener("click", () => {
        timelineButtons.forEach((item) => item.classList.remove("active"));
        button.classList.add("active");

        timelineYear.textContent = button.dataset.year;
        timelineTitle.textContent = button.dataset.title;
        timelineText.textContent = button.dataset.text;
      });
    });
  </script>
</body>
</html>
```Abaixo está uma versão completa em **um único arquivo**, sem dividir. Salve como `index.html` e abra no navegador.

```html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Devil May Cry — Trabalho Escolar</title>

  <meta
    name="description"
    content="Site escolar informativo sobre Devil May Cry, sua história, personagens, jogabilidade e legado."
  />

  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />

  <link
    href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;600;700;800;900&family=Inter:wght@300;400;500;600;700&display=swap"
    rel="stylesheet"
  />

  <style>
    :root {
      --background: #06080d;
      --surface: #0a0d14;
      --surface-light: #10141e;
      --red: #ff314f;
      --red-light: #ff7187;
      --blue: #5185ff;
      --white: #ffffff;
      --muted: rgba(255, 255, 255, 0.55);
      --border: rgba(255, 255, 255, 0.12);
      --display: "Cinzel", serif;
      --sans: "Inter", sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      background: var(--background);
    }

    body {
      overflow-x: hidden;
      background: var(--background);
      color: var(--white);
      font-family: var(--sans);
    }

    button,
    a {
      color: inherit;
      font: inherit;
    }

    button {
      border: 0;
      cursor: pointer;
    }

    a {
      text-decoration: none;
    }

    img {
      display: block;
      max-width: 100%;
    }

    ::selection {
      color: white;
      background: var(--red);
    }

    .container {
      width: min(1180px, calc(100% - 40px));
      margin-inline: auto;
    }

    .section {
      padding-block: 120px;
    }

    .eyebrow {
      color: rgba(255, 255, 255, 0.4);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.25em;
      text-transform: uppercase;
    }

    .section-title {
      margin-top: 18px;
      font-family: var(--display);
      font-size: clamp(2.3rem, 6vw, 4.8rem);
      line-height: 1;
      letter-spacing: -0.04em;
      text-transform: uppercase;
    }

    .section-title em {
      color: var(--red);
      font-weight: 500;
    }

    .button {
      display: inline-flex;
      min-height: 50px;
      align-items: center;
      justify-content: center;
      padding-inline: 22px;
      border: 1px solid var(--border);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      transition: 0.25s ease;
    }

    .button-primary {
      border-color: var(--red);
      background: #df1d42;
      box-shadow: 0 14px 40px rgba(223, 29, 66, 0.25);
    }

    .button:hover {
      border-color: rgba(255, 255, 255, 0.5);
      color: white;
      transform: translateY(-2px);
    }

    .header {
      position: fixed;
      z-index: 100;
      top: 0;
      right: 0;
      left: 0;
      border-bottom: 1px solid var(--border);
      background: rgba(7, 9, 14, 0.84);
      backdrop-filter: blur(18px);
    }

    .header-content {
      display: flex;
      min-height: 72px;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 13px;
      font-family: var(--display);
      font-size: 14px;
      font-weight: 800;
      letter-spacing: 0.14em;
      text-transform: uppercase;
    }

    .logo-mark {
      display: grid;
      width: 37px;
      height: 37px;
      place-items: center;
      border: 1px solid var(--red);
      color: var(--red-light);
      font-size: 19px;
      transform: rotate(45deg);
    }

    .logo-mark span {
      transform: rotate(-45deg);
    }

    .logo-red {
      color: var(--red);
    }

    .logo small {
      display: block;
      margin-top: 4px;
      color: rgba(255, 255, 255, 0.35);
      font-family: var(--sans);
      font-size: 7px;
      letter-spacing: 0.3em;
    }

    .navigation {
      display: flex;
      align-items: center;
      gap: 28px;
    }

    .navigation a {
      color: rgba(255, 255, 255, 0.6);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.13em;
      text-transform: uppercase;
      transition: color 0.2s ease;
    }

    .navigation a:hover {
      color: white;
    }

    .menu-button {
      display: none;
      width: 42px;
      height: 42px;
      border: 1px solid var(--border);
      background: transparent;
      color: white;
      font-size: 22px;
    }

    .hero {
      position: relative;
      display: flex;
      min-height: 100vh;
      align-items: flex-end;
      padding-block: 160px 90px;
      background:
        linear-gradient(90deg, rgba(5, 7, 12, 0.97), rgba(5, 7, 12, 0.74) 48%, rgba(5, 7, 12, 0.2)),
        linear-gradient(0deg, #06080d, transparent 38%),
        url("https://images.unsplash.com/photo-1671393332989-fb0ea854a6ed?auto=format&fit=crop&w=2000&q=90")
        center / cover;
    }

    .hero::before {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(255, 255, 255, 0.07) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.07) 1px, transparent 1px);
      background-size: 80px 80px;
      content: "";
      mask-image: linear-gradient(to right, black, transparent 65%);
    }

    .hero-content {
      position: relative;
      z-index: 2;
    }

    .hero-label {
      display: flex;
      align-items: center;
      gap: 12px;
      color: var(--red-light);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.26em;
      text-transform: uppercase;
    }

    .hero-label::before {
      width: 44px;
      height: 1px;
      background: var(--red);
      content: "";
    }

    .hero h1 {
      margin-top: 25px;
      font-family: var(--display);
      font-size: clamp(4rem, 11vw, 9rem);
      font-weight: 900;
      line-height: 0.78;
      letter-spacing: -0.06em;
      text-transform: uppercase;
    }

    .outlined {
      display: block;
      color: transparent;
      -webkit-text-stroke: 1px rgba(255, 255, 255, 0.75);
    }

    .hero-description {
      max-width: 690px;
      margin-top: 35px;
      padding-left: 20px;
      border-left: 1px solid var(--red);
      color: rgba(255, 255, 255, 0.65);
      font-size: 18px;
      line-height: 1.7;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 34px;
    }

    .universe-grid {
      display: grid;
      grid-template-columns: 0.75fr 1.25fr;
      gap: 80px;
    }

    .universe-intro {
      color: rgba(255, 255, 255, 0.78);
      font-size: clamp(1.5rem, 3vw, 2rem);
      font-weight: 300;
      line-height: 1.65;
    }

    .universe-intro strong {
      color: white;
      font-weight: 500;
    }

    .text-columns {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 35px;
      margin-top: 40px;
      padding-top: 35px;
      border-top: 1px solid var(--border);
    }

    .body-text {
      color: rgba(255, 255, 255, 0.48);
      font-size: 14px;
      line-height: 1.8;
    }

    .quote {
      margin-top: 45px;
      padding-block: 28px;
      border-block: 1px solid var(--border);
      color: #93b9ff;
      font-family: var(--display);
      font-size: clamp(1.3rem, 3vw, 2rem);
      font-style: italic;
      line-height: 1.5;
    }

    .story {
      border-block: 1px solid var(--border);
      background:
        linear-gradient(90deg, rgba(6, 8, 13, 0.98), rgba(6, 8, 13, 0.87)),
        url("https://images.unsplash.com/photo-1719042948053-eafa289f90fb?auto=format&fit=crop&w=1800&q=80")
        center / cover;
    }

    .story-grid {
      display: grid;
      grid-template-columns: 0.7fr 1.3fr;
      gap: 70px;
    }

    .story-summary {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.8;
    }

    .chapters {
      border-top: 1px solid var(--border);
    }

    .chapter {
      display: grid;
      grid-template-columns: 70px 1fr;
      gap: 24px;
      padding-block: 34px;
      border-bottom: 1px solid var(--border);
    }

    .chapter-number {
      color: transparent;
      font-family: var(--display);
      font-size: 35px;
      font-weight: 800;
      -webkit-text-stroke: 1px rgba(132, 169, 255, 0.6);
    }

    .chapter-era {
      color: var(--red-light);
      font-size: 9px;
      font-weight: 700;
      letter-spacing: 0.2em;
      text-transform: uppercase;
    }

    .chapter h3 {
      margin-top: 8px;
      font-family: var(--display);
      font-size: 27px;
      text-transform: uppercase;
    }

    .chapter p:last-child {
      margin-top: 14px;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    .characters {
      background: var(--surface);
    }

    .section-heading {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 30px;
      margin-bottom: 55px;
    }

    .section-heading > p {
      max-width: 400px;
      color: var(--muted);
      font-size: 14px;
      line-height: 1.7;
    }

    .character-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
    }

    .character-card {
      position: relative;
      min-height: 680px;
      overflow: hidden;
      padding: 25px;
      border: 1px solid var(--border);
      background: linear-gradient(145deg, rgba(255, 255, 255, 0.05), transparent);
      transition: 0.35s ease;
    }

    .character-card:hover {
      border-color: rgba(255, 255, 255, 0.3);
      transform: translateY(-8px);
    }

    .character-card img {
      position: absolute;
      top: 8px;
      left: 50%;
      width: auto;
      height: 72%;
      max-width: none;
      object-fit: contain;
      transform: translateX(-50%);
      filter: saturate(0.8);
    }

    .character-card::after {
      position: absolute;
      z-index: 1;
      inset: 0;
      background: linear-gradient(to bottom, transparent 25%, rgba(9, 12, 19, 0.2) 46%, #090c13 70%);
      content: "";
    }

    .character-content {
      position: relative;
      z-index: 2;
      display: flex;
      min-height: 625px;
      flex-direction: column;
      justify-content: flex-end;
    }

    .character-role {
      margin-bottom: 8px;
      color: rgba(255, 255, 255, 0.5);
      font-size: 9px;
      font-weight: 700;
      letter-spacing: 0.18em;
      text-transform: uppercase;
    }

    .character-card h3 {
      font-family: var(--display);
      font-size: 43px;
      text-transform: uppercase;
    }

    .character-description {
      margin-top: 18px;
      color: rgba(255, 255, 255, 0.58);
      font-size: 13px;
      line-height: 1.75;
    }

    .character-info {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 18px;
      margin-top: 24px;
      padding-top: 18px;
      border-top: 1px solid var(--border);
    }

    .character-info small {
      display: block;
      color: rgba(255, 255, 255, 0.34);
      font-size: 8px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .character-info strong {
      display: block;
      margin-top: 8px;
      font-size: 10px;
      line-height: 1.5;
      text-transform: uppercase;
    }

    .supporting-title {
      display: flex;
      align-items: center;
      gap: 20px;
      margin-top: 90px;
      margin-bottom: 30px;
      font-family: var(--display);
      font-size: 23px;
      text-transform: uppercase;
    }

    .supporting-title::after {
      height: 1px;
      flex: 1;
      background: var(--border);
      content: "";
    }

    .supporting-grid,
    .extras-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      border-top: 1px solid var(--border);
      border-left: 1px solid var(--border);
    }

    .supporting-card,
    .extra-card {
      min-height: 220px;
      padding: 27px;
      border-right: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      background: rgba(255, 255, 255, 0.015);
    }

    .supporting-card small,
    .extra-tag {
      color: var(--red-light);
      font-size: 8px;
      font-weight: 700;
      letter-spacing: 0.16em;
      text-transform: uppercase;
    }

    .supporting-card h4,
    .extra-card h3 {
      margin-top: 10px;
      font-family: var(--display);
      font-size: 21px;
      text-transform: uppercase;
    }

    .supporting-card p,
    .extra-card p {
      margin-top: 15px;
      color: rgba(255, 255, 255, 0.46);
      font-size: 12px;
      line-height: 1.75;
    }

    .gameplay {
      position: relative;
      background:
        linear-gradient(110deg, #07090f 10%, rgba(7, 9, 15, 0.94) 50%, rgba(7, 9, 15, 0.55)),
        url("https://images.unsplash.com/photo-1511200903586-f88075762629?auto=format&fit=crop&w=1800&q=85")
        center / cover;
    }

    .gameplay-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 70px;
      margin-top: 25px;
    }

    .gameplay-description {
      max-width: 570px;
      margin-top: 28px;
      color: var(--muted);
      font-size: 15px;
      line-height: 1.8;
    }

    .gameplay-item {
      display: grid;
      grid-template-columns: 45px 1fr;
      gap: 15px;
      margin-bottom: 12px;
      padding: 20px;
      border: 1px solid var(--border);
      background: rgba(8, 10, 16, 0.68);
      backdrop-filter: blur(12px);
    }

    .gameplay-number {
      color: var(--red);
      font-family: var(--display);
    }

    .gameplay-item h3 {
      font-family: var(--display);
      font-size: 20px;
      text-transform: uppercase;
    }

    .gameplay-item p {
      margin-top: 6px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.7;
    }

    .rank-strip {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      margin-top: 60px;
      border-block: 1px solid var(--border);
    }

    .rank-strip span {
      padding-block: 22px;
      border-right: 1px solid var(--border);
      color: rgba(255, 255, 255, 0.16);
      font-family: var(--display);
      font-size: clamp(1rem, 3vw, 2.3rem);
      font-weight: 800;
      text-align: center;
    }

    .rank-strip span:nth-last-child(-n + 3) {
      color: var(--red);
    }

    .extras {
      background:
        radial-gradient(circle at 80% 20%, rgba(62, 100, 255, 0.12), transparent 30%),
        #07090e;
    }

    .extra-card {
      min-height: 245px;
    }

    .extra-tag {
      display: inline-block;
      padding: 6px 9px;
      border: 1px solid rgba(255, 73, 100, 0.35);
    }

    .glossary-quiz {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 45px;
      margin-top: 70px;
    }

    .glossary-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      margin-top: 25px;
      border-top: 1px solid var(--border);
      border-left: 1px solid var(--border);
    }

    .glossary-item {
      min-height: 145px;
      padding: 22px;
      border-right: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .glossary-item dt {
      font-family: var(--display);
      font-size: 12px;
      font-weight: 700;
      text-transform: uppercase;
    }

    .glossary-item dd {
      margin-top: 10px;
      color: rgba(255, 255, 255, 0.45);
      font-size: 11px;
      line-height: 1.7;
    }

    .quiz {
      align-self: start;
      padding: 32px;
      border: 1px solid rgba(255, 73, 100, 0.25);
      background: linear-gradient(145deg, rgba(223, 29, 66, 0.1), transparent);
    }

    .quiz h3 {
      margin-top: 18px;
      font-family: var(--display);
      font-size: 25px;
      text-transform: uppercase;
    }

    .quiz > p {
      margin-top: 12px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.7;
    }

    .quiz-options {
      display: grid;
      gap: 8px;
      margin-top: 25px;
    }

    .quiz-option {
      display: flex;
      min-height: 50px;
      align-items: center;
      justify-content: space-between;
      padding-inline: 17px;
      border: 1px solid var(--border);
      background: transparent;
      color: var(--muted);
      font-family: var(--display);
      font-size: 11px;
      text-transform: uppercase;
      transition: 0.2s ease;
    }

    .quiz-option:hover,
    .quiz-option.selected {
      border-color: rgba(255, 255, 255, 0.4);
      background: rgba(255, 255, 255, 0.06);
      color: white;
    }

    .quiz-result {
      display: none;
      margin-top: 16px;
      padding: 15px;
      border-left: 2px solid var(--red);
      background: rgba(223, 29, 66, 0.08);
      color: rgba(255, 210, 216, 0.8);
      font-size: 11px;
      line-height: 1.7;
    }

    .quiz-result.correct {
      border-color: #79d8b0;
      background: rgba(62, 183, 133, 0.08);
      color: rgba(193, 255, 229, 0.8);
    }

    .timeline-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 40px;
      margin-top: 50px;
    }

    .timeline-tabs {
      border-top: 1px solid var(--border);
    }

    .timeline-button {
      display: grid;
      width: 100%;
      min-height: 76px;
      grid-template-columns: 65px 1fr 25px;
      align-items: center;
      padding-inline: 0;
      border-bottom: 1px solid var(--border);
      background: transparent;
      color: rgba(255, 255, 255, 0.38);
      text-align: left;
      transition: 0.2s ease;
    }

    .timeline-button:hover,
    .timeline-button.active {
      padding-left: 13px;
      background: linear-gradient(90deg, rgba(223, 29, 66, 0.14), transparent);
      color: white;
    }

    .timeline-button span {
      color: var(--red);
      font-family: var(--display);
      font-size: 12px;
    }

    .timeline-button strong {
      font-family: var(--display);
      font-size: 12px;
      text-transform: uppercase;
    }

    .timeline-feature {
      position: relative;
      display: flex;
      min-height: 470px;
      align-items: flex-end;
      overflow: hidden;
      padding: 45px;
      border: 1px solid var(--border);
      background:
        linear-gradient(to top, #0b0e15, transparent),
        url("https://images.unsplash.com/photo-1671393332989-fb0ea854a6ed?auto=format&fit=crop&w=1400&q=85")
        center / cover;
    }

    .timeline-year {
      color: rgba(255, 255, 255, 0.15);
      font-family: var(--display);
      font-size: clamp(4rem, 10vw, 8rem);
      font-weight: 900;
    }

    .timeline-feature h3 {
      margin-top: 8px;
      font-family: var(--display);
      font-size: clamp(1.8rem, 4vw, 3rem);
      text-transform: uppercase;
    }

    .timeline-feature p {
      max-width: 600px;
      margin-top: 15px;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    .legacy {
      border-block: 1px solid var(--border);
      background: radial-gradient(circle, rgba(45, 91, 255, 0.15), transparent 55%);
      text-align: center;
    }

    .legacy h2 {
      margin-top: 20px;
      font-family: var(--display);
      font-size: clamp(2rem, 5vw, 3.5rem);
      text-transform: uppercase;
    }

    .legacy h2 span {
      color: var(--red);
    }

    .legacy p {
      max-width: 700px;
      margin: 25px auto 0;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    footer {
      padding-block: 45px;
      background: #05070b;
    }

    .footer-content {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 30px;
    }

    .footer-logo {
      font-family: var(--display);
      font-weight: 800;
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

  
