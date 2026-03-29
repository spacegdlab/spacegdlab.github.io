<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Артём Разработчик | Unity Portfolio</title>
    <!-- Google Fonts & Smooth Scroll -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #050b14;
            font-family: 'Inter', sans-serif;
            color: #eef5ff;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        /* custom cursor glow */
        .cursor-glow {
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 255, 255, 0.08) 0%, rgba(0, 255, 255, 0) 70%);
            position: fixed;
            pointer-events: none;
            border-radius: 50%;
            z-index: 999;
            transform: translate(-50%, -50%);
            transition: transform 0.05s linear;
            will-change: transform;
        }

        /* container */
        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 2;
        }

        /* header / hero */
        .hero {
            min-height: 90vh;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            text-align: center;
            gap: 1.2rem;
            padding: 4rem 0;
        }

        .badge {
            background: rgba(0, 255, 255, 0.12);
            backdrop-filter: blur(4px);
            padding: 0.5rem 1.2rem;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            border: 1px solid rgba(0, 255, 255, 0.3);
            color: #0ff;
            display: inline-block;
        }

        h1 {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff, #0ff, #aaffff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            line-height: 1.2;
        }

        .highlight {
            color: #0ff;
            text-shadow: 0 0 8px rgba(0, 255, 255, 0.5);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            color: #b0c7e9;
        }

        .btn-group {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 1rem;
        }

        .btn {
            padding: 0.9rem 2rem;
            border-radius: 60px;
            font-weight: 600;
            transition: all 0.3s ease;
            text-decoration: none;
            font-size: 1rem;
        }

        .btn-primary {
            background: #0ff;
            color: #050b14;
            box-shadow: 0 0 12px rgba(0, 255, 255, 0.4);
        }

        .btn-primary:hover {
            background: #fff;
            box-shadow: 0 0 22px #0ff;
            transform: scale(1.02);
        }

        .btn-outline {
            border: 1px solid #0ff;
            color: #0ff;
            background: transparent;
        }

        .btn-outline:hover {
            background: rgba(0, 255, 255, 0.1);
            transform: scale(1.02);
        }

        /* section styles */
        section {
            padding: 5rem 0;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
        }
        .section-title:after {
            content: '';
            position: absolute;
            bottom: -12px;
            left: 0;
            width: 60%;
            height: 3px;
            background: linear-gradient(90deg, #0ff, transparent);
        }

        /* фильтры и проекты */
        .filter-bar {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }
        .filter-btn {
            background: rgba(20, 40, 60, 0.6);
            border: none;
            padding: 0.6rem 1.6rem;
            border-radius: 40px;
            color: #ccdeff;
            font-weight: 500;
            cursor: pointer;
            transition: 0.2s;
            backdrop-filter: blur(5px);
        }
        .filter-btn.active, .filter-btn:hover {
            background: #0ff;
            color: #050b14;
            box-shadow: 0 0 12px #0ff;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: rgba(12, 22, 35, 0.75);
            backdrop-filter: blur(12px);
            border-radius: 28px;
            overflow: hidden;
            border: 1px solid rgba(0, 255, 255, 0.2);
            transition: all 0.35s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            cursor: pointer;
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
        }
        .project-card:hover {
            transform: translateY(-10px);
            border-color: #0ff;
            box-shadow: 0 25px 40px rgba(0, 255, 255, 0.2);
        }
        .card-img {
            width: 100%;
            height: 210px;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            position: relative;
            transition: transform 0.4s;
        }
        .project-card:hover .card-img {
            transform: scale(1.02);
        }
        .card-content {
            padding: 1.5rem;
        }
        .project-category {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #0ff;
            font-weight: 600;
        }
        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin: 0.5rem 0 0.5rem;
        }
        .project-desc {
            color: #b9d0f0;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }
        .tech-badge {
            display: inline-block;
            background: rgba(0, 255, 255, 0.1);
            border-radius: 20px;
            padding: 0.2rem 0.8rem;
            font-size: 0.7rem;
            font-weight: 500;
            margin-right: 0.5rem;
            margin-top: 0.5rem;
        }

        /* about / skills */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: space-between;
            background: rgba(0, 20, 30, 0.4);
            border-radius: 32px;
            padding: 2rem;
            border: 1px solid rgba(0,255,255,0.15);
        }
        .skill-cat {
            flex: 1;
        }
        .skill-cat h3 {
            color: #0ff;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }
        .skill-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.7rem;
        }
        .skill-tag {
            background: #0a1824;
            padding: 0.4rem 1rem;
            border-radius: 30px;
            font-size: 0.85rem;
            font-weight: 500;
            border-left: 2px solid #0ff;
        }

        /* модалка увеличенный скрин */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.9);
            backdrop-filter: blur(12px);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            cursor: pointer;
        }
        .modal.active {
            display: flex;
        }
        .modal-content {
            max-width: 85vw;
            max-height: 85vh;
            border-radius: 32px;
            border: 2px solid #0ff;
            box-shadow: 0 0 40px #0ff;
        }
        .modal-content img {
            width: 100%;
            height: auto;
            border-radius: 28px;
            object-fit: contain;
        }

        footer {
            text-align: center;
            padding: 2rem;
            border-top: 1px solid rgba(0,255,255,0.2);
            font-size: 0.85rem;
            color: #7f9fcf;
        }
        @media (max-width: 700px) {
            .container { padding: 0 1.2rem; }
            .projects-grid { grid-template-columns: 1fr; }
            .skills-container { flex-direction: column; }
        }
        .scroll-to-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: #0ff;
            width: 48px;
            height: 48px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #050b14;
            font-size: 1.5rem;
            cursor: pointer;
            opacity: 0;
            transition: 0.3s;
            pointer-events: none;
            z-index: 99;
            box-shadow: 0 0 12px #0ff;
        }
        .scroll-to-top.visible {
            opacity: 1;
            pointer-events: auto;
        }
    </style>
