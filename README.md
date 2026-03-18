<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fagner Jacob - Experiência Única em Café</title>
    <link href="https://fonts.googleapis.com/css2?family=SoDo+Sans:wght@300;400;600;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --starbucks-green: #00704A;
            --starbucks-dark: #1E3932;
            --starbucks-light: #D4E9E2;
            --starbucks-accent: #CBA258;
            --white: #FFFFFF;
            --black: #000000;
            --gray: #F2F2F2;
            --text-gray: #6B6B6B;
        }

        body {
            font-family: 'SoDo Sans', 'Open Sans', sans-serif;
            line-height: 1.6;
            color: var(--black);
            overflow-x: hidden;
        }

        /* Header & Navigation */
        header {
            background: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            height: 80px;
        }

        nav {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100%;
        }

        .nav-left {
            display: flex;
            align-items: center;
            gap: 40px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            text-decoration: none;
        }

        .logo svg {
            width: 50px;
            height: 50px;
            transition: transform 0.3s;
        }

        .logo:hover svg {
            transform: scale(1.1);
        }

        .logo-text {
            font-size: 24px;
            font-weight: 700;
            color: var(--starbucks-dark);
            letter-spacing: -0.5px;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--black);
            font-weight: 600;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--starbucks-green);
            transition: width 0.3s;
        }

        .nav-links a:hover {
            color: var(--starbucks-green);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-right {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .location-link {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--black);
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            transition: color 0.3s;
        }

        .location-link:hover {
            color: var(--starbucks-green);
        }

        .btn {
            padding: 12px 24px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s;
            cursor: pointer;
            border: none;
            display: inline-block;
        }

        .btn-primary {
            background: var(--black);
            color: var(--white);
        }

        .btn-primary:hover {
            background: var(--starbucks-dark);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .btn-secondary {
            background: transparent;
            color: var(--black);
            border: 1px solid var(--black);
        }

        .btn-secondary:hover {
            background: var(--gray);
        }

        /* Hero Section */
        .hero {
            margin-top: 80px;
            background: linear-gradient(135deg, var(--starbucks-dark) 0%, var(--starbucks-green) 100%);
            min-height: 90vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 600px;
            height: 600px;
            background: rgba(255,255,255,0.05);
            border-radius: 50%;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -5%;
            width: 400px;
            height: 400px;
            background: rgba(255,255,255,0.03);
            border-radius: 50%;
        }

        .hero-content {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .hero-text h1 {
            font-size: 72px;
            color: var(--white);
            line-height: 1.1;
            margin-bottom: 20px;
            font-weight: 700;
            letter-spacing: -2px;
        }

        .hero-text p {
            font-size: 24px;
            color: var(--starbucks-light);
            margin-bottom: 40px;
            font-weight: 300;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
        }

        .hero-buttons .btn-primary {
            background: var(--white);
            color: var(--starbucks-dark);
        }

        .hero-buttons .btn-primary:hover {
            background: var(--starbucks-light);
        }

        .hero-buttons .btn-secondary {
            color: var(--white);
            border-color: var(--white);
        }

        .hero-buttons .btn-secondary:hover {
            background: rgba(255,255,255,0.1);
        }

        .hero-image {
            position: relative;
        }

        .hero-image img {
            width: 100%;
            max-width: 600px;
            border-radius: 20px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.3);
            transform: rotate(-3deg);
            transition: transform 0.3s;
        }

        .hero-image:hover img {
            transform: rotate(0deg) scale(1.02);
        }

        /* Featured Sections */
        .featured {
            padding: 100px 0;
        }

        .featured-grid {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
        }

        .featured-card {
            border-radius: 20px;
            overflow: hidden;
            position: relative;
            min-height: 500px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 40px;
            transition: transform 0.3s;
        }

        .featured-card:hover {
            transform: translateY(-10px);
        }

        .featured-card.green {
            background: var(--starbucks-green);
            color: var(--white);
        }

        .featured-card.light {
            background: var(--starbucks-light);
            color: var(--starbucks-dark);
        }

        .featured-card.dark {
            background: var(--starbucks-dark);
            color: var(--white);
        }

        .featured-card.gold {
            background: var(--starbucks-accent);
            color: var(--starbucks-dark);
        }

        .featured-content h2 {
            font-size: 48px;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .featured-content p {
            font-size: 18px;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .featured-image {
            position: absolute;
            bottom: 0;
            right: 0;
            width: 50%;
            height: 60%;
            object-fit: contain;
            opacity: 0.9;
        }

        /* Menu Preview */
        .menu-section {
            background: var(--gray);
            padding: 100px 0;
        }

        .section-header {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 60px;
            padding: 0 40px;
        }

        .section-header h2 {
            font-size: 48px;
            color: var(--starbucks-dark);
            margin-bottom: 20px;
        }

        .section-header p {
            font-size: 18px;
            color: var(--text-gray);
        }

        .menu-grid {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
        }

        .menu-item {
            background: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s;
        }

        .menu-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .menu-item-image {
            height: 250px;
            background: linear-gradient(135deg, var(--starbucks-light) 0%, var(--white) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .menu-item-image::before {
            content: '';
            position: absolute;
            width: 150px;
            height: 150px;
            background: radial-gradient(circle, rgba(0,112,74,0.1) 0%, transparent 70%);
            border-radius: 50%;
        }

        .menu-item-image img {
            width: 180px;
            height: 180px;
            object-fit: cover;
            border-radius: 50%;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .menu-item:hover .menu-item-image img {
            transform: scale(1.1) rotate(5deg);
        }

        .menu-item-content {
            padding: 25px;
            text-align: center;
        }

        .menu-item-content h3 {
            font-size: 20px;
            color: var(--starbucks-dark);
            margin-bottom: 10px;
        }

        .menu-item-content p {
            font-size: 14px;
            color: var(--text-gray);
            margin-bottom: 15px;
        }

        .price {
            font-size: 24px;
            font-weight: 700;
            color: var(--starbucks-green);
        }

        /* Rewards Section */
        .rewards {
            background: var(--starbucks-dark);
            color: var(--white);
            padding: 100px 0;
            position: relative;
            overflow: hidden;
        }

        .rewards::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
        }

        .rewards-content {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .rewards-text h2 {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .rewards-text p {
            font-size: 20px;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .rewards-features {
            list-style: none;
            margin-bottom: 40px;
        }

        .rewards-features li {
            padding: 15px 0;
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 18px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .rewards-features li::before {
            content: '★';
            color: var(--starbucks-accent);
            font-size: 24px;
        }

        .rewards-visual {
            position: relative;
        }

        .rewards-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
        }

        .rewards-card .stars {
            font-size: 48px;
            color: var(--starbucks-accent);
            margin-bottom: 20px;
        }

        /* Locations */
        .locations {
            padding: 100px 0;
        }

        .locations-grid {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }

        .location-card {
            background: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s;
        }

        .location-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.12);
        }

        .location-image {
            height: 200px;
            background: linear-gradient(135deg, var(--starbucks-light) 0%, var(--starbucks-green) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
        }

        .location-info {
            padding: 30px;
        }

        .location-info h3 {
            font-size: 24px;
            color: var(--starbucks-dark);
            margin-bottom: 10px;
        }

        .location-info p {
            color: var(--text-gray);
            margin-bottom: 20px;
        }

        .location-status {
            display: inline-block;
            padding: 5px 15px;
            background: var(--starbucks-green);
            color: var(--white);
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }

        /* Footer */
        footer {
            background: var(--starbucks-dark);
            color: var(--white);
            padding: 80px 0 40px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .footer-content {
            max-width: 1440px;
            margin: 0 auto;
            padding: 0 40px;
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 60px;
        }

        .footer-brand .logo {
            margin-bottom: 20px;
        }

        .footer-brand .logo-text {
            color: var(--white);
        }

        .footer-brand p {
            color: rgba(255,255,255,0.7);
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: var(--starbucks-green);
            transform: translateY(-3px);
        }

        .footer-links h4 {
            font-size: 16px;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 15px;
        }

        .footer-links a {
            color: rgba(255,255,255,0.7);
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--starbucks-accent);
        }

        .footer-bottom {
            max-width: 1440px;
            margin: 60px auto 0;
            padding: 40px 40px 0;
            border-top: 1px solid rgba(255,255,255,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: rgba(255,255,255,0.5);
            font-size: 14px;
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            z-index: 1001;
        }

        .mobile-menu-btn span {
            width: 25px;
            height: 3px;
            background: var(--starbucks-dark);
            transition: all 0.3s;
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-text h1 {
                font-size: 48px;
            }

            .hero-image {
                order: -1;
            }

            .featured-grid {
                grid-template-columns: 1fr;
            }

            .menu-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .rewards-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .rewards-features li {
                justify-content: center;
            }

            .locations-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .footer-content {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu-btn {
                display: flex;
            }

            .hero-text h1 {
                font-size: 36px;
            }

            .menu-grid {
                grid-template-columns: 1fr;
            }

            .locations-grid {
                grid-template-columns: 1fr;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .social-links {
                justify-content: center;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate-on-scroll {
            opacity: 0;
            animation: fadeInUp 0.8s ease forwards;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: var(--gray);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--starbucks-green);
            border-radius: 5px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--starbucks-dark);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="nav-left">
                <a href="#" class="logo">
                    <!-- Logo SVG Siren Estilo Starbucks -->
                    <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                        <defs>
                            <linearGradient id="logoGradient" x1="0%" y1="0%" x2="100%" y2="100%">
                                <stop offset="0%" style="stop-color:#00704A"/>
                                <stop offset="100%" style="stop-color:#1E3932"/>
                            </linearGradient>
                        </defs>
                        <circle cx="50" cy="50" r="48" fill="url(#logoGradient)"/>
                        <!-- Siren Stylized -->
                        <path d="M50 20 C40 20 35 30 35 40 C35 50 40 55 50 60 C60 55 65 50 65 40 C65 30 60 20 50 20 Z" fill="white" opacity="0.9"/>
                        <path d="M50 60 C45 65 40 70 40 80 L45 85 L50 80 L55 85 L60 80 C60 70 55 65 50 60" fill="white" opacity="0.9"/>
                        <!-- Crown -->
                        <path d="M35 35 L40 25 L50 30 L60 25 L65 35" stroke="white" stroke-width="3" fill="none" opacity="0.9"/>
                        <!-- Hair waves -->
                        <path d="M35 40 Q25 45 30 55 Q35 60 40 55" fill="white" opacity="0.6"/>
                        <path d="M65 40 Q75 45 70 55 Q65 60 60 55" fill="white" opacity="0.6"/>
                    </svg>
                    <span class="logo-text">Fagner Jacob</span>
                </a>
                <ul class="nav-links">
                    <li><a href="#menu">Cardápio</a></li>
                    <li><a href="#rewards">Rewards</a></li>
                    <li><a href="#locations">Lojas</a></li>
                    <li><a href="#about">Nossa História</a></li>
                </ul>
            </div>
            <div class="nav-right">
                <a href="#" class="location-link">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                        <circle cx="12" cy="10" r="3"></circle>
                    </svg>
                    Encontrar Loja
                </a>
                <a href="#" class="btn btn-secondary">Entrar</a>
                <a href="#" class="btn btn-primary">Participe</a>
                <div class="mobile-menu-btn">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-text">
                <h1>Experimente o extraordinário</h1>
                <p>Descubra uma nova experiência em café. Cada xícara conta uma história de paixão, qualidade e dedicação.</p>
                <div class="hero-buttons">
                    <a href="#menu" class="btn btn-primary">Ver Cardápio</a>
                    <a href="#rewards" class="btn btn-secondary">Conheça o Rewards</a>
                </div>
            </div>
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=800&h=600&fit=crop" alt="Café Fagner Jacob">
            </div>
        </div>
    </section>

    <!-- Featured Sections -->
    <section class="featured">
        <div class="featured-grid">
            <div class="featured-card green">
                <div class="featured-content">
                    <h2>Verão Refresh</h2>
                    <p>Refresque seu dia com nossas bebidas geladas especiais da estação.</p>
                    <a href="#" class="btn btn-primary" style="background: white; color: var(--starbucks-dark);">Explorar</a>
                </div>
            </div>
            <div class="featured-card light">
                <div class="featured-content">
                    <h2>Grãos Premium</h2>
                    <p>Descubra nossa seleção exclusiva de cafés especiais de origem única.</p>
                    <a href="#" class="btn btn-primary">Comprar</a>
                </div>
            </div>
            <div class="featured-card dark">
                <div class="featured-content">
                    <h2>Delícias da Casa</h2>
                    <p>Experimente nossos novos sanduíches e sobremesas artesanais.</p>
                    <a href="#" class="btn btn-secondary">Ver mais</a>
                </div>
            </div>
            <div class="featured-card gold">
                <div class="featured-content">
                    <h2>Fagner Jacob Rewards</h2>
                    <p>Junte estrelas a cada compra e ganhe bebidas grátis.</p>
                    <a href="#" class="btn btn-primary" style="background: var(--starbucks-dark); color: white;">Cadastre-se</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Preview -->
    <section class="menu-section" id="menu">
        <div class="section-header">
            <h2>Destaques do Cardápio</h2>
            <p>Bebidas e comidas cuidadosamente preparadas para tornar seu dia melhor</p>
        </div>
        <div class="menu-grid">
            <div class="menu-item">
                <div class="menu-item-image">
                    <img src="https://images.unsplash.com/photo-1572442388796-11668a67e53d?w=400&h=400&fit=crop" alt="Cappuccino">
                </div>
                <div class="menu-item-content">
                    <h3>Cappuccino Clássico</h3>
                    <p>Espresso com leite vaporizado e espuma cremosa</p>
                    <div class="price">R$ 12,90</div>
                </div>
            </div>
            <div class="menu-item">
                <div class="menu-item-image">
                    <img src="https://images.unsplash.com/photo-1461023058943-07fcbe16d735?w=400&h=400&fit=crop" alt="Frappuccino">
                </div>
                <div class="menu-item-content">
                    <h3>Frappuccino Caramel</h3>
                    <p>Bebida gelada com café, leite e calda de caramelo</p>
                    <div class="price">R$ 16,90</div>
                </div>
            </div>
            <div class="menu-item">
                <div class="menu-item-image">
                    <img src="https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?w=400&h=400&fit=crop" alt="Cold Brew">
                </div>
                <div class="menu-item-content">
                    <h3>Cold Brew Nitro</h3>
                    <p>Café extraído a frio com nitrogenio para cremosidade</p>
                    <div class="price">R$ 14,90</div>
                </div>
            </div>
            <div class="menu-item">
                <div class="menu-item-image">
                    <img src="https://images.unsplash.com/photo-1559496417-e7f25cb247f3?w=400&h=400&fit=crop" alt="Latte">
                </div>
                <div class="menu-item-content">
                    <h3>Matcha Latte</h3>
                    <p>Chá verde matcha com leite vaporizado</p>
                    <div class="price">R$ 15,90</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Rewards Section -->
    <section class="rewards" id="rewards">
        <div class="rewards-content">
            <div class="rewards-text">
                <h2>Fagner Jacob Rewards</h2>
                <p>Junte estrelas em cada compra e desbloqueie benefícios exclusivos.</p>
                <ul class="rewards-features">
                    <li>Bebida de boas-vindas grátis ao cadastrar</li>
                    <li>Bebida grátia a cada 100 estrelas</li>
                    <li>Refil grátis de café do dia</li>
                    <li>Ofertas exclusivas para membros</li>
                </ul>
                <a href="#" class="btn btn-primary" style="background: var(--starbucks-accent); color: var(--starbucks-dark);">Cadastre-se grátis</a>
            </div>
            <div class="rewards-visual">
                <div class="rewards-card">
                    <div class="stars">★★★</div>
                    <h3>Nível Gold</h3>
                    <p>Membros Gold recebem benefícios exclusivos e double stars mensalmente.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Locations -->
    <section class="locations" id="locations">
        <div class="section-header">
            <h2>Nossas Lojas</h2>
            <p>Encontre uma Fagner Jacob perto de você</p>
        </div>
        <div class="locations-grid">
            <div class="location-card">
                <div class="location-image">🏢</div>
                <div class="location-info">
                    <h3>Centro - Flagship</h3>
                    <p>Rua Augusta, 1500 - São Paulo, SP</p>
                    <span class="location-status">Aberto 24h</span>
                </div>
            </div>
            <div class="location-card">
                <div class="location-image">🏬</div>
                <div class="location-info">
                    <h3>Shopping Morumbi</h3>
                    <p>Av. Roque Petroni Jr, 1089 - São Paulo, SP</p>
                    <span class="location-status">10h às 22h</span>
                </div>
            </div>
            <div class="location-card">
                <div class="location-image">🏪</div>
                <div class="location-info">
                    <h3>Pinheiros</h3>
                    <p>Rua dos Pinheiros, 320 - São Paulo, SP</p>
                    <span class="location-status">6h às 20h</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-brand">
                <a href="#" class="logo">
                    <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" style="width: 60px; height: 60px;">
                        <defs>
                            <linearGradient id="footerGradient" x1="0%" y1="0%" x2="100%" y2="100%">
                                <stop offset="0%" style="stop-color:#00704A"/>
                                <stop offset="100%" style="stop-color:#1E3932"/>
                            </linearGradient>
                        </defs>
                        <circle cx="50" cy="50" r="48" fill="url(#footerGradient)"/>
                        <path d="M50 20 C40 20 35 30 35 40 C35 50 40 55 50 60 C60 55 65 50 65 40 C65 30 60 20 50 20 Z" fill="white" opacity="0.9"/>
                        <path d="M50 60 C45 65 40 70 40 80 L45 85 L50 80 L55 85 L60 80 C60 70 55 65 50 60" fill="white" opacity="0.9"/>
                        <path d="M35 35 L40 25 L50 30 L60 25 L65 35" stroke="white" stroke-width="3" fill="none" opacity="0.9"/>
                    </svg>
                    <span class="logo-text">Fagner Jacob</span>
                </a>
                <p>Desde 2024 criando momentos especiais através do café. Cada xícara é uma experiência única de sabor e acolhimento.</p>
                <div class="social-links">
                    <a href="#">📘</a>
                    <a href="#">📸</a>
                    <a href="#">🐦</a>
                    <a href="#">▶️</a>
                </div>
            </div>
            <div class="footer-links">
                <h4>Sobre Nós</h4>
                <ul>
                    <li><a href="#">Nossa História</a></li>
                    <li><a href="#">Missão e Valores</a></li>
                    <li><a href="#">Sustentabilidade</a></li>
                    <li><a href="#">Carreiras</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Atendimento</h4>
                <ul>
                    <li><a href="#">Fale Conosco</a></li>
                    <li><a href="#">Dúvidas Frequentes</a></li>
                    <li><a href="#">Rewards</a></li>
                    <li><a href="#">Presentes</a></li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Legal</h4>
                <ul>
                    <li><a href="#">Termos de Uso</a></li>
                    <li><a href="#">Privacidade</a></li>
                    <li><a href="#">Cookies</a></li>
                    <li><a href="#">Acessibilidade</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 Fagner Jacob Coffee Company. Todos os direitos reservados.</p>
            <p>Desenvolvido com ☕ e paixão</p>
        </div>
    </footer>

    <script>
        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Header scroll effect
        let lastScroll = 0;
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            const currentScroll = window.pageYOffset;
            
            if (currentScroll > 100) {
                header.style.boxShadow = '0 2px 20px rgba(0,0,0,0.1)';
            } else {
                header.style.boxShadow = '0 2px 10px rgba(0,0,0,0.1)';
            }
            
            lastScroll = currentScroll;
        });

        // Animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.menu-item, .location-card, .featured-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
