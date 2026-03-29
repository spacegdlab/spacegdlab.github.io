
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Артём | Liquid Glass Dev — Unity Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0c12;
            font-family: 'Space Grotesk', sans-serif;
            color: #eef5ff;
            line-height: 1.5;
            overflow-x: hidden;
        }

        /* animated liquid gradient background */
        .liquid-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: radial-gradient(circle at 20% 30%, #0d111c, #03050a);
        }

        .glass-orb {
            position: fixed;
            width: 70vw;
            height: 70vw;
            background: radial-gradient(circle, rgba(80, 180, 255, 0.2), rgba(0, 255, 255, 0.02));
            border-radius: 50%;
            filter: blur(80px);
            z-index: -1;
            animation: floatLiquid 18s infinite alternate ease-in-out;
        }

        .glass-orb2 {
            position: fixed;
            bottom: -20%;
            right: -10%;
            width: 60vw;
            height: 60vw;
            background: radial-gradient(circle, rgba(255, 80, 200, 0.15), rgba(0, 255, 255, 0.0));
            filter: blur(100px);
            z-index: -1;
            animation: floatLiquid2 22s infinite alternate;
        }

        @keyframes floatLiquid {
            0% { transform: translate(-5%, -5%) scale(1); opacity: 0.5; }
            100% { transform: translate(10%, 15%) scale(1.2); opacity: 0.8; }
        }
        @keyframes floatLiquid2 {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(-8%, -12%) scale(1.25); }
        }

        /* glass morphism card style */
        .glass-card {
            background: rgba(20, 25, 40, 0.45);
            backdrop-filter: blur(14px);
            border-radius: 2rem;
            border: 1px solid rgba(100, 210, 255, 0.25);
            box-shadow: 0 15px 35px rgba(0,0,0,0.2), inset 0 1px 0 rgba(255,255,255,0.05);
            transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
        }

        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 5;
        }

        /* hero */
        .hero {
            min-height: 90vh;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            text-align: center;
            gap: 1.5rem;
            padding: 4rem 0;
        }

        .liquid-badge {
            background: rgba(0, 255, 255, 0.08);
            backdrop-filter: blur(12px);
            padding: 0.5rem 1.2rem;
            border-radius: 60px;
            font-size: 0.8rem;
            font-weight: 500;
            letter-spacing: 1px;
            border: 1px solid rgba(0, 255, 255, 0.4);
            color: #8effff;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        h1 {
            font-size: clamp(3rem, 8vw, 5.5rem);
            font-weight: 600;
            line-height: 1.2;
            background: linear-gradient(135deg, #ffffff 20%, #88ddff 50%, #c084fc 80%);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.02em;
        }

        .glow-text {
            text-shadow: 0 0 12px rgba(0, 200, 255, 0.3);
        }

        .hero-desc {
            font-size: 1.15rem;
            max-width: 580px;
            color: #b9d0f5;
            font-weight: 300;
        }

        .btn-group {
            display: flex;
            gap: 1.2rem;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 1rem;
        }

        .btn-glass {
            padding: 0.85rem 2rem;
            border-radius: 48px;
            font-weight: 500;
            transition: all 0.25s ease;
            text-decoration: none;
            backdrop-filter: blur(8px);
        }
        .btn-primary-glass {
            background: rgba(0, 210, 255, 0.2);
            border: 1px solid rgba(0, 255, 255, 0.6);
            color: #0ff;
            box-shadow: 0 0 12px rgba(0, 200, 255, 0.2);
        }
        .btn-primary-glass:hover {
            background: #0ff;
            color: #0a0c12;
            border-color: #fff;
            box-shadow: 0 0 24px #0ff;
            transform: scale(1.02);
        }
        .btn-outline-glass {
            border: 1px solid rgba(255,255,255,0.3);
            background: rgba(255,255,255,0.02);
            color: #d9eaff;
        }
        .btn-outline-glass:hover {
            background: rgba(0, 255, 255, 0.1);
            border-color: #0ff;
            color: #0ff;
        }

        section {
            padding: 5rem 0;
        }

        .section-title {
            font-size: 2.2rem;
            font-weight: 500;
            letter-spacing: -0.3px;
            margin-bottom: 2rem;
            display: inline-block;
            background: linear-gradient(120deg, #fff, #aaffff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        /* filter chips */
        .filter-group {
            display: flex;
            gap: 0.8rem;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }
        .filter-chip {
            background: rgba(30, 40, 60, 0.5);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            padding: 0.5rem 1.4rem;
            border-radius: 40px;
            font-weight: 500;
            font-size: 0.85rem;
            cursor: pointer;
            transition: 0.2s;
            color: #ccf;
        }
        .filter-chip.active, .filter-chip:hover {
            background: rgba(0, 255, 255, 0.2);
            border-color: #0ff;
            color: white;
            box-shadow: 0 0 12px rgba(0,255,200,0.3);
        }

        /* project grid liquid glass cards */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(330px, 1fr));
            gap: 2rem;
        }

        .project-liquid {
            background: rgba(18, 24, 36, 0.5);
            backdrop-filter: blur(16px);
            border-radius: 2rem;
            overflow: hidden;
            border: 1px solid rgba(0, 255, 255, 0.2);
            transition: all 0.35s ease;
            cursor: pointer;
            transform: translateY(0);
        }
        .project-liquid:hover {
            transform: translateY(-8px);
            border-color: #0ff;
            box-shadow: 0 20px 35px -12px rgba(0, 200, 255, 0.25);
            background: rgba(25, 35, 55, 0.6);
        }
        .project-img {
            width: 100%;
            height: 220px;
            background-size: cover;
            background-position: center;
            transition: transform 0.5s ease;
        }
        .project-liquid:hover .project-img {
            transform: scale(1.03);
        }
        .project-info {
            padding: 1.5rem;
        }
        .project-tag {
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #7efff0;
            font-weight: 500;
        }
        .project-title {
            font-size: 1.5rem;
            font-weight: 500;
            margin: 0.5rem 0 0.4rem;
        }
        .project-desc {
            font-size: 0.85rem;
            color: #b7cef0;
            margin-bottom: 1rem;
        }
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }
        .tech-badge-glass {
            background: rgba(0, 255, 255, 0.1);
            padding: 0.2rem 0.8rem;
            border-radius: 30px;
            font-size: 0.7rem;
            font-weight: 400;
            backdrop-filter: blur(2px);
        }

        /* skills with liquid glass */
        .skills-glass {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            background: rgba(12, 20, 32, 0.4);
            backdrop-filter: blur(12px);
            border-radius: 2rem;
            padding: 2rem;
            border: 1px solid rgba(0, 255, 255, 0.2);
        }
        .skill-block {
            flex: 1;
        }
        .skill-block h3 {
            color: #6efff0;
            font-weight: 500;
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }
        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
        }
        .skill-pill {
            background: rgba(0, 212, 255, 0.08);
            border: 1px solid rgba(0, 255, 200, 0.3);
            padding: 0.35rem 1rem;
            border-radius: 30px;
            font-size: 0.8rem;
            font-weight: 400;
            backdrop-filter: blur(4px);
        }

        /* contact glass */
        .contact-glass {
            background: rgba(20, 28, 44, 0.4);
            backdrop-filter: blur(16px);
            border-radius: 2rem;
            padding: 2rem;
            text-align: center;
            border: 1px solid rgba(0, 255, 255, 0.25);
        }
        .contact-icons {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 1.5rem 0;
            flex-wrap: wrap;
        }
        .contact-icons a {
            color: #c0e0ff;
            font-size: 1.2rem;
            transition: 0.2s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        .contact-icons a:hover {
            color: #0ff;
            text-shadow: 0 0 8px cyan;
        }

        /* modal for screenshots */
        .glass-modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(20px);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            cursor: pointer;
        }
        .glass-modal.active {
            display: flex;
        }
        .modal-inner {
            max-width: 85vw;
            max-height: 85vh;
            border-radius: 2rem;
            border: 1px solid rgba(0, 255, 255, 0.5);
            overflow: hidden;
            box-shadow: 0 0 40px rgba(0, 200, 255, 0.3);
        }
        .modal-inner img {
            width: 100%;
            height: auto;
            display: block;
        }

        footer {
            text-align: center;
            padding: 2rem;
            font-size: 0.8rem;
            color: #8bb3dd;
            border-top: 1px solid rgba(0,255,255,0.1);
        }
        .scroll-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 48px;
            height: 48px;
            border-radius: 60px;
            background: rgba(0, 200, 255, 0.2);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(0,255,255,0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: 0.3s;
            pointer-events: none;
            z-index: 99;
            color: #0ff;
        }
        .scroll-top.visible {
            opacity: 1;
            pointer-events: auto;
        }

        @media (max-width: 700px) {
            .container { padding: 0 1.2rem; }
            .skills-glass { flex-direction: column; }
        }
    </style>
