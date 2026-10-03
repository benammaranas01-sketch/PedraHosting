<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Pedra Hosting - LTD</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background-color: #040814;
            color: #f1f5f9;
            overflow-x: hidden;
        }

        /* Navbar */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 6%;
            background-color: rgba(4, 8, 20, 0.9);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(59, 130, 246, 0.2);
            width: 100%;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 24px;
            font-weight: 800;
            background: linear-gradient(135deg, #60a5fa, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(96, 165, 250, 0.4);
        }
        .nav-links {
            display: flex;
            gap: 10px;
            list-style: none;
            flex-wrap: wrap;
        }
        .nav-links button {
            background: transparent;
            border: 1px solid transparent;
            color: #93c5fd;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s ease;
            padding: 8px 18px;
            border-radius: 10px;
            font-weight: 600;
        }
        .nav-links button:hover {
            color: #ffffff;
            background: rgba(59, 130, 246, 0.1);
            border-color: rgba(59, 130, 246, 0.3);
        }
        .nav-links button.active {
            color: #ffffff;
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.3), rgba(37, 99, 235, 0.3));
            border-color: #3b82f6;
            box-shadow: 0 0 15px rgba(59, 130, 246, 0.3);
        }
        
        .page {
            display: none;
            padding: 50px 5%;
            min-height: calc(100vh - 150px);
            animation: fadeIn 0.4s ease-in-out;
        }
        .page.active {
            display: block;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(rgba(4, 8, 20, 0.75), rgba(4, 8, 20, 0.85)), url('pedra_background.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            max-width: 1300px;
            margin: 0 auto;
            border-radius: 24px;
            border: 1px solid rgba(59, 130, 246, 0.4);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.7);
        }
        
        .Pedra-container {
            margin-bottom: 25px;
        }
        .Pedra-img {
            width: 160px;
            height: 160px;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid #60a5fa;
            box-shadow: 0 0 30px rgba(96, 165, 250, 0.6);
            animation: float 3s ease-in-out infinite;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        .hero h1 {
            font-size: 52px;
            font-weight: 900;
            margin-bottom: 15px;
            background: linear-gradient(90deg, #60a5fa, #ffffff, #60a5fa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(59, 130, 246, 0.5);
        }
        .hero p {
            color: #93c5fd;
            font-size: 18px;
            margin-bottom: 35px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 500;
        }
        .btn-group {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 50px;
        }
        .btn {
            padding: 14px 32px;
            border-radius: 12px;
            text-decoration: none;
            font-weight: bold;
            font-size: 16px;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
        }
        .btn-primary {
            background: linear-gradient(135deg, #3b82f6, #1d4ed8);
            color: #fff;
            border: none;
            box-shadow: 0 4px 20px rgba(59, 130, 246, 0.4);
        }
        .btn-primary:hover {
            opacity: 0.95;
            transform: translateY(-3px);
            box-shadow: 0 6px 25px rgba(59, 130, 246, 0.6);
        }
        .btn-secondary {
            background-color: rgba(11, 19, 41, 0.9);
            color: #fff;
            border: 1px solid #1e3a8a;
        }
        .btn-secondary:hover {
            background-color: #1e293b;
            border-color: #3b82f6;
        }
        .stats {
            display: flex;
            justify-content: center;
            gap: 70px;
            margin-top: 30px;
            padding-top: 30px;
            border-top: 1px solid rgba(30, 58, 138, 0.5);
        }
        .stat-item h3 {
            font-size: 34px;
            font-weight: 800;
            color: #ffffff;
            text-shadow: 0 0 10px rgba(96, 165, 250, 0.4);
        }
        .stat-item span {
            color: #93c5fd;
            font-size: 14px;
            font-weight: 500;
        }

        /* Pricing Grids */
        .section-title {
            text-align: center;
            font-size: 38px;
            font-weight: 800;
            margin-bottom: 12px;
            background: linear-gradient(90deg, #60a5fa, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .section-subtitle {
            text-align: center;
            color: #93c5fd;
            margin-bottom: 45px;
            font-size: 17px;
        }
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 22px;
            max-width: 1350px;
            margin: 0 auto;
        }
        .price-card {
            background: linear-gradient(145deg, #070e1f, #0b1530);
            border: 1px solid rgba(30, 58, 138, 0.8);
            border-radius: 18px;
            padding: 30px 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0,0,0,0.4);
        }
        .price-card:hover {
            border-color: rgba(96, 165, 250, 0.8);
            transform: translateY(-6px);
            box-shadow: 0 15px 40px rgba(59, 130, 246, 0.2);
        }
        .price-card.popular {
            background: linear-gradient(145deg, #091330, #0f2252);
            border: 2px solid #3b82f6;
            box-shadow: 0 10px 35px rgba(59, 130, 246, 0.3);
        }
        .popular-badge {
            position: absolute;
            top: -14px;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(135deg, #3b82f6, #60a5fa);
            color: #ffffff;
            font-size: 12px;
            font-weight: 700;
            padding: 5px 16px;
            border-radius: 20px;
            white-space: nowrap;
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.4);
        }
        .card-header {
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 1px solid rgba(30, 58, 138, 0.8);
            padding-bottom: 20px;
        }
        .card-header h3 {
            font-size: 22px;
            color: #ffffff;
            margin-bottom: 10px;
            font-weight: 700;
        }
        .price-tag {
            font-size: 32px;
            font-weight: 800;
            color: #60a5fa;
        }
        .price-tag span {
            font-size: 14px;
            color: #93c5fd;
            font-weight: normal;
        }
        .specs-list {
            list-style: none;
            margin-bottom: 25px;
        }
        .specs-list li {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px dashed rgba(30, 58, 138, 0.5);
            font-size: 14px;
            color: #cbd5e1;
        }
        .specs-list li span:last-child {
            font-weight: 700;
            color: #ffffff;
        }
        .payment-box {
            background-color: rgba(7, 14, 31, 0.8);
            border: 1px solid rgba(30, 58, 138, 0.8);
            border-radius: 12px;
            padding: 12px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
        }
        .payment-box .usd-price {
            font-size: 16px;
            font-weight: 800;
            color: #60a5fa;
        }
        .payment-methods {
            text-align: right;
            color: #93c5fd;
            font-size: 11px;
            line-height: 1.5;
        }
        .btn-order {
            width: 100%;
            padding: 12px;
            border-radius: 12px;
            border: none;
            font-weight: 700;
            font-size: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }
        .btn-default {
            background-color: #1e3a8a;
            color: #ffffff;
        }
        .btn-default:hover {
            background-color: #2563eb;
        }
        .btn-highlight {
            background: linear-gradient(135deg, #3b82f6, #60a5fa);
            color: #ffffff;
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.3);
        }
        .btn-highlight:hover {
            opacity: 0.95;
            box-shadow: 0 6px 20px rgba(59, 130, 246, 0.5);
        }

        footer {
            text-align: center;
            padding: 40px;
            border-top: 1px solid rgba(30, 58, 138, 0.6);
            color: #93c5fd;
            font-size: 14px;
            background-color: #020408;
            margin-top: 50px;
        }

        @media(max-width: 1200px) {
            .pricing-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        @media(max-width: 768px) {
            .pricing-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav>
        <div class="logo">
            <span>Pedra Hosting 🧢</span>
        </div>
        <ul class="nav-links">
            <li><button onclick="switchPage('home')" id="nav-home" class="active">Home</button></li>
            <li><button onclick="switchPage('samp')" id="nav-samp">Host SAMP</button></li>
            <li><button onclick="switchPage('mta')" id="nav-mta">Host MTA</button></li>
            <li><button onclick="switchPage('minecraft')" id="nav-minecraft">Host Minecraft</button></li>
            <li><button onclick="switchPage('bot')" id="nav-bot">Host Bot</button></li>
        </ul>
    </nav>

    <!-- PAGE 1: HOME -->
    <div id="page-home" class="page active">
        <div class="hero">
            <div class="Pedra-container">
                <img src="pedra_background.jpg" alt="pedra Boss" class="Pedra-img">
            </div>
            <h1>Pedra Hosting <span style="color: #60a5fa;">Ltd</span></h1>
            <p>High-performance servers protected and managed by the ultimate Pedra squad. Lightning-fast speed & 99.9% uptime.</p>
            
            <div class="btn-group">
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn btn-primary">💬 Join Discord</a>
                <button onclick="switchPage('samp')" class="btn btn-secondary">Explore Plans 🚀</button>
            </div>

            <div class="stats">
                <div class="stat-item">
                    <h3>24/7</h3>
                    <span>Support</span>
                </div>
                <div class="stat-item">
                    <h3>+500</h3>
                    <span>Happy Clients</span>
                </div>
                <div class="stat-item">
                    <h3>99.9%</h3>
                    <span>Uptime</span>
                </div>
            </div>
        </div>
    </div>

    <!-- PAGE 2: HOST SAMP -->
    <div id="page-samp" class="page">
        <h2 class="section-title">Host SA-MP Plans</h2>
        <p class="section-subtitle">High performance SA-MP server hosting with advanced DDoS protection</p>
        
        <div class="pricing-grid">
            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 1</h3>
                    <div class="price-tag">$1 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>50 👥</span></li>
                    <li><span>RAM</span> <span>1 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>2 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>5.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 2</h3>
                    <div class="price-tag">$2 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>100 👥</span></li>
                    <li><span>RAM</span> <span>1.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>11 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #60a5fa;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>200 👥</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3.5 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #60a5fa;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>16.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-highlight">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 4</h3>
                    <div class="price-tag">$4 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>500 👥</span></li>
                    <li><span>RAM</span> <span>2.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>4 GB 💽</span></li>
                    <li><span>Network</span> <span>11 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>22 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- PAGE 3: HOST MTA -->
    <div id="page-mta" class="page">
        <h2 class="section-title">Host MTA Plans</h2>
        <p class="section-subtitle">Lightning fast MTA server hosting with smooth performance</p>
        
        <div class="pricing-grid">
            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 1</h3>
                    <div class="price-tag">$1 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>50 👥</span></li>
                    <li><span>RAM</span> <span>1 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>2 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>5.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 2</h3>
                    <div class="price-tag">$2 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>100 👥</span></li>
                    <li><span>RAM</span> <span>1.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>11 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #60a5fa;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>200 👥</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3.5 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #60a5fa;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>16.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-highlight">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 4</h3>
                    <div class="price-tag">$4 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>500 👥</span></li>
                    <li><span>RAM</span> <span>2.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>4 GB 💽</span></li>
                    <li><span>Network</span> <span>11 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>22 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- PAGE 4: HOST MINECRAFT -->
    <div id="page-minecraft" class="page">
        <h2 class="section-title">Host Minecraft Plans</h2>
        <p class="section-subtitle">Lag-free Minecraft server hosting with full plugin & mod support</p>
        
        <div class="pricing-grid">
            <div class="price-card">
                <div class="card-header">
                    <h3>MC Plan 1</h3>
                    <div class="price-tag">$1.5 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>Storage</span> <span>10 GB SSD 💽</span></li>
                    <li><span>Players</span> <span>Up to 20 👥</span></li>
                    <li><span>Support</span> <span>Spigot / Paper ⛏️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1.5</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>8 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>MC Plan 2</h3>
                    <div class="price-tag" style="color: #60a5fa;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>4 GB 🔋</span></li>
                    <li><span>Storage</span> <span>25 GB SSD 💽</span></li>
                    <li><span>Players</span> <span>Up to 50 👥</span></li>
                    <li><span>Support</span> <span>Mods & Plugins ⚙️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #60a5fa;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>16.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-highlight">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>MC Plan 3</h3>
                    <div class="price-tag">$5 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>6 GB 🔋</span></li>
                    <li><span>Storage</span> <span>40 GB SSD 💽</span></li>
                    <li><span>Players</span> <span>Unlimited 👥</span></li>
                    <li><span>Support</span> <span>High Performance 🚀</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$5</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>27.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>MC Plan 4</h3>
                    <div class="price-tag">$8 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>8 GB 🔋</span></li>
                    <li><span>Storage</span> <span>60 GB SSD 💽</span></li>
                    <li><span>Players</span> <span>Unlimited 👥</span></li>
                    <li><span>Support</span> <span>Dedicated Core ⚙️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$8</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>44 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- PAGE 5: HOST BOT -->
    <div id="page-bot" class="page">
        <h2 class="section-title">Host Bot Plans</h2>
        <p class="section-subtitle">Reliable Discord & Telegram bot hosting 24/7 without downtime</p>
        
        <div class="pricing-grid">
            <div class="price-card">
                <div class="card-header">
                    <h3>Bot Lite</h3>
                    <div class="price-tag">$1 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>512 MB 🔋</span></li>
                    <li><span>Storage</span> <span>5 GB 💽</span></li>
                    <li><span>Uptime</span> <span>24/7 Online 🟢</span></li>
                    <li><span>Node.js / Python</span> <span>Supported 🤖</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>5.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Best Choice</div>
                <div class="card-header">
                    <h3>Bot Pro</h3>
                    <div class="price-tag" style="color: #60a5fa;">$2 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>1 GB 🔋</span></li>
                    <li><span>Storage</span> <span>10 GB 💽</span></li>
                    <li><span>Uptime</span> <span>24/7 Online 🟢</span></li>
                    <li><span>Database</span> <span>Included 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #60a5fa;">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>11 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-highlight">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Bot Ultra</h3>
                    <div class="price-tag">$3.5 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>Storage</span> <span>20 GB 💽</span></li>
                    <li><span>Uptime</span> <span>24/7 Online 🟢</span></li>
                    <li><span>CPU</span> <span>Priority Cores ⚙️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$3.5</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>19 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Bot Enterprise</h3>
                    <div class="price-tag">$5 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>RAM</span> <span>4 GB 🔋</span></li>
                    <li><span>Storage</span> <span>35 GB 💽</span></li>
                    <li><span>Uptime</span> <span>24/7 Online 🟢</span></li>
                    <li><span>Performance</span> <span>Max Power 🚀</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$5</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>27.5 DT</strong></div>
                </div>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>Powered by Pedra Squad • Pedra Hosting © 2026</p>
    </footer>

    <!-- JavaScript -->
    <script>
        function switchPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.querySelectorAll('.nav-links button').forEach(btn => {
                btn.classList.remove('active');
            });
            document.getElementById('page-' + pageId).classList.add('active');
            document.getElementById('nav-' + pageId).classList.add('active');
        }
    </script>
</body>
</html>
