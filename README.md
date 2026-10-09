
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#000000">
  <meta name="description" content="MeuPrimeiroDate — conheça pessoas, descubra afinidades e crie conexões verdadeiras. Plataforma exclusiva para maiores de 18 anos.">
  <title>MeuPrimeiroDate 💗 | Conexões reais</title>
  <style>
    :root {
      --bg: #000;
      --surface: #151515;
      --surface2: #202020;
      --pink: #ff1493;
      --pink2: #ff66f4;
      --white: #fff;
      --muted: #aaa;
      --border: #303030;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      background: var(--bg);
      color: var(--white);
      font-family: Inter, system-ui, Arial, sans-serif;
    }
    a { color: inherit; text-decoration: none; }
    button, input, select { font: inherit; }
    button { cursor: pointer; }

    .container { width: min(1120px, 92%); margin: auto; }
    header {
      position: sticky;
      top: 0;
      z-index: 10;
      background: rgba(0,0,0,.88);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }
    nav {
      min-height: 74px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }
    .brand { font-size: 1.35rem; font-weight: 850; letter-spacing: -.7px; }
    .brand span { color: var(--pink); }
    .navlinks { display: flex; align-items: center; gap: 22px; color: #ddd; font-size: .94rem; }
    .btn {
      border: 0;
      border-radius: 999px;
      padding: 12px 20px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      font-weight: 750;
      transition: .2s;
    }
    .btn:hover { transform: translateY(-2px); }
    .primary { color: white; background: linear-gradient(110deg,var(--pink),#c600ff); }
    .secondary { color: white; background: #191919; border: 1px solid #444; }
    .hero {
      min-height: 590px;
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      align-items: center;
      gap: 48px;
      padding-top: 55px;
      padding-bottom: 65px;
    }
    .eyebrow {
      color: var(--pink2);
      text-transform: uppercase;
      letter-spacing: 2px;
      font-weight: 800;
      font-size: .76rem;
    }
    h1 { font-size: clamp(2.8rem,6vw,5.2rem); line-height: 1.02; letter-spacing: -3px; margin: 18px 0; }
    h1 span, .gradient { color: var(--pink2); }
    .hero p { color: var(--muted); line-height: 1.8; font-size: 1.08rem; max-width: 530px; }
    .actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 28px; }
    .note { font-size: .8rem !important; margin-top: 18px; }
    .visual {
      min-height: 390px;
      position: relative;
      display: grid;
      place-items: center;
      border: 1px solid #3c1230;
      border-radius: 34px;
      overflow: hidden;
      background: radial-gradient(ellipse at 50% 40%,#521032 0%,#170611 38%,#080808 72%);
    }
    .bigheart {
      font-size: clamp(8rem,20vw,14rem);
      filter: drop-shadow(0 0 30px rgba(255,20,147,.55));
      animation: float 4s ease-in-out infinite;
    }
    .visual-label {
      position: absolute;
      bottom: 24px;
      left: 24px;
      right: 24px;
      padding: 16px;
      border: 1px solid #ffffff22;
      background: #080808bb;
      border-radius: 18px;
      backdrop-filter: blur(10px);
    }
    .visual-label small { color: var(--pink2); }
    @keyframes float { 50% { transform: translateY(-12px); } }

    section { padding: 70px 0; }
    .section-head { margin-bottom: 28px; }
    .section-head h2 { font-size: clamp(2rem,4vw,3rem); margin: 8px 0; letter-spacing: -1px; }
    .section-head p { color: var(--muted); line-height: 1.7; }
    .filters { display: flex; flex-wrap: wrap; gap: 10px; margin: 24px 0; }
    .filters input, .filters select, .field input, .field select {
      min-width: 0;
      background: var(--surface);
      color: white;
      border: 1px solid #393939;
      padding: 13px 15px;
      border-radius: 12px;
    }
    .filters input { flex: 1; min-width: 190px; }
    .profiles { display: grid; grid-template-columns: repeat(3,minmax(0,1fr)); gap: 20px; }
    .profile {
      overflow: hidden;
      border: 1px solid var(--border);
      border-radius: 22px;
      background: var(--surface);
      transition: .25s;
    }
    .profile:hover { transform: translateY(-5px); border-color: #8a285e; }
    .profile-art {
      min-height: 240px;
      display: grid;
      place-items: center;
      font-size: 4.5rem;
      background: radial-gradient(circle at 50% 35%,#58203e,#20111b 65%,#121212);
    }
    .profile-body { padding: 19px; }
    .profile-body h3 { margin: 0 0 6px; }
    .profile-body p { color: var(--muted); line-height: 1.55; font-size: .91rem; }
    .tag {
      display: inline-block;
      font-size: .72rem;
      padding: 6px 9px;
      border: 1px solid #69304e;
      border-radius: 999px;
      color: #ff9dd1;
      margin-bottom: 10px;
    }
    .profile-actions { display: flex; gap: 8px; margin-top: 15px; }
    .profile-actions button { flex: 1; }
    .empty { color: var(--muted); padding: 30px 0; }

    .features { display: grid; grid-template-columns: repeat(3,1fr); gap: 18px; }
    .feature {
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 24px;
      background: linear-gradient(145deg,#171717,#090909);
    }
    .feature .emoji { font-size: 1.8rem; }
    .feature h3 { margin-bottom: 8px; }
    .feature p { color: var(--muted); line-height: 1.7; font-size: .94rem; }
    .cta {
      text-align: center;
      padding: 55px 25px;
      border: 1px solid #58203e;
      border-radius: 28px;
      background: radial-gradient(ellipse at top,#391027,#0b080a 65%);
    }
    .cta h2 { font-size: clamp(2rem,4vw,3.2rem); margin: 0 0 14px; }
    .cta p { color: #ccc; line-height: 1.7; }
    footer { border-top: 1px solid var(--border); padding: 28px 0; color: var(--muted); font-size: .86rem; }
    .footer-inner { display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px; }

    dialog {
      background: #121212;
      color: white;
      width: min(460px,92%);
      border: 1px solid #494949;
      border-radius: 22px;
      padding: 26px;
    }
    dialog::backdrop { background: #000c; backdrop-filter: blur(5px); }
    .modal-head { display: flex; justify-content: space-between; align-items: center; gap: 15px; }
    .modal-head h2 { font-size: 1.4rem; }
    .close { background: #292929; color: white; border: 0; border-radius: 50%; width: 36px; height: 36px; }
    .field { display: grid; gap: 7px; margin: 15px 0; }
    .field label { font-size: .9rem; color: #ddd; }
    .field input, .field select { width: 100%; }
    .disclaimer { color: var(--muted); font-size: .8rem; line-height: 1.6; }
    .toast {
      position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%);
      background: #222; border: 1px solid #555; padding: 13px 18px;
      border-radius: 12px; z-index: 30; max-width: 90%; display: none;
    }
    .toast.show { display: block; }
    @media(max-width:800px) {
      .hero { grid-template-columns: 1fr; gap: 30px; padding-top: 40px; }
      .visual { min-height: 300px; }
      .profiles { grid-template-columns: repeat(2,minmax(0,1fr)); }
      .features { grid-template-columns: 1fr; }
      .navlinks a:not(.btn) { display: none; }
    }
    @media(max-width:520px) {
      h1 { letter-spacing: -1.8px; }
      .profiles { grid-template-columns: 1fr; }
      .profile-art { min-height: 220px; }
      .brand { font-size: 1.1rem; }
      .navlinks { gap: 8px; }
      .navlinks .btn { padding: 10px 13px; font-size: .83rem; }
      section { padding: 48px 0; }
    }
  </style>
</head>
<body>
  <header>
    <nav class="container">
      <a class="brand" href="#" aria-label="MeuPrimeiroDate início">♡ MeuPrimeiro<span>Date</span></a>
      <div class="navlinks">
        <a href="#como-funciona">Como funciona</a>
        <a href="#descobrir">Descobrir</a>
        <button class="btn secondary" onclick="openModal('login')">Entrar</button>
        <button class="btn primary" onclick="openModal('signup')">Criar conta</button>
      </div>
    </nav>
  </header>

  <main>
    <section class="container hero">
      <div>
        <div class="eyebrow">♡ Seu próximo capítulo começa aqui</div>
        <h1>Menos distância.<br>Mais <span>conexão.</span></h1>
        <p>Conheça pessoas novas, descubra afinidades e dê espaço para histórias que podem começar com um simples olá.</p>
        <div class="actions">
          <button class="btn primary" onclick="openModal('signup')">💗 Encontrar conexões</button>
          <a class="btn secondary" href="#descobrir">Explorar perfis ↓</a>
        </div>
        <p class="note">🔞 Exclusivo para maiores de 18 anos. Respeito e privacidade importam.</p>
      </div>
      <div class="visual" aria-label="Coração rosa em fundo escuro">
        <div class="bigheart">♡</div>
        <div class="visual-label">
          <small>MEUPRIMEIRODATE</small>
          <div><strong>Conexões que começam com afinidade.</strong></div>
        </div>
      </div>
    </section>

    <section id="descobrir">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">Descubra novas histórias</div>
          <h2>Pessoas, possibilidades e <span class="gradient">conexões.</span></h2>
          <p>Estes são exemplos fictícios para demonstrar o layout. Não representam pessoas cadastradas.</p>
        </div>
        <div class="filters">
          <input id="search" type="search" placeholder="Buscar por nome demonstrativo..." aria-label="Buscar perfis">
          <select id="interest" aria-label="Filtrar por interesse">
            <option value="">Todos os interesses</option>
            <option value="viagens">Viagens</option>
            <option value="musica">Música</option>
            <option value="gastronomia">Gastronomia</option>
            <option value="natureza">Natureza</option>
          </select>
        </div>
        <div class="profiles" id="profiles"></div>
        <p class="disclaimer">Perfis demonstrativos. A versão de produção deve exibir somente perfis autorizados e gerenciados por usuários reais.</p>
      </div>
    </section>

    <section id="como-funciona">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">Simples e intuitivo</div>
          <h2>Uma conexão de cada vez.</h2>
        </div>
        <div class="features">
          <article class="feature">
            <div class="emoji">👤</div>
            <h3>Crie seu perfil</h3>
            <p>Conte um pouco sobre você e adicione suas próprias fotos. Você controla o que deseja compartilhar.</p>
          </article>
          <article class="feature">
            <div class="emoji">💗</div>
            <h3>Descubra afinidades</h3>
            <p>Explore perfis e demonstre interesse. Curtidas e matches reais exigem uma conta e um serviço de backend.</p>
          </article>
          <article class="feature">
            <div class="emoji">🛡️</div>
            <h3>Conheça com cuidado</h3>
            <p>Respeite os limites, proteja seus dados e denuncie comportamentos inadequados quando houver essa função disponível.</p>
          </article>
        </div>
      </div>
    </section>

    <section class="container">
      <div class="cta">
        <h2>Uma nova história pode começar <span class="gradient">hoje.</span></h2>
        <p>Crie seu perfil quando o cadastro seguro estiver configurado.</p>
        <button class="btn primary" onclick="openModal('signup')">Quero conhecer o site 💗</button>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <div>♡ MeuPrimeiro<span class="gradient">Date</span> · Conexões com respeito.</div>
      <div>18+ · <a href="#como-funciona">Segurança</a> · Protótipo demonstrativo</div>
      <div>© <span id="year"></span> MeuPrimeiroDate</div>
    </div>
  </footer>

  <dialog id="modal">
    <div class="modal-head">
      <h2 id="modalTitle">Criar conta</h2>
      <button class="close" onclick="closeModal()" aria-label="Fechar">✕</button>
    </div>
    <div id="modalContent"></div>
  </dialog>
  <div class="toast" id="toast" role="status" aria-live="polite"></div>

  <script>
    // Perfis fictícios usados somente para demonstrar o layout.
    // Nenhum dado real é armazenado ou enviado por este protótipo.
    const demoProfiles = [
      { name: "Alex · DEMO", age: 28, interest: "viagens", emoji: "🌍", bio: "Ama conhecer lugares novos e experimentar outras culturas." },
      { name: "Sam · DEMO", age: 31, interest: "musica", emoji: "🎧", bio: "Música boa, conversas longas e shows ao vivo." },
      { name: "Dani · DEMO", age: 27, interest: "gastronomia", emoji: "🍜", bio: "Descobrindo cafés, receitas e novos sabores." },
      { name: "Chris · DEMO", age: 30, interest: "natureza", emoji: "🌿", bio: "Trilhas, natureza e finais de semana ao ar livre." },
      { name: "Taylor · DEMO", age: 29, interest: "viagens", emoji: "✈️", bio: "Planejando a próxima aventura e novas histórias." },
      { name: "Jordan · DEMO", age: 32, interest: "musica", emoji: "🎸", bio: "Guitarra, cinema e boas conversas sem pressa." }
    ];

    const profilesElement = document.getElementById("profiles");
    const searchElement = document.getElementById("search");
    const interestElement = document.getElementById("interest");

    function renderProfiles() {
      const term = searchElement.value.trim().toLocaleLowerCase("pt-BR");
      const interest = interestElement.value;
      const filtered = demoProfiles.filter(profile =>
        profile.name.toLocaleLowerCase("pt-BR").includes(term) &&
        (!interest || profile.interest === interest)
      );

      profilesElement.innerHTML = "";

      if (!filtered.length) {
        profilesElement.innerHTML = '<p class="empty">Nenhum perfil demonstrativo encontrado.</p>';
        return;
      }

      filtered.forEach(profile => {
        const card = document.createElement("article");
        card.className = "profile";

        const art = document.createElement("div");
        art.className = "profile-art";
        art.setAttribute("aria-hidden", "true");
        art.textContent = profile.emoji;

        const body = document.createElement("div");
        body.className = "profile-body";

        const tag = document.createElement("span");
        tag.className = "tag";
        tag.textContent = "PERFIL FICTÍCIO · DEMO";

        const title = document.createElement("h3");
        title.textContent = `${profile.name} · ${profile.age}`;

        const bio = document.createElement("p");
        bio.textContent = profile.bio;

        const actions = document.createElement("div");
        actions.className = "profile-actions";

        const like = document.createElement("button");
        like.className = "btn primary";
        like.textContent = "♡ Curtir";
        like.addEventListener("click", () =>
          showToast("Demonstração: curtidas reais exigem cadastro e backend.")
        );

        const details = document.createElement("button");
        details.className = "btn secondary";
        details.textContent = "Ver perfil";
        details.addEventListener("click", () =>
          showToast("Este é um perfil fictício usado para demonstrar o site.")
        );

        actions.append(like, details);
        body.append(tag, title, bio, actions);
        card.append(art, body);
        profilesElement.append(card);
      });
    }

    function openModal(type) {
      const modal = document.getElementById("modal");
      const title = document.getElementById("modalTitle");
      const content = document.getElementById("modalContent");

      if (type === "login") {
        title.textContent = "Entrar";
        content.innerHTML = `
          <p class="disclaimer">O login ainda não está conectado a um servidor.</p>
          <form id="demoForm">
            <div class="field"><label for="email">E-mail</label><input id="email" type="email" autocomplete="email" required></div>
            <div class="field"><label for="password">Senha</label><input id="password" type="password" autocomplete="current-password" required></div>
            <button class="btn primary" type="submit" style="width:100%">Continuar</button>
          </form>`;
      } else {
        title.textContent = "Criar conta";
        content.innerHTML = `
          <p class="disclaimer">Este formulário é apenas demonstrativo: não cria conta nem transmite dados.</p>
          <form id="demoForm">
            <div class="field"><label for="name">Como deseja ser chamado(a)?</label><input id="name" maxlength="60" autocomplete="name" required></div>
            <div class="field"><label for="email">E-mail</label><input id="email" type="email" autocomplete="email" required></div>
            <div class="field"><label for="birth">Data de nascimento</label><input id="birth" type="date" required></div>
            <div class="field"><label><input id="agree" type="checkbox" required> Confirmo que tenho 18 anos ou mais e aceito ler os termos e a política de privacidade.</label></div>
            <button class="btn primary" type="submit" style="width:100%">Continuar</button>
          </form>`;
      }

      document.getElementById("demoForm").addEventListener("submit", event => {
        event.preventDefault();
        showToast("Protótipo: nenhum dado foi enviado ou salvo. Configure autenticação segura para lançar o cadastro.");
        closeModal();
      });

      if (!modal.open) modal.showModal();
    }

    function closeModal() {
      document.getElementById("modal").close();
    }

    function showToast(message) {
      const toast = document.getElementById("toast");
      toast.textContent = message;
      toast.classList.add("show");
      window.setTimeout(() => toast.classList.remove("show"), 4000);
    }

    searchElement.addEventListener("input", renderProfiles);
    interestElement.addEventListener("change", renderProfiles);
    document.getElementById("year").textContent = new Date().getFullYear();
    renderProfiles();
  </script>
</body>
</html>
import { startAuthorization } from '@vercel/connect';

startAuthorization('github/meuprimeirodate-2027', {
  subject: { type: "user", id: "usr_123" }
}); .
