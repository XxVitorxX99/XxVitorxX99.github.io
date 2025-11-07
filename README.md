# XxVitorxX99.github.io<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sabor Caseiro - Sabores do Amor</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg1: #b82e2e; /* vermelho elegante */
      --bg2: #f2d7b6; /* bege suave */
      --card: #fff8f0;
      --muted: #6b6b6b;
      --accent: #c0392b;
      --glass: rgba(255, 255, 255, 0.1);
      --shadow: 0 10px 40px rgba(0, 0, 0, 0.25);
      --transition: all 0.3s ease;
    }
    * {
      box-sizing: border-box;
    }
    html, body {
      height: 100%;
      margin: 0;
      font-family: Inter, system-ui, Arial;
      background: linear-gradient(135deg, var(--bg1), var(--bg2));
      color: #111;
      display: flex;
      align-items: flex-start;
      justify-content: center;
      padding: 1rem;
      min-height: 100vh;
      background-attachment: fixed;
    }
    .menu-wrap {
      width: 100%;
      max-width: 1200px;
      background: var(--card);
      border-radius: 18px;
      box-shadow: var(--shadow);
      overflow: hidden;
      position: relative;
      padding: 32px;
      margin-top: 20px;
    }
    header {
      display: flex;
      gap: 20px;
      align-items: center;
      justify-content: center;
      margin-bottom: 24px;
      text-align: center;
      flex-wrap: wrap;
    }
    .logo {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 30%, #ffe6e6, #ff9999 30%, transparent 31%), linear-gradient(180deg, #ff5f5f, #c0392b);
      display: inline-flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 6px 18px rgba(192, 57, 43, 0.4);
      font-family: Playfair Display, serif;
      color: white;
      font-weight: 700;
      font-size: 26px;
    }
    h1 {
      font-family: Playfair Display, serif;
      margin: 0;
      font-size: clamp(28px, 5vw, 34px);
      color: #8b0000;
    }
    p.lead {
      margin: 6px 0 0 0;
      color: var(--muted);
      font-size: 15px;
    }
    .grid {
      display: grid;
      grid-template-columns: 1fr 360px;
      gap: 20px;
    }
    .card {
      padding: 18px;
      border-radius: 12px;
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.95));
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
      transition: var(--transition);
    }
    .section-title {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 10px;
    }
    .section-title h2 {
      margin: 0;
      font-family: Playfair Display, serif;
      color: #a10e0e;
      font-size: 22px;
    }
    .dish {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      padding: 10px 6px;
      border-radius: 8px;
      transition: var(--transition);
      cursor: pointer;
      role: button;
      tab-index:0;
    }
    .dish:hover, .dish:focus {
      background-color: rgba(184, 46, 46, 0.05);
      transform: translateY(-2px);
    }
    .dish + .dish {
      margin-top: 6px;
    }
    .dish .meta {
      max-width: 70%;
    }
    .dish .meta h3 {
      margin: 0;
      font-size: 17px;
      font-weight: 600;
      font-family: Playfair Display, serif;
      color: #8b0000;
    }
    .dish .meta p {
      margin: 6px 0 0 0;
      color: var(--muted);
      font-size: 13px;
    }
    .dish .tag {
      font-size: 13px;
      color: var(--accent);
      font-weight: 700;
      text-align: right;
      min-width: 80px;
    }
    aside.card {
      height: fit-content;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .aside-title {
      margin: 0;
      font-family: Playfair Display, serif;
      color: #8b0000;
    }
    .drink {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 12px;
      border-radius: 10px;
      background: var(--glass);
      border: 1px solid rgba(0, 0, 0, 0.05);
    }
    .drink h4 {
      margin: 0;
      font-size: 15px;
    }
    .romantic-quote {
      padding: 12px;
      border-radius: 10px;
      background: linear-gradient(135deg, rgba(192, 57, 43, 0.06), rgba(242, 215, 182, 0.08));
      font-style: italic;
      text-align: center;
      color: var(--muted);
      font-size: 14px;
      font-family: Playfair Display, serif;
    }
    .flowers {
      position: absolute;
      inset: 0;
      pointer-events: none;
      background: url('https://cdn.pixabay.com/photo/2017/09/05/17/20/flowers-2712308_1280.png') center top / cover no-repeat;
      opacity: 0.1;
      z-index: 0;
    }
    /* Modal Styles */
    .modal {
      display: none;
      position: fixed;
      z-index: 1000;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.7);
      justify-content: center;
      align-items: center;
      animation: fadeIn 0.3s ease;
    }
    .modal-content {
      background: var(--card);
      border-radius: 12px;
      padding: 20px;
      max-width: 500px;
      width: 90%;
      box-shadow: var(--shadow);
      text-align: center;
      position: relative;
    }
    .modal img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 15px;
    }
    .modal h3 {
      color: #8b0000;
      font-family: Playfair Display, serif;
    }
    .modal p {
      color: var(--muted);
      margin: 10px 0;
    }
    .modal .price {
      font-weight: 700;
      color: var(--accent);
      font-size: 18px;
    }
    .close {
      position: absolute;
      top: 10px;
      right: 15px;
      font-size: 24px;
      cursor: pointer;
      color: var(--muted);
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @media (max-width: 880px) {
      .grid {
        grid-template-columns: 1fr;
      }
      aside.card {
        order: 2;
      }
    }
    @media (max-width: 600px) {
      .menu-wrap {
        padding: 16px;
      }
      .modal-content {
        padding: 15px;
      }
    }
    @media print {
      body {
        background: white;
        padding: 0;
      }
      .menu-wrap {
        box-shadow: none;
        border-radius: 0;
      }
      .flowers, .modal {
        display: none;
      }
      .section {
        page-break-inside: avoid;
      }
    }
  </style>
</head>
<body>
  <div class="menu-wrap">
    <div class="flowers" aria-hidden="true"></div>
    <header>
      <div class="logo">❤</div>
      <div>
        <h1>Sabor Caseiro</h1>
        <p class="lead">Sabores do Amor — Menu especial para o Dia dos Namorados.</p>
      </div>
    </header>

    <div class="grid">
      <main class="card" id="menu-main">
        <section class="section">
          <div class="section-title">
            <h2>Entrada</h2>
          </div>
          <div class="dish" data-modal="tartar-salmão">
            <div class="meta">
              <h3>Tartar de Salmão com Avocado</h3>
              <p>Salmão fresco cortado em cubos, misturado com avocado cremoso e ervas frescas, um começo leve e apaixonado para a noite.</p>
            </div>
            <div class="tag">R$ 20,00</div>
          </div>
          <div class="dish" data-modal="coracoes-brie">
            <div class="meta">
              <h3>Corações de Queijo Brie</h3>
              <p>Mini corações de massa folhada recheados com brie cremoso e geleia de frutas vermelhas, um toque doce e apaixonado.</p>
            </div>
            <div class="tag">R$ 22,00</div>
          </div>
          <div class="dish" data-modal="salada-folhas">
            <div class="meta">
              <h3>Salada de Folhas com Nozes Caramelizadas</h3>
              <p>Mistura de folhas verdes frescas, nozes caramelizadas e vinagrete de frutas cítricas, leve e romântica para iniciar a noite.</p>
            </div>
            <div class="tag">R$ 16,00</div>
          </div>
        </section>

        <section class="section" style="margin-top: 14px">
          <div class="section-title">
            <h2>Prato Principal</h2>
          </div>
          <div class="dish" data-modal="risoto-paixao">
            <div class="meta">
              <h3>Risoto Paixão ao Funghi com Filé Mignon</h3>
              <p>Risoto cremoso com cogumelos selvagens, finalizado com medalhão de filé mignon ao molho de vinho tinto, uma explosão de sabores apaixonados.</p>
            </div>
            <div class="tag">R$ 45,00</div>
          </div>
          <div class="dish" data-modal="salmao-amor">
            <div class="meta">
              <h3>Salmão do Amor em Crosta de Ervas</h3>
              <p>Salmão grelhado envolto em crosta de ervas frescas, acompanhado de purê de batata-doce e molho de maracujá, perfeito para dois.</p>
            </div>
            <div class="tag">R$ 48,00</div>
          </div>
          <div class="dish" data-modal="medalhao-carne">
            <div class="meta">
              <h3>Medalhão de Carne com Redução de Balsâmico</h3>
              <p>Medalhão suculento de carne bovina com redução de balsâmico e legumes assados, um clássico romântico para celebrar o amor.</p>
            </div>
            <div class="tag">R$ 50,00</div>
          </div>
        </section>

        <section class="section" style="margin-top: 14px">
          <div class="section-title">
            <h2>Acompanhamentos</h2>
          </div>
          <div class="dish" data-modal="arroz-branco">
            <div class="meta">
              <h3>Arroz Branco ou Integral</h3>
              <p>Arroz leve e perfumado, ideal para acompanhar os pratos principais com elegância.</p>
            </div>
            <div class="tag">R$ 8,00</div>
          </div>
          <div class="dish" data-modal="salada-legumes">
            <div class="meta">
              <h3>Salada de Legumes Grelhados</h3>
              <p>Mistura de berinjela, abobrinha e pimentão grelhados, temperados com ervas frescas.</p>
            </div>
            <div class="tag">R$ 12,00</div>
          </div>
        </section>

        <section class="section" style="margin-top: 14px">
          <div class="section-title">
            <h2>Sobremesa</h2>
          </div>
          <div class="dish" data-modal="fondue-apaixonados">
            <div class="meta">
              <h3>Fondue dos Apaixonados</h3>
              <p>Chocolate meio amargo derretido com frutas frescas, morangos e marshmallows, perfeito para compartilhar momentos doces.</p>
            </div>
            <div class="tag">R$ 25,00</div>
          </div>
          <div class="dish" data-modal="coracao-mousse">
            <div class="meta">
              <h3>Coração de Mousse de Framboesa</h3>
              <p>Mousse leve de framboesa em formato de coração, com calda de frutas vermelhas e um toque de amor.</p>
            </div>
            <div class="tag">R$ 20,00</div>
          </div>
          <div class="dish" data-modal="torta-chocolate">
            <div class="meta">
              <h3>Torta de Chocolate com Frutas Vermelhas</h3>
              <p>Torta decadente de chocolate amargo, decorada com frutas vermelhas frescas, um final romântico e irresistível.</p>
            </div>
            <div class="tag">R$ 22,00</div>
          </div>
        </section>
      </main>

      <aside class="card">
        <div>
          <h3 class="aside-title">Bebidas Especiais</h3>
        </div>
        <div class="drink">
          <div>
            <h4>Drink “Romeu e Julieta”</h4>
            <p style="margin: 4px 0 0 0; color: var(--muted); font-size: 13px">Morango + espumante rosé + limão siciliano. (R$ 15,00)</p>
          </div>
        </div>
        <div class="drink">
          <div>
            <h4>Vinho Rosé Especial</h4>
            <p style="margin: 4px 0 0 0; color: var(--muted); font-size: 13px">Vinho rosé leve e frutado, ideal para acompanhar momentos românticos. (R$ 18,00)</p>
          </div>
        </div>
        <div class="romantic-quote">
          Em cada prato, um pedaço do nosso amor. Bom