</head>
<body>

<div class="cursor-glow" id="cursorGlow"></div>
<div class="scroll-to-top" id="scrollTopBtn"><i class="fas fa-arrow-up"></i></div>

<div class="container">
    <!-- HERO SECTION -->
    <div class="hero">
        <div class="badge"><i class="fas fa-cube"></i> UNITY DEVELOPER · GAMES & APPS</div>
        <h1>ИГРЫ <span class="highlight">+ ПРИЛОЖЕНИЯ</span><br> НА UNITY</h1>
        <p>Создаю цифровой опыт, где код встречается с искусством. 2 приложения, 3 игры — каждый проект заряжен душой и технологиями.</p>
        <div class="btn-group">
            <a href="#projects" class="btn btn-primary"><i class="fas fa-rocket"></i> Смотреть проекты</a>
            <a href="#contact" class="btn btn-outline"><i class="fas fa-paper-plane"></i> Связаться</a>
        </div>
    </div>

    <!-- PROJECTS SECTION с фильтрацией (2 приложения, 3 игры) -->
    <section id="projects">
        <h2 class="section-title">Портфолио проектов</h2>
        <div class="filter-bar">
            <button class="filter-btn active" data-filter="all">Всё</button>
            <button class="filter-btn" data-filter="game">Игры (3)</button>
            <button class="filter-btn" data-filter="app">Приложения (2)</button>
        </div>
        <div class="projects-grid" id="projectsGrid"></div>
    </section>

    <!-- ОБО МНЕ + СКИЛЛЫ -->
    <section id="about">
        <h2 class="section-title">Технологический стек</h2>
        <div class="skills-container">
            <div class="skill-cat">
                <h3><i class="fab fa-unity"></i> Core</h3>
                <div class="skill-list">
                    <span class="skill-tag">Unity 3D/2D</span>
                    <span class="skill-tag">C#</span>
                    <span class="skill-tag">Unity UI</span>
                    <span class="skill-tag">Animation</span>
                    <span class="skill-tag">Shaders</span>
                </div>
            </div>
            <div class="skill-cat">
                <h3><i class="fas fa-mobile-alt"></i> Мобильные</h3>
                <div class="skill-list">
                    <span class="skill-tag">Android/iOS Build</span>
                    <span class="skill-tag">Firebase</span>
                    <span class="skill-tag">Ads Integration</span>
                    <span class="skill-tag">In-App Purchases</span>
                </div>
            </div>
            <div class="skill-cat">
                <h3><i class="fas fa-code-branch"></i> Инструменты</h3>
                <div class="skill-list">
                    <span class="skill-tag">Git</span>
                    <span class="skill-tag">Blender</span>
                    <span class="skill-tag">Photoshop</span>
                    <span class="skill-tag">Zenject</span>
                </div>
            </div>
        </div>
    </section>

    <!-- КОНТАКТ -->
    <section id="contact">
        <h2 class="section-title">Давайте создадим что-то мощное</h2>
        <div style="background: rgba(0,20,30,0.5); border-radius: 32px; padding: 2rem; margin-top: 1rem; text-align: center;">
            <p style="font-size: 1.2rem; margin-bottom: 1.5rem;">Всегда открыт для сотрудничества и крутых идей.</p>
            <div style="display: flex; gap: 1.8rem; justify-content: center; flex-wrap: wrap;">
                <a href="#" style="color:#0ff; font-size: 1.2rem;"><i class="fab fa-telegram"></i> Telegram</a>
                <a href="#" style="color:#0ff; font-size: 1.2rem;"><i class="fab fa-github"></i> GitHub</a>
                <a href="#" style="color:#0ff; font-size: 1.2rem;"><i class="fas fa-envelope"></i> dev@unitymaster.ru</a>
            </div>
            <div style="margin-top: 2rem;">
                <i class="fas fa-map-marker-alt"></i> Работаю удаленно по всему миру
            </div>
        </div>
    </section>
    <footer>
        <i class="fas fa-crown"></i> Разработчик игр и приложений на Unity — 2025 · всё сделано с душой
    </footer>
