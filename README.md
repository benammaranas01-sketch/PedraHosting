<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>خطط الأسعار - PedraHosting</title>
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
        .pricing-section {
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }
        .pricing-section h2 {
            font-size: 36px;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #c084fc, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .pricing-section > p {
            color: #94a3b8;
            margin-bottom: 40px;
            font-size: 16px;
        }
        /* Grid */
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            align-items: stretch;
        }
        /* Card Style */
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
            text-align: right;
        }
        .price-card:hover {
            border-color: #8b5cf6;
            transform: translateY(-5px);
        }
        /* Popular Card Highlight */
        .price-card.popular {
            background: linear-gradient(180deg, rgba(139, 92, 246, 0.08) 0%, #0e121d 40%);
            border: 2px solid #8b5cf6;
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
            box-shadow: 0 4px 10px rgba(139, 92, 246, 0.3);
        }
        /* Plan Header */
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
        /* Specs List */
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
        .specs-list li span:last-child {
            font-weight: bold;
            color: #ffffff;
        }
        /* Payment Box */
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
        .payment-box .usd-price {
            font-size: 16px;
            font-weight: bold;
            color: #3b82f6;
        }
        .payment-methods {
            text-align: left;
            color: #94a3b8;
            font-size: 11px;
            line-height: 1.5;
        }
        /* Button */
        .btn-order {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
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
            box-shadow: 0 4px 15px rgba(139, 92, 246, 0.4);
        }
        .btn-highlight:hover {
            opacity: 0.9;
        }
    </style>
</head>
<body>

    <div class="pricing-section">
        <h2>خطط الأسعار والإمكانيات</h2>
        <p>اختر الخطة المناسبة لسيرفرك أو مشروعك الرقمي بأفضل الأسعار في السوق</p>

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
                    <li><span>SSD Storage</span> <span>4 GB 💽</span></li>
                    <li><span>Network Speed</span> <span>11 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$4</span>
                    <div class="payment-methods">
                        Binance<br>
                        Ooredoo: <strong>DT 22</strong><br>
                        D17: <strong>DT 16.8</strong>
                    </div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">اطلب الآن</a>
            </div>

            <!-- Plan 3 (Most Popular) -->
            <div class="price-card popular">
                <div class="popular-badge">⭐ الأكثر طلباً</div>
                <div class="card-header">
                    <h3>Plan 3</h3>
                    <div class="price-tag" style="color: #c084fc;">$3 <span>/ شهرياً</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>200 👥</span></li>
                    <li><span>RAM</span> <span>2 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3.5 GB 💽</span></li>
                    <li><span>Network Speed</span> <span>1 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price" style="color: #c084fc;">$3</span>
                    <div class="payment-methods">
                        Binance<br>
                        Ooredoo: <strong>DT 16.5</strong><br>
                        D17: <strong>DT 12.6</strong>
                    </div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-highlight">اطلب الآن</a>
            </div>

            <!-- Plan 2 -->
            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 2</h3>
                    <div class="price-tag">$2 <span>/ شهرياً</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>100 👥</span></li>
                    <li><span>RAM</span> <span>1.5 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>3 GB 💽</span></li>
                    <li><span>Network Speed</span> <span>1 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$2</span>
                    <div class="payment-methods">
                        Binance<br>
                        Ooredoo: <strong>DT 11</strong><br>
                        D17: <strong>DT 8.4</strong>
                    </div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">اطلب الآن</a>
            </div>

            <!-- Plan 1 -->
            <div class="price-card">
                <div class="card-header">
                    <h3>Plan 1</h3>
                    <div class="price-tag">$1 <span>/ شهرياً</span></div>
                </div>
                <ul class="specs-list">
                    <li><span>Slots</span> <span>50 👥</span></li>
                    <li><span>RAM</span> <span>1 GB 🔋</span></li>
                    <li><span>SSD Storage</span> <span>2 GB 💽</span></li>
                    <li><span>Network Speed</span> <span>1 GB/s 🛜</span></li>
                    <li><span>Database</span> <span>x1 Database 🗄️</span></li>
                </ul>
                <div class="payment-box">
                    <span class="usd-price">$1</span>
                    <div class="payment-methods">
                        Binance<br>
                        Ooredoo: <strong>DT 5.5</strong><br>
                        D17: <strong>DT 4.2</strong>
                    </div>
                </div>
                <a href="https://pedrahosting.top/" target="_blank" class="btn-order btn-default">اطلب الآن</a>
            </div>

        </div>
    </div>

</body>
</html>
