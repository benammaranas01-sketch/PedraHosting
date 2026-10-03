<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PedraHosting - الخدمات والخطط</title>
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
            padding: 40px 20px;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }
        h2 {
            font-size: 32px;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #c084fc, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        p.subtitle {
            color: #94a3b8;
            margin-bottom: 40px;
            font-size: 16px;
        }
        /* Grid des services */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 60px;
            text-align: right;
        }
        .service-card {
            background-color: #0e121d;
            border: 1px solid #1e293b;
            border-radius: 12px;
            padding: 30px;
            transition: 0.3s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .service-card:hover {
            border-color: #8b5cf6;
            transform: translateY(-5px);
        }
        .service-card h3 {
            font-size: 20px;
            margin-bottom: 10px;
            color: #ffffff;
        }
        .service-card p {
            color: #94a3b8;
            font-size: 14px;
            margin-bottom: 20px;
        }
        .service-btn {
            display: inline-block;
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
            color: #fff;
            padding: 10px 20px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            font-size: 14px;
            text-align: center;
            transition: 0.3s;
        }
        .service-btn:hover {
            opacity: 0.9;
        }

        /* Section Plans (Kima l'capture l'lola) */
        .plans-section {
            border-top: 1px solid #1e293b;
            padding-top: 50px;
        }
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            align-items: stretch;
            text-align: right;
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
        }
        .price-card.popular {
            border: 2px solid #8b5cf6;
            background: linear-gradient(180deg, rgba(139, 92, 246, 0.08) 0%, #0e121d 40%);
        }
        .popular-badge {
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
            color: #ffffff;
            font-size: 12px;
            font-weight: bold;
            padding: 4px 14px;
            border-radius: 20px;
        }
        .card-header {
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 1px solid #1e293b;
            padding-bottom: 20px;
        }
        .price-tag {
            font-size: 32px;
            font-weight: bold;
            color: #3b82f6;
        }
        .price-tag span {
            font-size: 14px;
            color: #94a3b8;
        }
        .specs-list {
            list-style: none;
            margin-bottom: 25px;
        }
        .specs-list li {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px dashed #1e293b;
            font-size: 14px;
            color: #cbd5e1;
        }
        .payment-box {
            background-color: #141c2e;
            border-radius: 8px;
            padding: 12px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
        }
        .btn-order {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            background-color: #1e293b;
            color: #fff;
            border: none;
            font-weight: bold;
            cursor: pointer;
            text-align: center;
            text-decoration: none;
        }
        .btn-order.highlight {
            background: linear-gradient(135deg, #8b5cf6, #3b82f6);
        }
    </style>
</head>
<body>

    <div class="container">
        <h2>خدمات الاستضافة لدينا</h2>
        <p class="subtitle">اختر الخدمة المطلوبة لعرض الأسعار والخطط المتاحة</p>

        <!-- Services Grid -->
        <div class="services-grid">
            <div class="service-card">
                <div>
                    <h3>Host SA-MP</h3>
                    <p>استضافة سيرفرات SA-MP بأداء عالي وحماية DDoS متقدمة.</p>
                </div>
                <a href="#samp-plans" class="service-btn">عرض الخطط ←</a>
            </div>

            <div class="service-card">
                <div>
                    <h3>Host MTA</h3>
                    <p>استضافة سيرفرات MTA بسرعة فائقة واستقرار تام لجميع المودات.</p>
                </div>
                <a href="#mta-plans" class="service-btn">عرض الخطط ←</a>
            </div>

            <div class="service-card">
                <div>
                    <h3>Host Bot (Discord / Telegram)</h3>
                    <p>استضافة بوتاتك بدون انقطاع وبأداء مستقر وسريع 24/7.</p>
                </div>
                <a href="#bot-plans" class="service-btn">عرض الخطط ←</a>
            </div>

            <div class="service-card">
                <div>
                    <h3>Minecraft Hosting</h3>
                    <p>استضافة سيرفرات Minecraft مع دعم كامل للمودات والـPlugins.</p>
                </div>
                <a href="#mc-plans" class="service-btn">عرض الخطط ←</a>
            </div>
        </div>

        <!-- Plans Section Example (Kima l'capture) -->
        <div id="samp-plans" class="plans-section">
            <h2>خطط استضافة SA-MP</h2>
            <p class="subtitle">اختر الباقة المناسبة لك وابدأ مشروعك الآن</p>

            <div class="pricing-grid">
                <!-- Plan 4 -->
                <div class="price-card">
                    <div class="card-header">
                        <h3>Plan 4</h3>
                        <div class="price-tag">$4 <span>/ شهرياً</span></div>
                    </div>
                    <ul class="specs-list">
                        <li><span>Slots</span> <span>500 👥</span></li>
                        <li><span>RAM</span> <span>2.5 GB 🔋</span></li>
                        <li><span>SSD</span> <span>4 GB 💽</span></li>
                    </ul>
                    <div class="payment-box">
                        <span>$4</span>
                        <div style="font-size: 11px; color:#94a3b8;">Ooredoo: DT 22<br>D17: DT 16.8</div>
                    </div>
                    <a href="https://pedrahosting.top/" target="_blank" class="btn-order">اطلب الآن</a>
                </div>

                <!-- Plan 3 (Popular) -->
                <div class="price-card popular">
                    <div class="popular-badge">⭐ الأكثر طلباً</div>
                    <div class="card-header">
                        <h3>Plan 3</h3>
                        <div class="price-tag" style="color: #c084fc;">$3 <span>/ شهرياً</span></div>
                    </div>
                    <ul class="specs-list">
                        <li><span>Slots</span> <span>200 👥</span></li>
                        <li><span>RAM</span> <span>2 GB 🔋</span></li>
                        <li><span>SSD</span> <span>3.5 GB 💽</span></li>
                    </ul>
                    <div class="payment-box">
                        <span style="color: #c084fc;">$3</span>
                        <div style="font-size: 11px; color:#94a3b8;">Ooredoo: DT 16.5<br>D17: DT 12.6</div>
                    </div>
                    <a href="https://pedrahosting.top/" target="_blank" class="btn-order highlight">اطلب الآن</a>
                </div>
            </div>
        </div>

    </div>

</body>
</html>
