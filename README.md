<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Corujão dos Bruxos | Blog de Jogos</title>
  
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Montserrat:wght@300;400;600;700&family=Yellowtail&display=swap" rel="stylesheet">
  
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    /* ==========================================================================
       Design System & Variáveis CSS (Dark Gourmet)
       ========================================================================== */
    :root {
      --bg-principal: #0A0A0A;
      --bg-card: #141414;
      --bg-card-hover: #1E1E1E;
      --cor-primaria: #E31B23;
      --cor-destaque: #FFD700;
      --texto-branco: #FFFFFF;
      --texto-cinza: #A0A0A0;
      --fonte-titulo: 'Bebas Neue', cursive;
      --fonte-corpo: 'Montserrat', sans-serif;
      --fonte-cursiva: 'Yellowtail', cursive;
      --transicao-padrao: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-principal);
      color: var(--texto-branco);
      font-family: var(--fonte-corpo);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button {
      cursor: pointer;
      border: none;
      outline: none;
      font-family: var(--fonte-corpo);
    }

    /* ==========================================================================
       Utilitários de Layout & Animações
       ========================================================================== */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    .btn {
      display: inline-block;
      padding: 12px 28px;
      border-radius: 4px;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1px;
      transition: var(--transicao-padrao);
    }

    .btn-primario {
      background-color: var(--cor-primaria);
      color: var(--texto-branco);
    }

    .btn-primario:hover {
      background-color: #b81219;
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(227, 27, 35, 0.4);
    }

    .btn-destaque {
      background-color: var(--cor-destaque);
      color: #000;
    }

    .btn-destaque:hover {
      background-color: #e6c200;
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
    }

    .cursivo {
      font-family: var(--fonte-cursiva);
      color: var(--cor-destaque);
      font-size: 2rem;
      text-transform: none;
    }

    /* SPA Views & Transitions */
    .spa-view {
      display: none;
      opacity: 0;
      transform: translateY(10px);
      transition: opacity 0.4s ease, transform 0.4s ease;
      min-height: calc(100vh - 80px);
      padding-top: 100px;
      padding-bottom: 60px;
    }

    .spa-view.active {
      display: block;
      opacity: 1;
      transform: translateY(0);
    }

    /* ==========================================================================
       Header / Navegação
       ========================================================================== */
    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;
      background: rgba(10, 10, 10, 0.85);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      height: 80px;
      display: flex;
      align-items: center;
    }

    .nav-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
    }

    .logo {
      font-family: var(--fonte-titulo);
      font-size: 2.2rem;
      letter-spacing: 2px;
      color: var(--texto-branco);
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo span {
      color: var(--cor-primaria);
    }

    .nav-menu {
      display: flex;
      list-style: none;
      gap: 30px;
    }

    .nav-link {
      font-size: 0.95rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: var(--texto-cinza);
      transition: var(--transicao-padrao);
      cursor: pointer;
    }

    .nav-link:hover, .nav-link.active {
      color: var(--cor-destaque);
    }

    /* ==========================================================================
       Seção: Home
       ========================================================================== */
    #home {
      padding-top: 80px;
    }

    .hero {
      height: 90vh;
      background: linear-gradient(rgba(10, 10, 10, 0.7), rgba(10, 10, 10, 0.9)), 
                  url('https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      position: relative;
    }

    .hero-content {
      max-width: 800px;
    }

    .hero-content h1 {
      font-family: var(--fonte-titulo);
      font-size: 5rem;
      line-height: 1;
      letter-spacing: 3px;
      margin-bottom: 20px;
      text-transform: uppercase;
    }

    .hero-content p {
      font-size: 1.2rem;
      color: var(--texto-cinza);
      margin-bottom: 30px;
    }

    .hero-buttons {
      display: flex;
      gap: 20px;
      justify-content: center;
    }

    .diferenciais-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
      margin-top: -60px;
      position: relative;
      z-index: 10;
      padding-bottom: 60px;
    }

    .diferencial-card {
      background-color: var(--bg-card);
      padding: 30px;
      border-radius: 8px;
      border: 1px solid rgba(255, 255, 255, 0.05);
      text-align: center;
      transition: var(--transicao-padrao);
    }

    .diferencial-card:hover {
      transform: translateY(-5px);
      border-color: var(--cor-primaria);
    }

    .diferencial-card i {
      font-size: 2.5rem;
      color: var(--cor-destaque);
      margin-bottom: 15px;
    }

    .diferencial-card h3 {
      font-family: var(--fonte-titulo);
      font-size: 1.8rem;
      margin-bottom: 10px;
      letter-spacing: 1px;
    }

    .promo-split {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      align-items: center;
      margin-top: 40px;
      background-color: var(--bg-card);
      border-radius: 12px;
      overflow: hidden;
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    .promo-img {
      height: 100%;
      min-height: 350px;
      background: url('https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=1000&q=80') center/cover no-repeat;
    }

    .promo-content {
      padding: 40px;
    }

    .promo-content h2 {
      font-family: var(--fonte-titulo);
      font-size: 3rem;
      line-height: 1.1;
      margin-bottom: 15px;
    }

    /* ==========================================================================
       Seção: Jogos (Cards)
       ========================================================================== */
    .section-header {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-header h2 {
      font-family: var(--fonte-titulo);
      font-size: 3.5rem;
      letter-spacing: 2px;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
    }

    .game-card {
      background-color: var(--bg-card);
      border-radius: 12px;
      overflow: hidden;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.05);
      transition: var(--transicao-padrao);
      display: flex;
      flex-direction: column;
    }

    .game-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
      border-color: var(--cor-destaque);
    }

    .card-img-wrap {
      position: relative;
      height: 200px;
      overflow: hidden;
    }

    .card-img-wrap img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: var(--transicao-padrao);
    }

    .game-card:hover .card-img-wrap img {
      transform: scale(1.05);
    }

    .tag-inscreva {
      position: absolute;
      top: 15px;
      right: 15px;
      background-color: var(--cor-primaria);
      color: var(--texto-branco);
      font-size: 0.75rem;
      font-weight: 700;
      padding: 5px 12px;
      border-radius: 20px;
      text-transform: uppercase;
      box-shadow: 0 2px 8px rgba(0,0,0,0.4);
    }

    .card-body {
      padding: 20px;
      display: flex;
      flex-direction: column;
      flex-grow: 1;
    }

    .card-body h3 {
      font-family: var(--fonte-titulo);
      font-size: 1.8rem;
      letter-spacing: 1px;
      margin-bottom: 10px;
    }

    .card-body p {
      color: var(--texto-cinza);
      font-size: 0.9rem;
      margin-bottom: 20px;
      flex-grow: 1;
    }

    .card-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: auto;
    }

    /* ==========================================================================
       Seção: Sobre
       ========================================================================== */
    .split-layout {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
      align-items: center;
    }

    .split-img {
      position: relative;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }

    .split-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    .stats-overlay {
      position: absolute;
      bottom: 20px;
      left: 20px;
      right: 20px;
      background: rgba(20, 20, 20, 0.9);
      backdrop-filter: blur(5px);
      padding: 20px;
      border-radius: 8px;
      display: flex;
      justify-content: space-around;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .stat-item {
      text-align: center;
    }

    .stat-item strong {
      display: block;
      font-family: var(--fonte-titulo);
      font-size: 2rem;
      color: var(--cor-destaque);
    }

    .stat-item span {
      font-size: 0.8rem;
      color: var(--texto-cinza);
      text-transform: uppercase;
    }

    /* ==========================================================================
       Seção: Novidades de Jogos
       ========================================================================== */
    .novidades-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
      background-color: var(--bg-card);
      padding: 40px;
      border-radius: 12px;
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    .novidades-lista {
      list-style: none;
      margin-top: 20px;
    }

    .novidades-lista li {
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 15px;
      color: var(--texto-cinza);
    }

    .novidades-lista i {
      color: var(--cor-primaria);
    }

    .form-estilizado {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 5px;
    }

    .form-group label {
      font-size: 0.85rem;
      color: var(--texto-cinza);
      text-transform: uppercase;
    }

    .form-group input, .form-group select {
      padding: 12px;
      background-color: var(--bg-principal);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 4px;
      color: var(--texto-branco);
      font-family: var(--fonte-corpo);
    }

    .form-group input:focus, .form-group select:focus {
      outline: none;
      border-color: var(--cor-destaque);
    }

    /* ==========================================================================
       Seção: Contato & Integração
       ========================================================================== */
    .contato-cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      margin-bottom: 40px;
    }

    .contato-card {
      background-color: var(--bg-card);
      padding: 25px;
      border-radius: 8px;
      text-align: center;
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    .contato-card i {
      font-size: 2rem;
      color: var(--cor-destaque);
      margin-bottom: 10px;
    }

    .excel-integration-box {
      background: linear-gradient(135deg, #1e1e1e 0%, #141414 100%);
      border: 1px dashed var(--cor-destaque);
      padding: 30px;
      border-radius: 8px;
      text-align: center;
    }

    .excel-integration-box i {
      font-size: 3rem;
      color: #107c41; /* Cor temática Excel/Planilha */
      margin-bottom: 15px;
    }

    /* ==========================================================================
       Footer / Apps de Jogos
       ========================================================================== */
    footer {
      background-color: #050505;
      padding: 50px 0 20px 0;
      border-top: 1px solid rgba(255, 255, 255, 0.05);
    }

    .footer-content {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr;
      gap: 40px;
      margin-bottom: 40px;
    }

    .footer-apps a {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background-color: var(--bg-card);
      padding: 10px 18px;
      border-radius: 6px;
      margin-right: 10px;
      margin-top: 10px;
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: var(--transicao-padrao);
    }

    .footer-apps a:hover {
      background-color: var(--bg-card-hover);
      border-color: var(--cor-destaque);
    }

    .whatsapp-btn-fixed {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background-color: #25d366;
      color: white;
      width: 60px;
      height: 60px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 2rem;
      box-shadow: 0 4px 10px rgba(0,0,0,0.5);
      z-index: 999;
      transition: var(--transicao-padrao);
    }

    .whatsapp-btn-fixed:hover {
      transform: scale(1.1);
    }

    /* ==========================================================================
       Responsividade
       ========================================================================== */
    @media (max-width: 992px) {
      .promo-split, .split-layout, .novidades-container {
        grid-template-columns: 1fr;
      }
      .contato-cards {
        grid-template-columns: 1fr;
      }
      .footer-content {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 768px) {
      .nav-menu {
        display: none; /* Simplificação mobile */
      }
      .hero-content h1 {
        font-size: 3rem;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="container nav-container">
      <div class="logo">
        <i class="fa-solid fa-owl"></i> CORUJÃO <span>DOS BRUXOS</span>
      </div>
      <ul class="nav-menu">
        <li><a class="nav-link active" onclick="navigateTo('home')">Home</a></li>
        <li><a class="nav-link" onclick="navigateTo('jogos')">Jogos</a></li>
        <li><a class="nav-link" onclick="navigateTo('sobre')">Sobre</a></li>
        <li><a class="nav-link" onclick="navigateTo('novidades')">Novidades</a></li>
        <li><a class="nav-link" onclick="navigateTo('contato')">Contato</a></li>
      </ul>
      <button class="btn btn-primario" onclick="navigateTo('novidades')">Inscreva-se</button>
    </div>
  </header>

  <section id="home" class="spa-view active">
    <div class="hero">
      <div class="hero-content container">
        <p class="cursivo">O portal definitivo da comunidade gamer</p>
        <h1>Corujão dos Bruxos</h1>
        <p>Análises profundas, guias avançados e a cobertura completa dos principais eSports e lançamentos do mercado.</p>
        <div class="hero-buttons">
          <button class="btn btn-primario" onclick="navigateTo('jogos')">Explorar Jogos</button>
          <button class="btn btn-destaque" onclick="navigateTo('novidades')">Inscrever-se</button>
        </div>
      </div>
    </div>

    <div class="container">
      <div class="diferenciais-grid">
        <div class="diferencial-card">
          <i class="fa-solid fa-fire"></i>
          <h3>Análises no Forno</h3>
          <p>Reviews detalhados lançados logo nas primeiras horas de lançamento dos títulos mais aguardados.</p>
        </div>
        <div class="diferencial-card">
          <i class="fa-solid fa-clock"></i>
          <h3>Maratona 48h</h3>
          <p>Cobertura ininterrupta de lançamentos e transmissões de campeonatos mundiais.</p>
        </div>
        <div class="diferencial-card">
          <i class="fa-solid fa-certificate"></i>
          <h3>Conteúdo DOP</h3>
          <p>Garantia de origem: artigos, guias e detonados produzidos 100% por pro-players e especialistas.</p>
        </div>
      </div>

      <div class="promo-split">
        <div class="promo-img"></div>
        <div class="promo-content">
          <span class="cursivo">Evento Semanal</span>
          <h2>Terça em Dobro</h2>
          <p>Toda terça-feira trazemos o dobro de análises, chaves de acesso gratuitas e sorteios de passe de batalha para os inscritos da nossa newsletter.</p>
          <br>
          <button class="btn btn-destaque" onclick="navigateTo('novidades')">Garantir Benefício</button>
        </div>
      </div>
    </div>
  </section>

  <section id="jogos" class="spa-view container">
    <div class="section-header">
      <p class="cursivo">Catálogo Selecionado</p>
      <h2>Principais Jogos</h2>
    </div>

    <div class="cards-grid">
      <div class="game-card">
        <div class="card-img-wrap">
          <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?auto=format&fit=crop&w=600&q=80" alt="RPG de Ação">
          <span class="tag-inscreva">Inscreva-se</span>
        </div>
        <div class="card-body">
          <h3>Elden Ring: Shadow of the Erdtree</h3>
          <p>Guias completos de chefes, builds otimizadas para PvP e localização de todos os itens secretos do mapa.</p>
          <div class="card-footer">
            <button class="btn btn-primario" onclick="navigateTo('novidades')">Inscreva-se</button>
          </div>
        </div>
      </div>

      <div class="game-card">
        <div class="card-img-wrap">
          <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=600&q=80" alt="FPS Competitivo">
          <span class="tag-inscreva">Inscreva-se</span>
        </div>
        <div class="card-body">
          <h3>Valorant & eSports</h3>
          <p>Análises táticas do meta atual, lineups de habilidades para todos os agentes e cobertura dos torneios VCT.</p>
          <div class="card-footer">
            <button class="btn btn-primario" onclick="navigateTo('novidades')">Inscreva-se</button>
          </div>
        </div>
      </div>

      <div class="game-card">
        <div class="card-img-wrap">
          <img src="https://images.unsplash.com/photo-1612287230202-1ff1d85d1bdf?auto=format&fit=crop&w=600&q=80" alt="Cyberpunk 2077">
          <span class="tag-inscreva">Inscreva-se</span>
        </div>
        <div class="card-body">
          <h3>Cyberpunk 2077</h3>
          <p>Explorando Night City: os melhores mods de performance, caminhos narrativos e segredos do universo sci-fi.</p>
          <div class="card-footer">
            <button class="btn btn-primario" onclick="navigateTo('novidades')">Inscreva-se</button>
          </div>
        </div>
      </div>
    </div>

    <div style="text-align: center; margin-top: 60px; background-color: var(--bg-card); padding: 40px; border-radius: 12px;">
      <i class="fa-solid fa-gamepad" style="font-size: 3rem; color: var(--cor-destaque); margin-bottom: 15px;"></i>
      <h3 style="font-family: var(--fonte-titulo); font-size: 2rem;">Aviso de Novos Jogos</h3>
      <p style="color: var(--texto-cinza); margin-bottom: 20px;">Quer sugerir uma análise ou entrar na comunidade VIP do WhatsApp?</p>
      <a href="https://wa.me/" target="_blank" class="btn btn-destaque"><i class="fa-brands fa-whatsapp"></i> Entrar no Canal do WhatsApp</a>
    </div>
  </section>

  <section id="sobre" class="spa-view container">
    <div class="split-layout">
      <div class="split-img">
        <img src="https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=800&q=80" alt="Setup Gamer">
        <div class="stats-overlay">
          <div class="stat-item">
            <strong>+50k</strong>
            <span>Leitores</span>
          </div>
          <div class="stat-item">
            <strong>4.9</strong>
            <span>Estrelas (Avaliação)</span>
          </div>
        </div>
      </div>
      <div>
        <span class="cursivo">Nossa História</span>
        <h2 style="font-family: var(--fonte-titulo); font-size: 3.5rem; line-height: 1.1; margin-bottom: 20px;">Os Maiores Jogos da Atualidade</h2>
        <p style="color: var(--texto-cinza); margin-bottom: 15px;">O Corujão dos Bruxos nasceu da paixão por madrugadas intensas de gameplay e discussões profundas sobre mecânicas de jogo. Nosso objetivo é entregar análises imparciais, notícias em primeira mão e tutoriais de altíssimo nível.</p>
        <p style="color: var(--texto-cinza);">Reunimos uma equipe de criadores e jogadores experientes cobrindo desde os indies mais aclamados até as produções AAA dos maiores estúdios globais.</p>
      </div>
    </div>
  </section>

  <section id="novidades" class="spa-view container">
    <div class="novidades-container">
      <div>
        <span class="cursivo">Fique por dentro</span>
        <h2 style="font-family: var(--fonte-titulo); font-size: 3rem; margin-bottom: 15px;">Novidades de Jogos</h2>
        <p style="color: var(--texto-cinza);">Cadastre-se na nossa newsletter semanal e receba em primeira mão relatórios de meta, anúncios de lançamentos e códigos promocionais.</p>
        <ul class="novidades-lista">
          <li><i class="fa-solid fa-check"></i> Cobertura semanal dos patch notes de eSports</li>
          <li><i class="fa-solid fa-check"></i> Convites para testes beta fechados</li>
          <li><i class="fa-solid fa-check"></i> Resumo de ofertas e jogos gratuitos da semana</li>
        </ul>
      </div>

      <div>
        <form class="form-estilizado" onsubmit="handleFormSubmit(event)">
          <div class="form-group">
            <label for="nome">Nome Completo</label>
            <input type="text" id="nome" required placeholder="Digite seu nome">
          </div>
          <div class="form-group">
            <label for="encontrar">Onde nos encontrou?</label>
            <select id="encontrar">
              <option value="twitch">Twitch</option>
              <option value="youtube">YouTube</option>
              <option value="instagram">Instagram</option>
              <option value="google">Google</option>
            </select>
          </div>
          <button type="submit" class="btn btn-primario">Inscrever-se Agora</button>
        </form>
      </div>
    </div>
  </section>

  <section id="contato" class="spa-view container">
    <div class="section-header">
      <p class="cursivo">Fale Conosco</p>
      <h2>Canais de Contato</h2>
    </div>

    <div class="contato-cards">
      <div class="contato-card">
        <i class="fa-solid fa-user"></i>
        <h3>Suporte Técnico</h3>
        <p style="color: var(--texto-cinza);">Atendimento ao Leitor</p>
      </div>
      <div class="contato-card">
        <i class="fa-solid fa-envelope"></i>
        <h3>E-mail Geral</h3>
        <p style="color: var(--texto-cinza);">contato@corujaodosbruxos.com</p>
      </div>
      <div class="contato-card">
        <i class="fa-solid fa-bullhorn"></i>
        <h3>Imprensa & Parcerias</h3>
        <p style="color: var(--texto-cinza);">parcerias@corujaodosbruxos.com</p>
      </div>
    </div>

    <div class="excel-integration-box">
      <i class="fa-solid fa-file-excel"></i>
      <h3 style="font-family: var(--fonte-titulo); font-size: 2rem;">Integração de Base de Contatos</h3>
      <p style="color: var(--texto-cinza); max-width: 600px; margin: 0 auto 20px auto;">Todos os dados capturados via cadastro de e-mail são processados e sincronizados com nossa planilha de controle via API.</p>
      <button class="btn btn-destaque" onclick="alert('Módulo de Sincronização Ativo - Planilha Atualizada.')">Simular Sincronização Excel</button>
    </div>
  </section>

  <footer>
    <div class="container footer-content">
      <div>
        <div class="logo" style="margin-bottom: 15px;">
          <i class="fa-solid fa-owl"></i> CORUJÃO
        </div>
        <p style="color: var(--texto-cinza); font-size: 0.9rem;">O melhor conteúdo sobre games reunido em um único lugar. Feito por quem ama jogar para quem vive de jogos.</p>
      </div>

      <div>
        <h4 style="font-family: var(--fonte-titulo); font-size: 1.5rem; margin-bottom: 15px;">Links Rápidos</h4>
        <ul style="list-style: none; color: var(--texto-cinza); line-height: 2;">
          <li><a onclick="navigateTo('home')">Home</a></li>
          <li><a onclick="navigateTo('jogos')">Jogos</a></li>
          <li><a onclick="navigateTo('sobre')">Sobre</a></li>
        </ul>
      </div>

      <div>
        <h4 style="font-family: var(--fonte-titulo); font-size: 1.5rem; margin-bottom: 15px;">Apps de Jogos</h4>
        <div class="footer-apps">
          <a href="https://store.steampowered.com/" target="_blank"><i class="fa-brands fa-steam"></i> Steam</a>
          <a href="#" target="_blank"><i class="fa-solid fa-gamepad"></i> App Gamer</a>
        </div>
      </div>
    </div>

    <div style="text-align: center; color: var(--texto-cinza); font-size: 0.8rem; border-top: 1px solid rgba(255,255,255,0.05); padding-top: 20px;">
      &copy; 2026 Corujão dos Bruxos. Todos os direitos reservados.
    </div>
  </footer>

  <a href="https://wa.me/" class="whatsapp-btn-fixed" target="_blank" title="Fale conosco no WhatsApp">
    <i class="fa-brands fa-whatsapp"></i>
  </a>

  <script>
    /**
     * Gerenciador de Navegação da SPA
     * Exibe a seção solicitada e esconde as demais sem recarregar a página
     */
    function navigateTo(viewId) {
      // Ocultar todas as seções
      const views = document.querySelectorAll('.spa-view');
      views.forEach(view => {
        view.classList.remove('active');
      });

      // Exibir a seção selecionada
      const targetView = document.getElementById(viewId);
      if (targetView) {
        targetView.classList.add('active');
      }

      // Atualizar a classe active no menu de navegação
      const navLinks = document.querySelectorAll('.nav-link');
      navLinks.forEach(link => {
        link.classList.remove('active');
      });

      // Rolar para o topo suavemente ao trocar de tela
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    /**
     * Manipulação de envio do formulário estilizado
     */
    function handleFormSubmit(event) {
      event.preventDefault();
      const nome = document.getElementById('nome').value;
      alert(`Obrigado pelo cadastro, ${nome}! Seus dados foram sincronizados.`);
      event.target.reset();
    }
  </script>
</body>
</html>
