<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PedraHosting - Professional Hosting</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background-color: #0a0d14;
            color: #ffffff;
            overflow-x: hidden;
        }
        /* Navbar */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 22px 5%;
            background-color: #0a0d14;
            border-bottom: 1px solid #1e293b;
            width: 100%;
        }
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 22px;
            font-weight: bold;
            color: #a855f7;
        }
        .nav-links {
            display: flex;
            gap: 20px;
            list-style: none;
        }
        .nav-links button {
            background: none;
            border: none;
            text-decoration: none;
            color: #94a3b8;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
            padding: 10px 20px;
            border-radius: 8px;
            font-weight: 500;
        }
        .nav-links button:hover, .nav-links button.active {
            color: #ffffff;
            background-color: #1e1b4b;
        }
        
        /* Pages */
        .page {
            display: none;
            padding: 50px 5%;
            min-height: calc(100vh - 160px);
        }
        .page.active {
            display: block;
        }

        /* Hero Section (Home) */
        .hero {
            text-align: center;
            padding: 80px 20px;
            background: radial-gradient(circle at center, #171c2e 0%, #0a0d14 70%);
            max-width: 1200px;
            margin: 0 auto;
        }
        .hero h1 {
            font-size: 56px;
            font-weight: bold;
            margin-bottom: 20px;
            background: linear-gradient(90deg, #c084fc, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero p {
            color: #94a3b8;
            font-size: 20px;
            margin-bottom: 40px;
        }
        .btn-group {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 60px;
        }
        .btn {
            padding: 14px 32px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: bold;
            font-size: 16px;
            transition: 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
        }
        .btn-primary {
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
            color: #fff;
            border: none;
        }
        .btn-primary:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }
        .btn-secondary {
            background-color: #1e293b;
            color: #fff;
            border: 1px solid #334155;
        }
        .btn-secondary:hover {
            background-color: #334155;
        }
        .stats {
            display: flex;
            justify-content: center;
            gap: 80px;
            margin-top: 30px;
        }
        .stat-item h3 {
            font-size: 32px;
            color: #ffffff;
        }
        .stat-item span {
            color: #64748b;
            font-size: 15px;
        }

        /* Pricing Grid - Adjusted to match requested dimensions */
        .section-title {
            text-align: center;
            font-size: 38px;
            margin-bottom: 12px;
            background: linear-gradient(90deg, #c084fc, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .section-subtitle {
            text-align: center;
            color: #94a3b8;
            margin-bottom: 40px;
            font-size: 18px;
        }
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            max-width: 1350px; /* Reduit bech yji kima el capture */
            margin: 0 auto;
        }
        .price-card {
            background-color: #0e121d;
            border: 1px solid #1e293b;
            border-radius: 16px;
            padding: 30px 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            transition: 0.3s;
        }
        .price-card:hover {
            border-color: #8b5cf6;
            transform: translateY(-5px);
        }
        .price-card.popular {
            background: linear-gradient(180deg, rgba(139, 92, 246, 0.08) 0%, #0e121d 40%);
            border: 2px solid #8b5cf6;
        }
        .popular-badge {
            position: absolute;
            top: -14px;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
            color: #ffffff;
            font-size: 13px;
            font-weight: bold;
            padding: 5px 16px;
            border-radius: 20px;
            white-space: nowrap;
        }
        .card-header {
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 1px solid #1e293b;
            padding-bottom: 20px;
        }
        .card-header h3 {
            font-size: 22px;
            color: #ffffff;
            margin-bottom: 10px;
        }
        .price-tag {
            font-size: 32px;
            font-weight: bold;
            color: #3b82f6;
        }
        .price-tag span {
            font-size: 14px;
            color: #94a3b8;
            font-weight: normal;
        }
        .specs-list {
            list-style: none;
            margin-bottom: 25px;
        }
        .specs-list li {
            display: flex;
            justify-content: space-between;
            padding: 9px 0;
            border-bottom: 1px dashed #1e293b;
            font-size: 14px;
            color: #cbd5e1;
        }
        .specs-list li span:last-child {
            font-weight: bold;
            color: #ffffff;
        }
        .payment-box {
            background-color: #141c2e;
            border-radius: 10px;
            padding: 12px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
        }
        .payment-box .usd-price {
            font-size: 16px;
            font-weight: bold;
            color: #3b82f6;
        }
        .payment-methods {
            text-align: right;
            color: #94a3b8;
            font-size: 11px;
            line-height: 1.5;
        }
        .btn-order {
            width: 100%;
            padding: 12px;
            border-radius: 10px;
            border: none;
            font-weight: bold;
            font-size: 15px;
            cursor: pointer;
            transition: 0.3s;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }
        .btn-default {
            background-color: #1e293b;
            color: #ffffff;
        }
        .btn-default:hover {
            background-color: #334155;
        }
        .btn-highlight {
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
            color: #ffffff;
        }
        .btn-highlight:hover {
            opacity: 0.9;
        }
        footer {
            text-align: center;
            padding: 35px;
            border-top: 1px solid #1e293b;
            color: #64748b;
            font-size: 14px;
        }

        /* Responsive */
        @media(max-width: 1200px) {
            .pricing-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        @media(max-width: 768px) {
            .pricing-grid {
                grid-template-columns: 1fr;
            }
            .nav-links {
                gap: 10px;
            }
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav>
        <div class="logo">
            <span>PedraHosting ☁️️</span>
        </div>
        <ul class="nav-links">
            <li><button onclick="switchPage('home')" id="nav-home" class="active">Home</button></li>
            <li><button onclick="switchPage('samp')" id="nav-samp">Host SAMP</button></li>
            <li><button onclick="switchPage('mta')" id="nav-mta">Host MTA</button></li>
            <li><button onclick="switchPage('bot')" id="nav-bot">Host Bot</button></li>
            <li><button onclick="switchPage('vps')" id="nav-vps">VPS</button></li>
        </ul>
    </nav>

    <!-- PAGE 1: HOME -->
    <div id="page-home" class="page active">
        <div class="hero">
            <h1>PedraHosting</h1>
            <p>Professional game servers & VPS hosting with high performance and advanced protection.</p>
            
            <div class="btn-group">
                <a href="https://pedrahosting.top/" target="_blank" class="btn btn-primary">Dashboard VPS →</a>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn btn-secondary">💬 Join Discord</a>
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
                    <h3>Plan 4</h3>
                    <div class="price-tag">$4 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>500 👥</span></li>
                    <li><span>RAM</span> <span>2.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>4 GB 💽</span></li>
                    <li><span>Network</span> <span>11 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 22</strong><br>D17: <strong>DT 16.8</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #c084fc;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>200 👥</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3.5 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #c084fc;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 16.5</strong><br>D17: <strong>DT 12.6</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-highlight">Order Now</a>
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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 11</strong><br>D17: <strong>DT 8.4</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 5.5</strong><br>D17: <strong>DT 4.2</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
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
                    <h3>Plan 4</h3>
                    <div class="price-tag">$4 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>500 👥</span></li>
                    <li><span>RAM</span> <span>2.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>4 GB 💽</span></li>
                    <li><span>Network</span> <span>11 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 22</strong><br>D17: <strong>DT 16.8</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #c084fc;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>200 👥</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3.5 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #c084fc;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 16.5</strong><br>D17: <strong>DT 12.6</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-highlight">Order Now</a>
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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 11</strong><br>D17: <strong>DT 8.4</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 5.5</strong><br>D17: <strong>DT 4.2</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- PAGE 4: HOST BOT -->
    <div id="page-bot" class="page">
        <h2 class="section-title">Host Bot Plans</h2>
        <p class="section-subtitle">Reliable Discord & Telegram bot hosting 24/7 without downtime</p>
        
        <div class="pricing-grid">
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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 22</strong><br>D17: <strong>DT 16.8</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #c084fc;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>200 👥</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3.5 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #c084fc;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 16.5</strong><br>D17: <strong>DT 12.6</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-highlight">Order Now</a>
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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 11</strong><br>D17: <strong>DT 8.4</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

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
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 5.5</strong><br>D17: <strong>DT 4.2</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- PAGE 5: VPS -->
    <div id="page-vps" class="page">
        <h2 class="section-title">VPS Servers Plans</h2>
        <p class="section-subtitle">Powerful VPS servers with high-speed NVMe storage for your projects</p>
        
        <div class="pricing-grid">
            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 4</h3>
                    <div class="price-tag">$4 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>CPU</span> <span>4 Cores ⚙️</span></li>
                    <li><span>RAM</span> <span>4 GB 🔋</span></li>
                    <li><span>NVMe Storage</span> <span>50 GB 💽</span></li>
                    <li><span>Network</span> <span>11 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 22</strong><br>D17: <strong>DT 16.8</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card popular">
                <div class="popular-badge">⭐ Most Popular</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #c084fc;">$3 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>CPU</span> <span>3 Cores ⚙️</span></li>
                    <li><span>RAM</span> <span>3 GB 🔋</span></li>
                    <li><span>NVMe Storage</span> <span>35 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #c084fc;">$3</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 16.5</strong><br>D17: <strong>DT 12.6</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-highlight">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 2</h3>
                    <div class="price-tag">$2 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>CPU</span> <span>2 Cores ⚙️️</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>NVMe Storage</span> <span>25 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 11</strong><br>D17: <strong>DT 8.4</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>

            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 1</h3>
                    <div class="price-tag">$1 <span>/ month</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>CPU</span> <span>1 Core ⚙️</span></li>
                    <li><span>RAM</span> <span>1 GB 🔋</span></li>
                    <li><span>NVMe Storage</span> <span>15 GB 💽</span></li>
                    <li><span>Network</span> <span>1 GB/s 🛜</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">Binance<br>Ooredoo: <strong>DT 5.5</strong><br>D17: <strong>DT 4.2</strong></div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">Order Now</a>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>Made by Atoms • PedraHosting © 2026</p>
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
