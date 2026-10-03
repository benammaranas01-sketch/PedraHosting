<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedra Hosting - Register & Dashboard</title>
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
                    <i class="fa-solid fa-server text-white text-sm"></i>
                </div>
                <span class="text-lg font-bold tracking-wide text-white">Pedra<span class="text-blue-400">Hosting</span></span>
            </div>

            <div class="space-y-1 text-sm font-medium">
                <a href="#" onclick="switchPage('dashboard')" id="nav-dashboard" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl bg-blue-600/10 text-blue-400 border border-blue-500/20 transition">
                    <i class="fa-solid fa-house text-base w-5"></i><span>Dashboard</span>
                </a>
                <a href="#" onclick="switchPage('register')" id="nav-register" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-solid fa-user-plus text-base w-5"></i><span>Register Account</span>
                </a>
                <a href="#" onclick="switchPage('store')" id="nav-store" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-solid fa-cart-shopping text-base w-5"></i><span>Order Server</span>
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
                <h1 class="text-3xl font-extrabold text-white mb-2">Welcome to Pedra Hosting 🚀</h1>
                <p class="text-gray-400 text-sm">Create an account using your Username & Email to manage your game servers.</p>
                <div class="mt-6">
                    <button onclick="switchPage('register')" class="px-5 py-2.5 bg-blue-600 hover:bg-blue-500 text-white font-semibold rounded-xl text-sm transition">Register Now</button>
                </div>
            </div>
        </div>

        <!-- PAGE 2: REGISTER -->
        <div id="page-register" class="page-section space-y-6 hidden">
            <div class="bg-dark-800 border border-dark-700 rounded-3xl p-8 max-w-md mx-auto shadow-xl">
                <h2 class="text-2xl font-bold text-white mb-6">Create Your Account</h2>
                
                <form id="register-form" onsubmit="handleRegister(event)" class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">Username</label>
                        <input type="text" id="reg-username" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-blue-500" placeholder="e.g. Iskandar">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">Email Address</label>
                        <input type="email" id="reg-email" required class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-blue-500" placeholder="name@example.com">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-gray-400 uppercase mb-1">Discord Tag (Optional - for notifications)</label>
                        <input type="text" id="reg-discord" class="w-full bg-dark-900 border border-dark-600 rounded-xl px-4 py-2.5 text-white text-sm focus:outline-none focus:border-blue-500" placeholder="e.g. username#1234">
                    </div>
                    <button type="submit" class="w-full py-3 bg-blue-600 hover:bg-blue-500 text-white font-bold rounded-xl text-sm transition shadow-lg shadow-blue-600/30">Register Account</button>
                </form>
            </div>
        </div>

        <!-- PAGE 3: ORDER STORE -->
        <div id="page-store" class="page-section space-y-6 hidden">
            <h2 class="text-2xl font-bold text-white">Order SA-MP Server (€3.99)</h2>
            <div class="bg-dark-800 border border-dark-700 rounded-2xl p-6 max-w-md">
                <p class="text-gray-400 text-sm mb-4">Deploy your game server instantly after registration.</p>
                <button onclick="orderServer()" class="w-full py-2.5 bg-emerald-600 hover:bg-emerald-500 text-white font-semibold rounded-xl text-sm transition">Deploy Server Now</button>
            </div>
        </div>

    </main>

    <!-- SCRIPT -->
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
            const discord = document.getElementById('reg-discord').value;

            const res = await fetch('http://localhost:3000/api/register', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ username, email, discord })
            });

            const data = await res.json();
            if (data.success) {
                localStorage.setItem('pedra_user', username);
                document.getElementById('user-name-display').innerText = username;
                document.getElementById('user-initial').innerText = username.charAt(0).toUpperCase();
                document.getElementById('user-status-text').innerText = 'Registered ✅';
                alert('Account created successfully!');
                switchPage('dashboard');
            } else {
                alert('Error: ' + data.error);
            }
        }

        function orderServer() {
            const user = localStorage.getItem('pedra_user');
            if (!user) {
                alert('Please register an account first!');
                switchPage('register');
                return;
            }
            alert(`Server ordered successfully for ${user}! Check your details.`);
        }

        window.onload = () => {
            const savedUser = localStorage.getItem('pedra_user');
            if (savedUser) {
                document.getElementById('user-name-display').innerText = savedUser;
                document.getElementById('user-initial').innerText = savedUser.charAt(0).toUpperCase();
                document.getElementById('user-status-text').innerText = 'Registered ✅';
            }
        }
    </script>
</body>
</html>
