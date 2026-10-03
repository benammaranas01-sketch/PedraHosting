<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>R4X Hosting - Sanfour Edition</title>
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
            gap: 12px;
            list-style: none;
        }
        .nav-links button {
            background: transparent;
            border: 1px solid transparent;
            color: #93c5fd;
            font-size: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            padding: 10px 22px;
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
        
        .sanfour-container {
            margin-bottom: 25px;
        }
        .sanfour-img {
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
        footer {
            text-align: center;
            padding: 40px;
            border-top: 1px solid rgba(30, 58, 138, 0.6);
            color: #93c5fd;
            font-size: 14px;
            background-color: #020408;
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav>
        <div class="logo">
            <span>R4X Hosting 🧢</span>
        </div>
        <ul class="nav-links">
            <li><button onclick="switchPage('home')" id="nav-home" class="active">Home</button></li>
        </ul>
    </nav>

    <!-- PAGE 1: HOME -->
    <div id="page-home" class="page active">
        <div class="hero">
            <div class="sanfour-container">
                <img src="pedra_background.jpg" alt="Sanfour Boss" class="sanfour-img">
            </div>
            <h1>R4X Hosting <span style="color: #60a5fa;">Sanfour Edition</span></h1>
            <p>High-performance servers protected and managed by the ultimate Sanfour squad. Lightning-fast speed & 99.9% uptime.</p>
            
            <div class="btn-group">
                <a href="#" class="btn btn-primary">Dashboard VPS →</a>
                <a href="#" class="btn btn-secondary">💬 Join Discord</a>
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

    <footer>
        <p>Powered by Sanfour Squad • R4X Hosting © 2026</p>
    </footer>

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
