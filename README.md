<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Био Алекса</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #e0e0e0;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            min-height: 100vh;
            padding: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
        }

        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 1rem;
            min-height: 100vh;
        }

        header {
            text-align: center;
            margin-bottom: 2rem;
            color: white;
            padding: 0 0.5rem;
        }

        h1 {
            font-size: clamp(1.8rem, 6vw, 3rem);
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            color: #ffffff;
            font-weight: 700;
        }

        .subtitle {
            font-size: clamp(0.9rem, 3.5vw, 1.2rem);
            opacity: 0.9;
            color: #b0b0b0;
            line-height: 1.4;
        }

        /* Основной контент */
        .content-wrapper {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            background: #1a1a1a;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 4px 20px rgba(0,0,0,0.4);
            border: 1px solid #333;
            margin: 0 auto;
            max-width: 600px;
        }

        /* Панель кнопок */
        .button-panel {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.8rem;
            width: 100%;
        }

        .theme-btn {
            padding: 14px 16px;
            border: none;
            border-radius: 10px;
            background: linear-gradient(135deg, #2a0a0a, #1a0a0a);
            color: #e0e0e0;
            font-size: clamp(0.9rem, 3.5vw, 1rem);
            cursor: pointer;
            transition: all 0.2s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
            border: 1px solid #500;
            font-weight: 500;
            touch-action: manipulation;
            min-height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .theme-btn:active {
            transform: scale(0.96);
            box-shadow: 0 0 15px rgba(200, 0, 0, 0.5);
            background: linear-gradient(135deg, #3a0a0a, #2a0a0a);
        }

        .theme-btn.active {
            background: linear-gradient(135deg, #500, #300);
            border-left: 3px solid #c00;
            box-shadow: 0 0 10px rgba(200, 0, 0, 0.4);
        }

        .profile-btn {
            background: linear-gradient(135deg, #400, #200);
            grid-column: 1 / -1;
            font-weight: 600;
            margin-top: 0.5rem;
        }

        .profile-btn:active {
            background: linear-gradient(135deg, #500, #300);
        }

        .channel-btn {
            background: linear-gradient(135deg, #600, #400);
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            max-width: 200px;
            margin-top: 1rem;
        }

        .channel-btn:active {
            background: linear-gradient(135deg, #700, #500);
        }

        /* Область с текстом */
        .text-display {
            background: #1a0a0a;
            border-radius: 10px;
            padding: 1.5rem;
            min-height: 300px;
            border-left: 3px solid #c00;
            position: relative;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.5);
        }

        .text-content {
            opacity: 0;
            transform: translateY(15px);
            transition: all 0.4s ease;
            position: absolute;
            width: calc(100% - 3rem);
            top: 1.5rem;
        }

        .text-content.active {
            opacity: 1;
            transform: translateY(0);
            position: relative;
        }

        .text-content h2 {
            color: #ffffff;
            margin-bottom: 1rem;
            font-size: clamp(1.3rem, 5vw, 1.8rem);
            text-shadow: 1px 1px 2px rgba(200,0,0,0.3);
            font-weight: 600;
        }

        .text-content p {
            margin-bottom: 1rem;
            font-size: clamp(0.95rem, 3.5vw, 1.1rem);
            line-height: 1.6;
        }

        .highlight {
            background: linear-gradient(120deg, #500 0%, #700 100%);
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            font-weight: 600;
            color: #fff;
            text-shadow: 1px 1px 1px rgba(0,0,0,0.3);
        }

        /* Дополнительные стили */
        .feature-list {
            list-style: none;
            margin: 1rem 0;
        }

        .feature-list li {
            padding: 0.5rem 0;
            border-bottom: 1px solid #400;
            position: relative;
            padding-left: 1.5rem;
            font-size: clamp(0.9rem, 3.5vw, 1rem);
        }

        .feature-list li:before {
            content: "►";
            color: #c00;
            font-weight: bold;
            position: absolute;
            left: 0;
            font-size: 0.8rem;
        }

        /* Специальные стили для Telegram */
        .tg-mobile .container {
            padding: 0.5rem;
        }

        .tg-mobile .content-wrapper {
            padding: 1rem;
            gap: 1rem;
        }

        .tg-mobile .text-display {
            padding: 1rem;
            min-height: 250px;
        }

        /* Адаптивность для очень маленьких экранов */
        @media (max-width: 360px) {
            .container {
                padding: 0.5rem;
            }
            
            .content-wrapper {
                padding: 1rem;
                border-radius: 10px;
            }
            
            .button-panel {
                grid-template-columns: 1fr;
                gap: 0.6rem;
            }
            
            .theme-btn {
                padding: 12px 14px;
                min-height: 45px;
                font-size: 0.9rem;
            }
            
            .text-display {
                padding: 1rem;
                min-height: 200px;
            }
            
            .text-content {
                width: calc(100% - 2rem);
            }
        }

        /* Планшеты и десктоп */
        @media (min-width: 768px) {
            .container {
                padding: 2rem;
                display: flex;
                flex-direction: column;
                justify-content: center;
                max-width: 800px;
            }
            
            .content-wrapper {
                display: grid;
                grid-template-columns: 1fr 2fr;
                gap: 2rem;
                max-width: 100%;
            }
            
            .button-panel {
                grid-template-columns: 1fr;
                gap: 1rem;
            }
            
            .theme-btn:hover {
                transform: translateX(5px);
                box-shadow: 0 5px 15px rgba(200, 0, 0, 0.3);
                background: linear-gradient(135deg, #3a0a0a, #2a0a0a);
            }
            
            .theme-btn.active:hover {
                transform: translateX(5px);
            }
            
            .profile-btn:hover {
                background: linear-gradient(135deg, #500, #300);
            }
            
            .channel-btn:hover {
                background: linear-gradient(135deg, #700, #500);
            }
        }

        /* Поддержка безопасных зон (iPhone X и новее) */
        @supports(padding: max(0px)) {
            .container {
                padding-left: max(1rem, env(safe-area-inset-left));
                padding-right: max(1rem, env(safe-area-inset-right));
                padding-bottom: max(1rem, env(safe-area-inset-bottom));
            }
        }

        a {
            color: #e0e0e0;
            text-decoration: none;
            display: block;
        }

        /* Улучшения для производительности */
        .theme-btn, .text-display {
            will-change: transform;
            backface-visibility: hidden;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Био Алекса</h1>
            <p class="subtitle">Информация о моей деятельности и проектах</p>
        </header>

        <div class="content-wrapper">
            <!-- Панель с кнопками -->
            <div class="button-panel">
                <button class="theme-btn active" data-tab="main">Главная</button>
                <button class="theme-btn" data-tab="about">Обо мне</button>
                <button class="theme-btn" data-tab="projects">Проекты</button>
                <a href="https://t.me/AlOsint" target="_blank" class="theme-btn profile-btn">Профиль</a>
            </div>

            <!-- Область отображения текста -->
            <div class="text-display">
                <!-- Главная -->
                <div class="text-content active" id="main-content">
                    <h2>Привет! 👋</h2>
                    <p>Я <span class="highlight">Алекс</span>, расскажу вам здесь немного о себе, кто я и в какой сфере работаю.</p>
                    <p>Занимаюсь различными IT-направлениями, но основная специализация - кибербезопасность и веб-разработка.</p>
                </div>

                <!-- Обо мне -->
                <div class="text-content" id="about-content">
                    <h2>Обо мне ✓</h2>
                    <p>Я работаю в сфере <span class="highlight">кибер безопасности</span>, пишу сайты и разные программы, также продаю различные услуги</p>
                </div>

                <!-- Проекты -->
                <div class="text-content" id="projects-content">
                    <h2>Мои проекты</h2>
                    <p>Наш проект <span class="highlight">Help</span> помогает людям и спасает их от доксинга и также мы устраиваем розыгрыши.</p>
                    <a href="https://t.me/+MNumg_FmEe9jYmMy" target="_blank" class="theme-btn channel-btn">Channel</a>
                </div>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const buttons = document.querySelectorAll('.theme-btn');
            const textContents = document.querySelectorAll('.text-content');
            
            // Определяем, открыто ли в Telegram
            function detectTelegram() {
                const userAgent = navigator.userAgent.toLowerCase();
                if (userAgent.includes('telegram') || userAgent.includes('webview')) {
                    document.body.classList.add('tg-mobile');
                }
                
                // Добавляем класс для iPhone X и новее
                if (/iPhone/.test(navigator.userAgent) && !/Safari/.test(navigator.userAgent)) {
                    document.body.classList.add('tg-ios');
                }
            }
            
            function switchContent(tabName) {
                buttons.forEach(btn => {
                    if (btn.getAttribute('data-tab')) {
                        btn.classList.remove('active');
                    }
                });
                
                textContents.forEach(content => {
                    content.classList.remove('active');
                    content.style.opacity = '0';
                    content.style.transform = 'translateY(15px)';
                });
                
                const activeBtn = document.querySelector(`[data-tab="${tabName}"]`);
                if (activeBtn) {
                    activeBtn.classList.add('active');
                    
                    // Эффект нажатия для тактильной обратной связи
                    activeBtn.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        activeBtn.style.transform = '';
                    }, 150);
                }
                
                const activeContent = document.getElementById(`${tabName}-content`);
                setTimeout(() => {
                    activeContent.classList.add('active');
                    activeContent.style.opacity = '1';
                    activeContent.style.transform = 'translateY(0)';
                }, 50);
            }
            
            buttons.forEach(button => {
                if (button.getAttribute('data-tab')) {
                    // Используем touchstart для лучшей отзывчивости на мобильных
                    button.addEventListener('touchstart', function(e) {
                        e.preventDefault();
                        const tabName = this.getAttribute('data-tab');
                        switchContent(tabName);
                    }, { passive: false });
                    
                    button.addEventListener('click', function() {
                        const tabName = this.getAttribute('data-tab');
                        switchContent(tabName);
                    });
                }
            });
            
            // Предзагрузка для улучшения производительности
            function preloadContent() {
                textContents.forEach(content => {
                    content.style.willChange = 'transform, opacity';
                });
            }
            
            // Инициализация
            detectTelegram();
            preloadContent();
            
            // Оптимизация для медленных устройств
            if (navigator.hardwareConcurrency && navigator.hardwareConcurrency <= 4) {
                document.body.classList.add('low-performance');
            }
        });
        
        // Предотвращаем масштабирование при двойном тапе
        let lastTouchEnd = 0;
        document.addEventListener('touchend', function (event) {
            const now = (new Date()).getTime();
            if (now - lastTouchEnd <= 300) {
                event.preventDefault();
            }
            lastTouchEnd = now;
        }, false);
    </script>
</body>
</html>