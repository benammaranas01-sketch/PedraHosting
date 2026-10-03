<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PedraHosting - استضافة احترافية</title>
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
            padding: 20px 8%;
            background-color: #0a0d14;
            border-bottom: 1px solid #1e293b;
        }
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 20px;
            font-weight: bold;
            color: #a855f7;
        }
        .nav-links {
            display: flex;
            gap: 25px;
            list-style: none;
        }
        .nav-links a {
            text-decoration: none;
            color: #94a3b8;
            font-size: 15px;
            transition: 0.3s;
        }
        .nav-links a:hover, .nav-links a.active {
            color: #ffffff;
            background-color: #1e1b4b;
            padding: 8px 16px;
            border-radius: 8px;
        }
        /* Hero Section */
        .hero {
            text-align: center;
            padding: 80px 20px;
            background: radial-gradient(circle at center, #171c2e 0%, #0a0d14 70%);
        }
        .hero h1 {
            font-size: 48px;
            font-weight: bold;
            margin-bottom: 15px;
            background: linear-gradient(90deg, #c084fc, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero p {
            color: #94a3b8;
            font-size: 18px;
            margin-bottom: 30px;
        }
        .btn-group {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 60px;
        }
        .btn {
            padding: 12px 28px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            font-size: 15px;
            transition: 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        .btn-primary {
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
            color: #fff;
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
        /* Stats */
        .stats {
            display: flex;
            justify-content: center;
            gap: 60px;
            margin-top: 20px;
        }
        .stat-item {
            text-align: center;
        }
        .stat-item h3 {
            font-size: 28px;
            color: #ffffff;
        }
        .stat-item span {
            color: #64748b;
            font-size: 14px;
        }
        /* Services Section */
        .services {
            padding: 60px 8%;
            text-align: center;
        }
        .services h2 {
            font-size: 32px;
            margin-bottom: 10px;
        }
        .services p {
            color: #94a3b8;
            margin-bottom: 40px;
        }
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            text-align: right;
        }
        .card {
            background-color: #0e121d;
            border: 1px solid #1e293b;
            border-radius: 12px;
            padding: 30px;
            transition: 0.3s;
        }
        .card:hover {
            border-color: #8b5cf6;
            transform: translateY(-5px);
        }
        .card h3 {
            font-size: 20px;
            margin-bottom: 10px;
            color: #ffffff;
        }
        .card p {
            color: #94a3b8;
            font-size: 14px;
            margin-bottom: 20px;
        }
        .card a {
            color: #3b82f6;
            text-decoration: none;
            font-weight: bold;
            font-size: 14px;
        }
        /* Footer */
        footer {
            text-align: center;
            padding: 30px;
            border-top: 1px solid #1e293b;
            color: #64748b;
            font-size: 13px;
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav>
        <div class="logo">
            <span>PedraHosting ☁️</span>
        </div>
        <ul class="nav-links">
            <li><a href="#" class="active">الرئيسية</a></li>
            <li><a href="https://pedrahosting.top/" target="_blank">Host SAMP</a></li>
            <li><a href="https://pedrahosting.top/" target="_blank">Host MTA</a></li>
            <li><a href="https://pedrahosting.top/" target="_blank">Host Bot</a></li>
            <li><a href="https://pedrahosting.top/" target="_blank">VPS</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <h1>PedraHosting</h1>
        <p>استضافة احترافية بأسعار لا تُقاوم. نوفر لك أفضل خدمات الاستضافة لسيرفرات الألعاب، البوتات، VPS و RDP بأداء عالي وحماية متقدمة.</p>
        
        <div class="btn-group">
            <a href="https://pedrahosting.top/" target="_blank" class="btn btn-primary">استكشف الخدمات ←</a>
            <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="btn btn-secondary">💬 Join Discord</a>
        </div>

        <div class="stats">
            <div class="stat-item">
                <h3>24/7</h3>
                <span>دعم فني</span>
            </div>
            <div class="stat-item">
                <h3>+500</h3>
                <span>عميل سعيد</span>
            </div>
            <div class="stat-item">
                <h3>99.9%</h3>
                <span>Uptime</span>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services">
        <h2>كل ما تحتاجه في مكان واحد</h2>
        <p>نقدم مجموعة متكاملة من خدمات الاستضافة لتلبية جميع احتياجاتك</p>

        <div class="cards-grid">
            <div class="card">
                <h3>Host Bot</h3>
                <p>استضافة بوتات Discord و Telegram بدون انقطاع وبأداء مستقر.</p>
                <a href="https://pedrahosting.top/" target="_blank">عرض الخطط ←</a>
            </div>
            <div class="card">
                <h3>Host MTA</h3>
                <p>استضافة سيرفرات MTA بسرعة فائقة واستقرار تام لجميع المودات.</p>
                <a href="https://pedrahosting.top/" target="_blank">عرض الخطط ←</a>
            </div>
            <div class="card">
                <h3>Host SA-MP</h3>
                <p>استضافة سيرفرات SA-MP بأداء عالي وحماية DDoS متقدمة.</p>
                <a href="https://pedrahosting.top/" target="_blank">عرض الخطط ←</a>
            </div>
            <div class="card">
                <h3>RDP Servers</h3>
                <p>سيرفرات RDP للوصول عن بعد بأداء ممتاز وسرعة نقل عالية.</p>
                <a href="https://pedrahosting.top/" target="_blank">عرض الخطط ←</a>
            </div>
            <div class="card">
                <h3>VPS Servers</h3>
                <p>سيرفرات VPS بمعالجات قوية وتخزين NvMe سريع جداً لمشاريعك.</p>
                <a href="https://pedrahosting.top/" target="_blank">عرض الخطط ←</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>Made by Atoms • PedraHosting © 2026</p>
    </footer>

</body>
</html>
