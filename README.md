<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Био Алекса</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #e0e0e0;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        header {
            text-align: center;
            margin-bottom: 3rem;
            color: white;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            color: #ffffff;
        }

        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            color: #b0b0b0;
        }

        /* Основной контент */
        .content-wrapper {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            background: #1a1a1a;
            border-radius: 15px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.4);
            border: 1px solid #333;
        }

        /* Панель кнопок */
        .button-panel {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .button-panel.horizontal {
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: center;
        }

        .theme-btn {
            padding: 15px 20px;
            border: none;
            border-radius: 8px;
            background: linear-gradient(135deg, #2a0a0a, #1a0a0a);
            color: #e0e0e0;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: left;
            position: relative;
            overflow: hidden;
            border: 1px solid #500;
            flex: 1;
            min-width: 150px;
        }

        .button-panel.horizontal .theme-btn {
            text-align: center;
            flex: 1;
            min-width: 120px;
        }

        .theme-btn:active {
            transform: scale(0.98);
            box-shadow: 0 0 15px rgba(200, 0, 0, 0.5);
            background: linear-gradient(135deg, #3a0a0a, #2a0a0a);
        }

        .theme-btn:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(200, 0, 0, 0.3);
            background: linear-gradient(135deg, #3a0a0a, #2a0a0a);
        }

        .button-panel.horizontal .theme-btn:hover {
            transform: translateY(-5px);
        }

        .theme-btn.active {
            background: linear-gradient(135deg, #500, #300);
            transform: translateX(10px);
            border-left: 4px solid #c00;
            box-shadow: 0 0 10px rgba(200, 0, 0, 0.4);
        }

        .button-panel.horizontal .theme-btn.active {
            transform: translateY(-5px);
            border-left: 1px solid #500;
            border-bottom: 4px solid #c00;
        }

        .profile-btn {
            background: linear-gradient(135deg, #400, #200);
            margin-top: 1rem;
            text-align: center;
            font-weight: bold;
        }

        .profile-btn:hover {
            background: linear-gradient(135deg, #500, #300);
        }

        .channel-btn {
            background: linear-gradient(135deg, #600, #400);
            margin-top: 1rem;
            text-align: center;
            font-weight: bold;
            display: inline-block;
            width: 200px;
        }

        .channel-btn:hover {
            background: linear-gradient(135deg, #700, #500);
        }

        /* Область с текстом */
        .text-display {
            background: #1a0a0a;
            border-radius: 10px;
            padding: 2rem;
            min-height: 400px;
            border-left: 4px solid #c00;
            position: relative;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.5);
        }

        .text-content {
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
            position: absolute;
            width: calc(100% - 4rem);
        }

        .text-content.active {
            opacity: 1;
            transform: translateY(0);
            position: relative;
        }

        .text-content h2 {
            color: #ffffff;
            margin-bottom: 1rem;
            font-size: 1.8rem;
            text-shadow: 1px 1px 2px rgba(200,0,0,0.3);
        }

        .text-content p {
            margin-bottom: 1rem;
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .highlight {
            background: linear-gradient(120deg, #500 0%, #700 100%);
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            font-weight: bold;
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
        }

        .feature-list li:before {
            content: "►";
            color: #c00;
            font-weight: bold;
            position: absolute;
            left: 0;
        }

        /* Адаптивность */
        @media (min-width: 769px) {
            .content-wrapper {
                display: grid;
                grid-template-columns: 1fr 2fr;
                gap: 2rem;
            }
        }

        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .button-panel {
                flex-direction: row;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .theme-btn {
                text-align: center;
                flex: 1;
                min-width: 120px;
            }
            
            .theme-btn:hover {
                transform: translateY(-5px);
            }
            
            .theme-btn.active {
                transform: translateY(-5px);
                border-left: 1px solid #500;
                border-bottom: 4px solid #c00;
            }
            
            .text-display {
                padding: 1.5rem;
                min-height: 350px;
            }
            
            .text-content h2 {
                font-size: 1.5rem;
            }
            
            .text-content p {
                font-size: 1rem;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .subtitle {
                font-size: 1rem;
            }
            
            .content-wrapper {
                padding: 1.5rem;
            }
            
            .theme-btn {
                padding: 12px 15px;
                font-size: 0.9rem;
                min-width: 100px;
            }
            
            .text-display {
                padding: 1rem;
                min-height: 300px;
            }
            
            .text-content h2 {
                font-size: 1.3rem;
            }
            
            .text-content p {
                font-size: 0.95rem;
            }
        }

        a {
            color: #e0e0e0;
            text-decoration: none;
            display: block;
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
                    <p>Я работаю в сфере <span class="highlight">кибер безопасности</span>, пишу сайты и разные программы, также продаю различные услуги которые вы можете узнать в личных сообщениях</p>
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
            
            function switchContent(tabName) {
                buttons.forEach(btn => btn.classList.remove('active'));
                textContents.forEach(content => {
                    content.classList.remove('active');
                    content.style.opacity = '0';
                    content.style.transform = 'translateY(20px)';
                });
                
                const activeBtn = document.querySelector(`[data-tab="${tabName}"]`);
                if (activeBtn) {
                    activeBtn.classList.add('active');
                    
                    // Добавляем эффект подсветки при нажатии
                    activeBtn.style.boxShadow = '0 0 20px rgba(255, 0, 0, 0.7)';
                    setTimeout(() => {
                        activeBtn.style.boxShadow = '';
                    }, 300);
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
                    button.addEventListener('click', function() {
                        const tabName = this.getAttribute('data-tab');
                        switchContent(tabName);
                    });
                }
            });
            
            // Адаптация кнопок для мобильных устройств
            function adaptLayout() {
                const buttonPanel = document.querySelector('.button-panel');
                if (window.innerWidth <= 768) {
                    buttonPanel.classList.add('horizontal');
                } else {
                    buttonPanel.classList.remove('horizontal');
                }
            }
            
            // Вызываем при загрузке и изменении размера окна
            adaptLayout();
            window.addEventListener('resize', adaptLayout);
        });
    </script>
</body>
</html>