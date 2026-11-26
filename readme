<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MOST WANTED</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Anton&family=Montserrat:wght@400;600;700&display=swap" rel="stylesheet" />

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html,
    body {
      min-height: 100vh;
      background-color: #000000;
      color: #ffffff;
      font-family: 'Montserrat', sans-serif;
      overflow-x: hidden;
    }

    .hidden {
      display: none !important;
    }

    /* ================= INTRO SCREEN ================= */
    #intro-screen {
      position: fixed;
      inset: 0;
      width: 100vw;
      height: 100vh;
      background-color: #000000;
      display: grid;
      place-items: center;
      z-index: 50;
    }

    .intro-logo-btn {
      background: none;
      border: none;
      padding: 0;
      cursor: pointer;
      outline: none;
      -webkit-tap-highlight-color: transparent;
    }

    .intro-logo-img {
      display: block;
      max-width: 90vw;
      width: 420px;
      height: auto;
      user-select: none;
      -webkit-user-drag: none;
      transition: transform 0.25s ease, filter 0.25s ease;
    }

    .intro-logo-btn:hover .intro-logo-img {
      transform: scale(1.06);
      filter:
        drop-shadow(1px 0 0 rgba(255, 255, 255, 0.9))
        drop-shadow(-1px 0 0 rgba(255, 255, 255, 0.9))
        drop-shadow(0 1px 0 rgba(255, 255, 255, 0.9))
        drop-shadow(0 -1px 0 rgba(255, 255, 255, 0.9))
        drop-shadow(0 0 6px rgba(255, 255, 255, 0.45));
    }

    .intro-logo-btn:active .intro-logo-img {
      transform: scale(1.02);
    }

    /* ================= NEXT PAGE ================= */
    #main-page {
      min-height: 100vh;
      background-color: #000000;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 40px 20px;
      position: relative;
      overflow-x: hidden;
    }

    /* Full-Screen Stars Background */
    .stars-layer {
      position: fixed;
      inset: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      overflow: hidden;
      z-index: 0;
    }

    .star {
      position: absolute;
      background: #ffffff;
      border-radius: 50%;
      box-shadow: 0 0 6px rgba(255, 255, 255, 0.85);
      animation: floatStar linear infinite, twinkle ease-in-out infinite;
    }

    @keyframes floatStar {
      0% {
        transform: translateY(15vh) translateX(0);
      }
      100% {
        transform: translateY(-120vh) translateX(30px);
      }
    }

    @keyframes twinkle {
      0%, 100% {
        opacity: 0.2;
      }
      50% {
        opacity: 1;
      }
    }

    /* Hover Background Video Layer */
    #hover-video-bg {
      position: fixed;
      inset: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.45s ease;
      z-index: 1;
    }

    #hover-video-bg.active {
      opacity: 1;
    }

    #hover-video-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.45);
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.45s ease;
      z-index: 1;
    }

    #hover-video-overlay.active {
      opacity: 1;
    }

    /* Header Logo Section */
    .header {
      text-align: center;
      margin-bottom: 50px;
      position: relative;
      z-index: 2;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .header-logo {
      display: block;
      max-width: 85vw;
      width: 340px;
      height: auto;
      user-select: none;
      -webkit-user-drag: none;
    }

    /* Main Cards Grid */
    .cards-container {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 20px;
      max-width: 1200px;
      width: 100%;
      flex-wrap: wrap;
      position: relative;
      z-index: 2;
    }

    .card {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 200px;
      transition: transform 0.3s ease;
      cursor: pointer;
    }

    .card:hover {
      transform: translateY(-8px);
    }

    .image-box {
      width: 100%;
      border: 2px solid #ffffff;
      overflow: hidden;
      background-color: #111;
      margin-bottom: 14px;
      transition: border-color 0.25s ease, box-shadow 0.25s ease;
    }

    .card:hover .image-box {
      box-shadow: 0 0 14px rgba(255, 255, 255, 0.35);
    }

    .card.short .image-box {
      height: 360px;
    }

    .card.tall .image-box {
      height: 410px;
    }

    .image-box img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: grayscale(100%) contrast(115%);
      display: block;
      transition: transform 0.4s ease;
    }

    .card:hover .image-box img {
      transform: scale(1.05);
    }

    /* Names and IDs */
    .name {
      font-size: 1.05rem;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 4px;
      text-align: center;
      letter-spacing: 1px;
    }

    .handle {
      font-size: 0.68rem;
      color: #888888;
      text-align: center;
      letter-spacing: 0.5px;
    }

    @media (max-width: 1100px) {
      .cards-container {
        gap: 25px;
      }

      .card.short .image-box,
      .card.tall .image-box {
        height: 350px;
      }
    }
  </style>