</div>

<!-- Modal для просмотра скринов -->
<div id="screenshotModal" class="modal">
    <div class="modal-content">
        <img id="modalImage" src="" alt="screenshot preview">
    </div>
</div>

<script>
    // ========= ДАННЫЕ ПРОЕКТОВ (2 приложения, 3 игры) =========
    const projectsData = [
        { // игра 1
            id: 1,
            title: "Starfall Rogue",
            category: "game",
            desc: "Космический roguelite шутер с процедурной генерацией уровней, мощной системой апгрейдов и неоновой графикой.",
            tech: ["Unity", "C#", "Shader Graph", "Addressables"],
            screenshot: "https://placehold.co/600x400/0a1a2a/0ff?text=Starfall+Rogue+Gameplay" // Замените на реальный скриншот игры
        },
        { // игра 2
            id: 2,
            title: "Echoes of Abyss",
            category: "game",
            desc: "Атмосферный платформер-головоломка с уникальной механикой эха. Более 10 уровней, сюжетная линия.",
            tech: ["Unity", "Cinemachine", "Post-Processing", "Tilemap"],
            screenshot: "https://placehold.co/600x400/0e1e2e/0ff?text=Echoes+of+Abyss+Art" 
        },
        { // игра 3
            id: 3,
            title: "Cyber Drift",
            category: "game",
            desc: "Гоночный аркада-шутер на антигравитационных машинах. Уничтожай врагов и дрифтуй в киберпространстве.",
            tech: ["Unity Physics", "Trail Renderer", "UI Toolkit", "Odin"],
            screenshot: "https://placehold.co/600x400/0c1c2c/0ff?text=Cyber+Drift+Neon+Speed" 
        },
        { // приложение 1
            id: 4,
            title: "TaskFlow Organizer",
            category: "app",
            desc: "Кроссплатформенный менеджер задач с синхронизацией, кастомными тегами и аналитикой продуктивности.",
            tech: ["Unity UI", "SQLite", "Firebase", "Native Plugins"],
            screenshot: "https://placehold.co/600x400/0b1b2b/0ff?text=TaskFlow+App+Interface" 
        },
        { // приложение 2
            id: 5,
            title: "HealthSync",
            category: "app",
            desc: "Фитнес-трекер с графиками активности, интеграцией с Google Fit и напоминаниями. Поддержка Wear OS.",
            tech: ["Unity", "REST API", "Android SDK", "Data Visualization"],
            screenshot: "https://placehold.co/600x400/09192a/0ff?text=HealthSync+Mobile+Stats" 
        }
    ];

    // Функция отрисовки карточек с фильтрацией
    const projectsGrid = document.getElementById('projectsGrid');
    
    function renderProjects(filter = 'all') {
        let filtered = projectsData;
        if (filter === 'game') {
            filtered = projectsData.filter(p => p.category === 'game');
        } else if (filter === 'app') {
            filtered = projectsData.filter(p => p.category === 'app');
        }
        if (projectsGrid) {
            projectsGrid.innerHTML = filtered.map(project => `
                <div class="project-card" data-id="${project.id}" data-category="${project.category}">
                    <div class="card-img" style="background-image: url('${project.screenshot}'); background-size: cover; background-position: center;"></div>
                    <div class="card-content">
                        <div class="project-category">${project.category === 'game' ? '🎮 ИГРА' : '📱 ПРИЛОЖЕНИЕ'}</div>
                        <div class="project-title">${project.title}</div>
                        <div class="project-desc">${project.desc}</div>
                        <div>
                            ${project.tech.map(t => `<span class="tech-badge">${t}</span>`).join('')}
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // добавить обработчики кликов по карточкам (открытие модалки с полным скрином)
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('click', (e) => {
                // не открывать модалку если кликнули на tech-badge или внутреннюю ссылку (но это не ссылка)
                e.stopPropagation();
                const projectId = parseInt(card.getAttribute('data-id'));
                const project = projectsData.find(p => p.id === projectId);
                if (project) {
                    openModalWithImage(project.screenshot, project.title);
                }
            });
        });
    }

    // функция модального окна с увеличенным скриншотом
    const modal = document.getElementById('screenshotModal');
    const modalImg = document.getElementById('modalImage');
    function openModalWithImage(src, title) {
        modalImg.src = src;
        modalImg.alt = title || 'screenshot';
        modal.classList.add('active');
    }
    function closeModal() {
        modal.classList.remove('active');
        modalImg.src = '';
    }
    modal.addEventListener('click', closeModal);

    // фильтрация кнопки
    const filterBtns = document.querySelectorAll('.filter-btn');
    filterBtns.forEach(btn => {
        btn.addEventListener('click', () => {
            filterBtns.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            const filterValue = btn.getAttribute('data-filter');
            renderProjects(filterValue);
        });
    });

    // инициализация всех проектов
    renderProjects('all');

    // доп эффекты: плавный скролл и кастомный курсор
    const glow = document.getElementById('cursorGlow');
    if (glow) {
        document.addEventListener('mousemove', (e) => {
            glow.style.left = e.clientX + 'px';
            glow.style.top = e.clientY + 'px';
        });
    }

    // Scroll to top button
    const scrollBtn = document.getElementById('scrollTopBtn');
    window.addEventListener('scroll', () => {
        if (window.scrollY > 400) {
            scrollBtn.classList.add('visible');
        } else {
            scrollBtn.classList.remove('visible');
        }
    });
    scrollBtn.addEventListener('click', () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Плавный переход по якорям
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            const href = this.getAttribute('href');
            if (href === "#" || href === "") return;
            const target = document.querySelector(href);
            if (target) {
                e.preventDefault();
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });
    });

    // Добавляем hover-эффект карточкам и динамический фон
    // небольшая анимация появления элементов
    const observerOptions = { threshold: 0.1, rootMargin: "0px 0px -20px 0px" };
    const fadeObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.style.opacity = '1';
                entry.target.style.transform = 'translateY(0)';
                fadeObserver.unobserve(entry.target);
            }
        });
    }, observerOptions);
    document.querySelectorAll('.project-card, .skill-cat, .skills-container').forEach(el => {
        el.style.opacity = '0';
        el.style.transform = 'translateY(18px)';
        el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
        fadeObserver.observe(el);
    });
    // hero элементы сразу видимые
    document.querySelectorAll('.hero .badge, .hero h1, .hero p, .btn-group').forEach(el => {
        el.style.opacity = '1';
        el.style.transform = 'translateY(0)';
    });
    // при нажатии на кнопки дополнительно подсветка
    console.log("🚀 АХУЕННЫЙ сайт-резюме готов! Используй реальные скриншоты вместо placeholder.");
</script>

<!-- Инструкция по замене изображений: 
     В объекте projectsData массив screenshot: замени ссылки на реальные пути к скринам твоих игр и приложений.
     Рекомендуется использовать изображения размером ~800x500 в формате webp/jpg.
-->
</body>
</html>