</head>
<body>
<div class="liquid-bg"></div>
<div class="glass-orb"></div>
<div class="glass-orb2"></div>

<div class="scroll-top" id="scrollTopBtn"><i class="fas fa-chevron-up"></i></div>

<div class="container">
    <div class="hero">
        <div class="liquid-badge">
            <i class="fas fa-droplet"></i> LIQUID GLASS / UNITY CRAFT
        </div>
        <h1>ИГРЫ <span class="glow-text">+<br>ПРИЛОЖЕНИЯ</span><br> НА UNITY</h1>
        <p class="hero-desc">Разработчик, превращающий идеи в текучие цифровые миры. 2 приложения, 3 игры — каждый проект дышит эстетикой и инновациями.</p>
        <div class="btn-group">
            <a href="#projects" class="btn-glass btn-primary-glass"><i class="fas fa-glasses"></i> Проекты</a>
            <a href="#contact" class="btn-glass btn-outline-glass"><i class="fas fa-paper-plane"></i> Контакт</a>
        </div>
    </div>

    <section id="projects">
        <h2 class="section-title">/ fluid portfolio</h2>
        <div class="filter-group">
            <button class="filter-chip active" data-filter="all">Все работы</button>
            <button class="filter-chip" data-filter="game">🎮 Игры (3)</button>
            <button class="filter-chip" data-filter="app">📱 Приложения (2)</button>
        </div>
        <div class="projects-grid" id="projectsGrid"></div>
    </section>

    <section id="skills">
        <h2 class="section-title">/ liquid toolset</h2>
        <div class="skills-glass">
            <div class="skill-block">
                <h3><i class="fab fa-unity"></i> Unity ecosystem</h3>
                <div class="skill-items">
                    <span class="skill-pill">C# / .NET</span>
                    <span class="skill-pill">URP/HDRP</span>
                    <span class="skill-pill">Unity DOTS</span>
                    <span class="skill-pill">Shaders Graph</span>
                    <span class="skill-pill">Timeline/Cinemachine</span>
                </div>
            </div>
            <div class="skill-block">
                <h3><i class="fas fa-mobile-alt"></i> Mobile & backend</h3>
                <div class="skill-items">
                    <span class="skill-pill">Firebase</span>
                    <span class="skill-pill">REST APIs</span>
                    <span class="skill-pill">AdMob / IronSource</span>
                    <span class="skill-pill">In-App Purchases</span>
                    <span class="skill-pill">Android/iOS</span>
                </div>
            </div>
            <div class="skill-block">
                <h3><i class="fas fa-crown"></i> Design patterns</h3>
                <div class="skill-items">
                    <span class="skill-pill">Zenject/DI</span>
                    <span class="skill-pill">MVVM/MVC</span>
                    <span class="skill-pill">Addressables</span>
                    <span class="skill-pill">Git LFS</span>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <h2 class="section-title">/ flow state contact</h2>
        <div class="contact-glass">
            <p style="font-size: 1.1rem; margin-bottom: 0.8rem;">Давайте создадим что-то текучее и мощное.</p>
            <div class="contact-icons">
                <a href="#"><i class="fab fa-telegram"></i> Telegram</a>
                <a href="#"><i class="fab fa-github"></i> GitHub</a>
                <a href="#"><i class="fas fa-envelope"></i> liquid.dev@unity.me</a>
            </div>
            <div><i class="fas fa-map-pin"></i> работаю удаленно по всему миру</div>
        </div>
    </section>
    <footer>
        <i class="fas fa-water"></i> liquid glass interface — разработчик игр и приложений на Unity
    </footer>