</head>
<body>

  <!-- Intro Screen -->
  <section id="intro-screen">
    <button type="button" class="intro-logo-btn" id="introLogoBtn" aria-label="Enter Site">
      <img
        src="https://i.ibb.co/Vck8gJdV/1000096054-removebg-preview-1-removebg-preview.png"
        alt="Most Wanted Logo"
        class="intro-logo-img"
      />
    </button>
  </section>

  <!-- Next Page -->
  <div id="main-page" class="hidden">
    <!-- Full-Screen Stars Background -->
    <div class="stars-layer" id="starsLayer"></div>

    <!-- Background Music -->
    <audio id="bg-music" src="https://files.catbox.moe/14pt8u.mp3" loop preload="auto"></audio>

    <!-- Dynamic Hover Background Video -->
    <video id="hover-video-bg" loop playsinline preload="auto"></video>
    <div id="hover-video-overlay"></div>

    <header class="header">
      <img
        src="https://i.ibb.co/Vck8gJdV/1000096054-removebg-preview-1-removebg-preview.png"
        alt="Most Wanted Logo"
        class="header-logo"
      />
    </header>

    <main class="cards-container">
      <!-- Card 1: DEVS -->
      <div class="card short"
           data-id="1170572664033792071"
           data-fallback="DEVS"
           data-video="https://cdn.discordapp.com/attachments/1481125659840348264/1575484813308330085/snaptik_7580148250875907350_v3.mp4?ex=6b097412&is=6b082292&hm=fdb712f60eb0adfa22f5d95bbd21f07ccc91cd22cf5b5520ffa3cb174ab26cfc&">
        <div class="image-box">
          <img src="https://cdn.discordapp.com/embed/avatars/0.png" alt="DEVS">
        </div>
        <h2 class="name">DEVS</h2>
        <p class="handle">@1170572664033792071</p>
      </div>

      <!-- Card 2: COZY -->
      <div class="card tall"
           data-id="1267457144274288741"
           data-fallback="COZY"
           data-video="https://cdn.discordapp.com/attachments/1481125659840348264/1575484813765513216/snaptik_7593111116348214550_v3.mp4?ex=6b097412&is=6b082292&hm=0c0aea9da8eeef3b6cd0db4cd01218cd1f0a9336e3630c32dbad80bdfa2f453a&">
        <div class="image-box">
          <img src="https://cdn.discordapp.com/embed/avatars/1.png" alt="COZY">
        </div>
        <h2 class="name">COZY</h2>
        <p class="handle">@1267457144274288741</p>
      </div>

      <!-- Card 3: WXZ (NASA GITNA) -->
      <div class="card short"
           data-id="1252968935360299071"
           data-fallback="WXZ"
           data-video="https://cdn.discordapp.com/attachments/1481125659840348264/1575484815124209684/snaptik_7597089058422050070_v3.mp4?ex=6b097413&is=6b082293&hm=3fc21ecd30b164cba2997e820195b1c6bb332484032c9f619ba1c2735b7bf124&">
        <div class="image-box">
          <img src="https://cdn.discordapp.com/embed/avatars/2.png" alt="WXZ">
        </div>
        <h2 class="name">WXZ</h2>
        <p class="handle">@1252968935360299071</p>
      </div>

      <!-- Card 4: PVZ -->
      <div class="card tall"
           data-id="1381988741593174046"
           data-fallback="PVZ"
           data-video="https://cdn.discordapp.com/attachments/1481125659840348264/1575484814608433303/snaptik_7599756828343291158_v3.mp4?ex=6b097412&is=6b082292&hm=b5db71223a85d4dbcf67fba1961fd5261e9c040c6acd74c917e2612214f3ec8b&">
        <div class="image-box">
          <img src="https://cdn.discordapp.com/embed/avatars/3.png" alt="PVZ">
        </div>
        <h2 class="name">PVZ</h2>
        <p class="handle">@1381988741593174046</p>
      </div>

      <!-- Card 5: FX -->
      <div class="card short"
           data-id="1276210406880317522"
           data-fallback="FX"
           data-video="https://cdn.discordapp.com/attachments/1481125659840348264/1575484814180618331/snaptik_7593761866636168470_v3.mp4?ex=6b097412&is=6b082292&hm=536a503e2bef9415bdcdc5dd6551514725dd2c47580537aaeb5358463cf83b31&">
        <div class="image-box">
          <img src="https://cdn.discordapp.com/embed/avatars/4.png" alt="FX">
        </div>
        <h2 class="name">FX</h2>
        <p class="handle">@1276210406880317522</p>
      </div>
    </main>
  </div>

  <script>
    const introScreen = document.getElementById('intro-screen');
    const introLogoBtn = document.getElementById('introLogoBtn');
    const mainPage = document.getElementById('main-page');
    const starsLayer = document.getElementById('starsLayer');

    // Gumawa ng 150 na gumagalaw at kumukutitap na bituin
    const starCount = 150;
    for (let i = 0; i < starCount; i++) {
      const star = document.createElement('span');
      star.classList.add('star');

      const size = Math.random() * 2.6 + 1;
      const left = Math.random() * 100;
      const top = Math.random() * 115;
      const moveDuration = Math.random() * 18 + 12;
      const twinkleDuration = Math.random() * 3 + 1.5;
      const delay = -(Math.random() * moveDuration);

      star.style.width = `${size}px`;
      star.style.height = `${size}px`;
      star.style.left = `${left}vw`;
      star.style.top = `${top}vh`;
      star.style.animationDuration = `${moveDuration}s, ${twinkleDuration}s`;
      star.style.animationDelay = `${delay}s, ${delay}s`;

      starsLayer.appendChild(star);
    }

    // Diretsong Background Music Handler
    const bgMusic = document.getElementById('bg-music');
    bgMusic.volume = 0.4;
    bgMusic.muted = false;
    let isHoveringCard = false;

    async function startDirectMusic() {
      if (isHoveringCard) return;
      try {
        bgMusic.muted = false;
        await bgMusic.play();
      } catch (_) {}
    }

    // Kapag pinindot ang logo sa intro, lilipat sa next page at magsisimula ang music
    introLogoBtn.addEventListener('click', () => {
      introScreen.classList.add('hidden');
      mainPage.classList.remove('hidden');
      startDirectMusic();
    });

    // Hover Background Video + Click to Open Discord Profile
    const hoverVideo = document.getElementById('hover-video-bg');
    const hoverOverlay = document.getElementById('hover-video-overlay');
    const allCards = document.querySelectorAll('.card[data-id]');

    hoverVideo.muted = false;
    hoverVideo.volume = 1.0;

    allCards.forEach(card => {
      const userId = card.dataset.id;
      const videoUrl = card.dataset.video;

      // Kapag pinindot ang picture (o card), bubuksan ang Discord account nila
      card.addEventListener('click', () => {
        if (!userId) return;
        window.open(`https://discord.com/users/${userId}`, '_blank', 'noopener,noreferrer');
      });

      card.addEventListener('mouseenter', async () => {
        if (!videoUrl) return;
        isHoveringCard = true;

        bgMusic.muted = true;
        bgMusic.pause();

        if (hoverVideo.src !== videoUrl) {
          hoverVideo.src = videoUrl;
        }
        hoverVideo.currentTime = 0;
        hoverVideo.muted = false;

        hoverVideo.classList.add('active');
        hoverOverlay.classList.add('active');

        try {
          await hoverVideo.play();
        } catch (_) {}
      });

      card.addEventListener('mouseleave', async () => {
        isHoveringCard = false;

        hoverVideo.classList.remove('active');
        hoverOverlay.classList.remove('active');
        hoverVideo.pause();
        hoverVideo.currentTime = 0;

        bgMusic.muted = false;
        try {
          await bgMusic.play();
        } catch (_) {}
      });
    });

    // Lanyard Discord Sync
    async function syncDiscordProfiles() {
      const cards = document.querySelectorAll('.card[data-id]');

      for (const card of cards) {
        const userId = card.dataset.id;
        const fallbackName = card.dataset.fallback;
        const imgEl = card.querySelector('img');
        const nameEl = card.querySelector('.name');
        const handleEl = card.querySelector('.handle');

        try {
          const res = await fetch(`https://api.lanyard.rest/v1/users/${userId}`);
          const json = await res.json();

          if (json.success && json.data && json.data.discord_user) {
            const user = json.data.discord_user;

            const displayName = user.global_name || user.username || fallbackName;
            nameEl.textContent = displayName;
            handleEl.textContent = `@${user.username}`;
            imgEl.alt = displayName;

            if (user.avatar) {
              const ext = user.avatar.startsWith('a_') ? 'gif' : 'png';
              imgEl.src = `https://cdn.discordapp.com/avatars/${userId}/${user.avatar}.${ext}?size=512`;
            } else {
              const defaultIndex = (BigInt(userId) >> 22n) % 6n;
              imgEl.src = `https://cdn.discordapp.com/embed/avatars/${defaultIndex}.png`;
            }
          } else {
            nameEl.textContent = fallbackName;
          }
        } catch (err) {
          console.warn(`Failed to fetch Lanyard data for ${userId}:`, err);
          nameEl.textContent = fallbackName;
        }
      }
    }

    syncDiscordProfiles();
    setInterval(syncDiscordProfiles, 30000);
  </script>

</body>
</html>
