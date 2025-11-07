<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Адаптер Klim Metobalitov</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #000000;
            --secondary-color: #ff0000;
            --accent-color: #2a2a2a;
            --text-color: #ffffff;
            --shadow: 0 4px 15px rgba(255, 0, 0, 0.3);
        }

        body {
            background-color: var(--primary-color);
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            padding: 20px 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
        }

        .logo h1 {
            font-size: 1.8rem;
            margin-left: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
            background: linear-gradient(to right, var(--text-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .logo-icon {
            color: var(--secondary-color);
            font-size: 2rem;
        }

        /* Hero Section */
        .hero {
            padding: 80px 0;
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="black"/><path d="M0 0L100 100M100 0L0 100" stroke="darkred" stroke-width="1"/></svg>');
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, transparent 0%, var(--primary-color) 70%);
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
            color: #cccccc;
        }

        .highlight {
            color: var(--secondary-color);
            font-weight: bold;
        }

        /* Buttons Section */
        .buttons-section {
            padding: 60px 0;
            background-color: var(--accent-color);
        }

        .section-title {
            text-align: center;
            margin-bottom: 40px;
            font-size: 2.2rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 3px;
            background-color: var(--secondary-color);
            margin: 10px auto;
        }

        .buttons-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .btn {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 25px 20px;
            background: linear-gradient(145deg, #1a1a1a, #2a2a2a);
            border-radius: 10px;
            text-decoration: none;
            color: var(--text-color);
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            border: 1px solid #333;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 0, 0, 0.2), transparent);
            transition: 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(255, 0, 0, 0.3);
            border-color: var(--secondary-color);
        }

        .btn-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--secondary-color);
        }

        .btn-title {
            font-size: 1.4rem;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .btn-description {
            font-size: 0.9rem;
            color: #cccccc;
        }

        /* Features Section */
        .features {
            padding: 80px 0;
            background-color: var(--primary-color);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: linear-gradient(145deg, #1a1a1a, #2a2a2a);
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
            border: 1px solid #333;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: var(--secondary-color);
        }

        .feature-icon {
            font-size: 3rem;
            color: var(--secondary-color);
            margin-bottom: 20px;
        }

        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .feature-description {
            color: #cccccc;
        }

        /* Footer */
        footer {
            background-color: var(--accent-color);
            padding: 40px 0 20px;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .footer-logo {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .footer-logo h3 {
            font-size: 1.5rem;
            margin-left: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .footer-links {
            display: flex;
            gap: 20px;
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .footer-link {
            color: var(--text-color);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-link:hover {
            color: var(--secondary-color);
        }

        .copyright {
            margin-top: 20px;
            color: #888;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            .logo {
                margin-bottom: 15px;
            }
        }

        @media (max-width: 480px) {
            .hero h2 {
                font-size: 1.8rem;
            }
            
            .btn-title {
                font-size: 1.2rem;
            }
            
            .feature-card {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-bolt logo-icon"></i>
                    <h1>Адаптер Klim Metobalitov</h1>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h2>Инновационный адаптер <span class="highlight">Klim Metobalitov</span></h2>
                <p>на любой вопрос мы найдем ответ :)</p>
            </div>
        </div>
    </section>

    <!-- Buttons Section -->
    <section class="buttons-section">
        <div class="container">
            <h2 class="section-title">Наши ресурсы</h2>
            <div class="buttons-grid">
                <a href="t.me/ewouv" class="btn">
                    <i class="fas fa-user-circle btn-icon"></i>
                    <div class="btn-title">Профиль</div>
                    <div class="btn-description">Свяжитесь с нами напрямую</div>
                </a>
                
                <a href="https://t.me/klprice" class="btn">
                    <i class="fas fa-tags btn-icon"></i>
                    <div class="btn-title">Прайс-лист</div>
                    <div class="btn-description">Актуальные цены на товар</div>
                </a>
                
                <a href="https://t.me/repklim" class="btn">
                    <i class="fas fa-star btn-icon"></i>
                    <div class="btn-title">Отзывы</div>
                    <div class="btn-description">Мнения наших клиентов</div>
                </a>
                
                <a href="https://t.me/PODARKI_KLIMA" class="btn">
                    <i class="fas fa-users btn-icon"></i>
                    <div class="btn-title">Проект</div>
                    <div class="btn-description">Присоединяйтесь к нашему сообществу</div>
                </a>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">Преимущества</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <i class="fas fa-tachometer-alt feature-icon"></i>
                    <h3 class="feature-title">Мы быстро отвечаем и помогаем нашим клиентам</h3>
                    <p class="feature-description">Обеспечиваем максимальную эффективность работы в любых условиях.</p>
                </div>
                
                <div class="feature-card">
                    <i class="fas fa-shield-alt feature-icon"></i>
                    <h3 class="feature-title">Надежная защита</h3>
                    <p class="feature-description">Не какого-либо обмана с нашей стороны .</p>
                </div>
                
                <div class="feature-card">
                    <i class="fas fa-cogs feature-icon"></i>
                    <h3 class="feature-title">поддержка</h3>
                    <p class="feature-description">ответим быстро на вопросы о наших услугах</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">
                    <i class="fas fa-bolt logo-icon"></i>
                    <h3>Klim Metobalitov</h3>
                </div>
                
                <div class="footer-links">
                    <a href="t.me/ewouv" class="footer-link">Профиль</a>
                    <a href="https://t.me/klprice" class="footer-link">Прайс</a>
                    <a href="https://t.me/repklim" class="footer-link">Отзывы</a>
                    <a href="https://t.me/Dealer_nett" class="footer-link">Проект</a>
                </div>
                
                <p class="copyright">© 2025 Адаптер Klim Metobalitov. Все права защищены.</p>
            </div>
        </div>
    </footer>
</body>
</html>
