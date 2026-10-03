<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>R4X Store - Client Dashboard & Order</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        dark: { 900: '#070b14', 800: '#0e1626', 700: '#162238', 600: '#1e2f4d' },
                        blueaccent: { 500: '#3b82f6', 600: '#2563eb' }
                    }
                }
            }
        }
    </script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-dark-900 text-gray-100 font-sans antialiased min-h-screen flex selection:bg-blue-600 selection:text-white">

    <!-- SIDEBAR -->
    <aside class="w-64 bg-dark-800 border-r border-dark-700 flex flex-col justify-between p-4 fixed top-0 left-0 h-screen z-20">
        <div>
            <div class="flex items-center space-x-3 px-2 mb-8 mt-2">
                <div class="w-9 h-9 rounded-xl bg-gradient-to-tr from-blue-600 to-indigo-500 flex items-center justify-center shadow-lg shadow-blue-500/30">
                    <i class="fa-solid fa-store text-white text-sm"></i>
                </div>
                <span class="text-lg font-bold tracking-wide text-white">R4X<span class="text-blue-400">Store</span></span>
            </div>

            <div class="space-y-1 text-sm font-medium">
                <a href="#" onclick="switchPage('dashboard')" id="nav-dashboard" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl bg-blue-600/10 text-blue-400 border border-blue-500/20 transition">
                    <i class="fa-solid fa-house text-base w-5"></i><span>Dashboard</span>
                </a>
                <a href="#" onclick="switchPage('register')" id="nav-register" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-solid fa-user-plus text-base w-5"></i><span>Register</span>
                </a>
                <a href="#" onclick="switchPage('store')" id="nav-store" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-solid fa-cart-shopping text-base w-5"></i><span>Order Store</span>
                </a>
            </div>
        </div>

        <div class="bg-dark-900/60 border border-dark-700 rounded-2xl p-3 flex items-center justify-between">
            <div class="flex items-center space-x-3 overflow-hidden">
                <div class="w-9 h-9 rounded-full bg-blue-600 flex items-center justify-center font-bold text-white text-sm" id="user-initial">G</div>
                <div class="truncate">
                    <div class="text-sm font-semibold text-white truncate" id="user-name-display">Guest</div>
                    <div class="text-xs text-gray-400" id="user-status-text">Not Registered</div>
                </div>
            </div>
        </div>
    </aside>

    <!-- MAIN CONTENT -->
    <main class="flex-grow ml-64 p-10 max-w-5xl mx-auto space-y-8">

        <!-- PAGE 1: DASHBOARD -->
        <div id="page-dashboard" class="page-section space-y-6">
            <div class="bg-dark-800 border border-dark-700 rounded-3xl p-8 shadow-xl">
                <h1 class="text-3xl font-extrabold text-white mb-2">Welcome to R4X Store 🛒</h1>
                <p class="text-gray-400 text-sm">Manage your orders and services easily. Register first to start ordering.</p>
            </div>
        </div>

        <!-- PAGE 2: REGISTER -->
        <div id="page-register" class="page-section space-y-6 hidden">
            <div class="bg-dark-800 border border-dark-700 rounded-3xl p-8 max-w-md mx-auto shadow-xl">
                <h2 class="text-2xl font-bold text-white mb-6">Register Account</h2>
                <form id="register-form" onsubmit="handleRegister(event)" class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">Username</label>
                        <input type="text" id="reg-username" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-blue-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">Email</label>
                        <input type="email" id="reg-email" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-blue-500">
                    </div>
                    <button type="submit" class="w-full py-3 bg-blue-600 hover:bg-blue-500 text-white font-bold rounded-xl text-sm transition">Register</button>
                </form>
            </div>
        </div>

        <!-- PAGE 3: ORDER STORE (Kif tswira) -->
        <div id="page-store" class="page-section space-y-6 hidden">
            <div class="bg-dark-800 border border-dark-700 rounded-3xl p-8 max-w-xl mx-auto shadow-xl">
                <h2 class="text-2xl font-bold text-white mb-6">🛒 R4X STORE - طلب جديد</h2>
                
                <form id="order-form" onsubmit="handleOrder(event)" class="space-y-4">
                    <div class="grid grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">👤 اسم الزبون</label>
                            <input type="text" id="ord-name" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">📱 الهاتف 1</label>
                            <input type="text" id="ord-phone1" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm">
                        </div>
                    </div>
                    <div class="grid grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">📱 الهاتف 2 (اختياري)</label>
                            <input type="text" id="ord-phone2" class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">🏙️ المدينة</label>
                            <input type="text" id="ord-city" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm">
                        </div>
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">📍 العنوان</label>
                        <input type="text" id="ord-address" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm">
                    </div>
                    <div class="grid grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">🎁 كود الخصم</label>
                            <input type="text" id="ord-promo" class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm" placeholder="e.g. r4x16">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">🛍️ الخدمة المطلوبة</label>
                            <select id="ord-service" class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm">
                                <option value="SA-MP Game Server (25 DT)">SA-MP Game Server - 25 DT</option>
                                <option value="Discord Bot Custom (30 DT)">Discord Bot Custom - 30 DT</option>
                                <option value="VPS Hosting (45 DT)">VPS Hosting - 45 DT</option>
                            </select>
                        </div>
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">📝 ملاحظات</label>
                        <textarea id="ord-notes" rows="2" class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2 text-white text-sm" placeholder="A3tini tafasil ekhra..."></textarea>
                    </div>
                    <button type="submit" class="w-full py-3 bg-blue-600 hover:bg-blue-500 text-white font-bold rounded-xl text-sm transition shadow-lg shadow-blue-600/30">إرسال الطلب (Submit Order)</button>
                </form>
            </div>
        </div>

    </main>

    <script>
        function switchPage(pageId) {
            document.querySelectorAll('.page-section').forEach(el => el.classList.add('hidden'));
            document.querySelectorAll('aside a[onclick^="switchPage"]').forEach(el => el.classList.remove('bg-blue-600/10', 'text-blue-400', 'border', 'border-blue-500/20'));
            
            document.getElementById('page-' + pageId).classList.remove('hidden');
            document.getElementById('nav-' + pageId).classList.add('bg-blue-600/10', 'text-blue-400', 'border', 'border-blue-500/20');
        }

        async function handleRegister(e) {
            e.preventDefault();
            const username = document.getElementById('reg-username').value;
            const email = document.getElementById('reg-email').value;

            const res = await fetch('http://localhost:3000/api/register', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ username, email })
            });
            const data = await res.json();
            if(data.success) {
                localStorage.setItem('r4x_user', username);
                document.getElementById('user-name-display').innerText = username;
                document.getElementById('user-initial').innerText = username.charAt(0).toUpperCase();
                document.getElementById('user-status-text').innerText = 'Registered ✅';
                alert('Account registered successfully!');
                switchPage('dashboard');
            }
        }

        async function handleOrder(e) {
            e.preventDefault();
            const orderData = {
                name: document.getElementById('ord-name').value,
                phone1: document.getElementById('ord-phone1').value,
                phone2: document.getElementById('ord-phone2').value || 'None',
                city: document.getElementById('ord-city').value,
                address: document.getElementById('ord-address').value,
                promo: document.getElementById('ord-promo').value || 'None',
                service: document.getElementById('ord-service').value,
                notes: document.getElementById('ord-notes').value || 'None'
            };

            const res = await fetch('http://localhost:3000/api/order', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(orderData)
            });
            const data = await res.json();
            if(data.success) {
                alert('📦 Order sent successfully to Discord channel!');
                switchPage('dashboard');
            } else {
                alert('Error sending order.');
            }
        }

        window.onload = () => {
            const user = localStorage.getItem('r4x_user');
            if(user) {
                document.getElementById('user-name-display').innerText = user;
                document.getElementById('user-initial').innerText = user.charAt(0).toUpperCase();
                document.getElementById('user-status-text').innerText = 'Registered ✅';
            }
        }
    </script>
</body>
</html>