</div>

<div id="screenshotModal" class="glass-modal">
    <div class="modal-inner">
        <img id="modalImgSrc" src="" alt="project screenshot">
    </div>
</div>

<script>
    // Projects data: 3 games + 2 apps, with placeholder screenshots (replace with your own images)
    const portfolio = [
        { id: 1, title: "NEBULA ROGUE", category: "game", desc: "Космический roguelite с системой фрактальных улучшений, динамическими врагами и неоновой графикой.", tech: ["Unity 2022 LTS", "Shader Graph", "Addressables", "VFX Graph"], screenshot: "https://placehold.co/700x450/14222e/4affff?text=NEBULA+ROGUE+GAMEPLAY" },
        { id: 2, title: "ECHOES OF THE VOID", category: "game", desc: "Атмосферный платформер-головоломка, где звук отражается от стен и открывает новые пути.", tech: ["Cinemachine", "Post-processing", "Audio Mixer", "Tilemap"], screenshot: "https://placehold.co/700x450/1a2a36/6efff0?text=Echoes+of+the+Void+Art" },
        { id: 3, title: "CYBER DRIFT NEO", category: "game", desc: "Гоночный экшен на антигравитации, разрушаемое окружение, кибер-панк эстетика.", tech: ["Unity Physics", "Trail FX", "Odin Inspector", "UI Toolkit"], screenshot: "https://placehold.co/700x450/0e1c2c/0ff?text=Cyber+Drift+Neo+Speed" },
        { id: 4, title: "TASKFLOW GLASS", category: "app", desc: "Кроссплатформенный менеджер задач с живыми виджетами, аналитикой и синхронизацией.", tech: ["Firebase Firestore", "SQLite", "Unity UI Toolkit", "Native Plugins"], screenshot: "https://placehold.co/700x450/0f192b/8effff?text=TaskFlow+Glass+Interface" },
        { id: 5, title: "HEALTH AURA", category: "app", desc: "Фитнес-трекер с метриками сна, калорий и интеграцией с Wear OS, красивая визуализация.", tech: ["Google Fit API", "MPAndroidChart", "REST", "JWT"], screenshot: "https://placehold.co/700x450/111d2f/c0e0ff?text=Health+Aura+Mobile" }
    ];

    const grid = document.getElementById('projectsGrid');
    const modal = document.getElementById('screenshotModal');
    const modalImage = document.getElementById('modalImgSrc');

    function renderProjects(filter = 'all') {
        let filtered = portfolio;
        if (filter === 'game') filtered = portfolio.filter(p => p.category === 'game');
        if (filter === 'app') filtered = portfolio.filter(p => p.category === 'app');
        
        grid.innerHTML = filtered.map(proj => `
            <div class="project-liquid" data-id="${proj.id}" data-category="${proj.category}">
                <div class="project-img" style="background-image: url('${proj.screenshot}'); background-size: cover; background-position: center;"></div>
                <div class="project-info">
                    <div class="project-tag">${proj.category === 'game' ? '✦ ИГРА ✦' : '✦ ПРИЛОЖЕНИЕ ✦'}</div>
                    <div class="project-title">${proj.title}</div>
                    <div class="project-desc">${proj.desc}</div>
                    <div class="tech-stack">
                        ${proj.tech.map(t => `<span class="tech-badge-glass">${t}</span>`).join('')}
                    </div>
                </div>
            </div>
        `).join('');

        // Attach click event for modal on each new card
        document.querySelectorAll('.project-liquid').forEach(card => {
            card.addEventListener('click', (e) => {
                e.stopPropagation();
                const id = parseInt(card.getAttribute('data-id'));
                const project = portfolio.find(p => p.id === id);
                if (project) {
                    modalImage.src = project.screenshot;
                    modal.classList.add('active');
                }
            });
        });
    }

    // Filter logic
    const filterChips = document.querySelectorAll('.filter-chip');
    filterChips.forEach(chip => {
        chip.addEventListener('click', () => {
            filterChips.forEach(c => c.classList.remove('active'));
            chip.classList.add('active');
            const filterValue = chip.getAttribute('data-filter');
            renderProjects(filterValue);
        });
    });

    // Close modal on click
    modal.addEventListener('click', () => {
        modal.classList.remove('active');
        modalImage.src = '';
    });

    // Scroll to top button
    const scrollBtn = document.getElementById('scrollTopBtn');
    window.addEventListener('scroll', () => {
        if (window.scrollY > 400) scrollBtn.classList.add('visible');
        else scrollBtn.classList.remove('visible');
    });
    scrollBtn.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

    // Smooth anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            const targetId = this.getAttribute('href');
            if (targetId === "#" || targetId === "") return;
            const targetEl = document.querySelector(targetId);
            if (targetEl) {
                e.preventDefault();
                targetEl.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });
    });

    // Fade-in animation on scroll for glass cards
    const fadeElements = document.querySelectorAll('.project-liquid, .skill-block, .contact-glass');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.style.opacity = '1';
                entry.target.style.transform = 'translateY(0)';
                observer.unobserve(entry.target);
            }
        });
    }, { threshold: 0.1, rootMargin: "0px 0px -30px 0px" });
    fadeElements.forEach(el => {
        el.style.opacity = '0';
        el.style.transform = 'translateY(18px)';
        el.style.transition = 'opacity 0.6s ease, transform 0.5s ease';
        observer.observe(el);
    });
    
    // initial render
    renderProjects('all');

    // tiny extra glassmorphic effect on hover for buttons 
    console.log("✨ Liquid Glass portfolio ready — replace placeholders with real game/app screenshots!");
</script>
</body>
</html>
