<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedra Hosting - Client Dashboard</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        dark: {
                            900: '#070b14',
                            800: '#0e1626',
                            700: '#162238',
                            600: '#1e2f4d'
                        },
                        blueaccent: {
                            500: '#3b82f6',
                            600: '#2563eb',
                            discord: '#5865F2'
                        }
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-dark-900 text-gray-100 font-sans antialiased min-h-screen flex selection:bg-blue-600 selection:text-white">

    <!-- LEFT SIDEBAR -->
    <aside class="w-64 bg-dark-800 border-r border-dark-700 hidden md:flex flex-col justify-between p-4 select-none">
        <div>
            <!-- Logo / Brand -->
            <div class="flex items-center space-x-3 px-2 mb-8 mt-2">
                <div class="w-9 h-9 rounded-xl bg-gradient-to-tr from-blue-600 to-indigo-500 flex items-center justify-center shadow-lg shadow-blue-500/30">
                    <i class="fa-solid fa-server text-white text-sm"></i>
                </div>
                <span class="text-lg font-bold tracking-wide text-white">Pedra<span class="text-blue-400">Hosting</span></span>
            </div>

            <!-- Navigation Links -->
            <div class="space-y-1 text-sm font-medium">
                <a href="#" onclick="switchTab('dashboard')" id="nav-dashboard" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl bg-blue-600/10 text-blue-400 border border-blue-500/20 transition">
                    <i class="fa-solid fa-house text-base w-5"></i>
                    <span>Dashboard</span>
                </a>
                <a href="#" onclick="switchTab('services')" id="nav-services" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-solid fa-box text-base w-5"></i>
                    <span>Services</span>
                </a>
                <a href="https://dash.pedrahosting.top" target="_blank" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-solid fa-cloud text-base w-5"></i>
                    <span>VPS Panel</span>
                </a>
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="flex items-center space-x-3 px-3 py-2.5 rounded-xl text-gray-400 hover:text-white hover:bg-dark-700/50 transition">
                    <i class="fa-brands fa-discord text-base w-5"></i>
                    <span>Discord Support</span>
                </a>
            </div>
        </div>

        <!-- User Profile Bottom Widget -->
        <div class="bg-dark-900/60 border border-dark-700 rounded-2xl p-3 flex items-center justify-between">
            <div class="flex items-center space-x-3 overflow-hidden">
                <div class="w-9 h-9 rounded-full bg-blue-600 flex items-center justify-center font-bold text-white text-sm">I</div>
                <div class="truncate">
                    <div class="text-sm font-semibold text-white truncate">Iskandar</div>
                    <div class="text-xs text-blue-400 font-medium">Balance: €2,000 EUR</div>
                </div>
            </div>
            <button onclick="logout()" class="text-gray-400 hover:text-red-400 transition p-1" title="Logout"><i class="fa-solid fa-right-from-bracket"></i></button>
        </div>
    </aside>

    <!-- MAIN CONTENT AREA -->
    <main class="flex-grow flex flex-col justify-between overflow-y-auto">
        
        <!-- Top Bar -->
        <header class="border-b border-dark-700 bg-dark-800/40 backdrop-blur px-6 py-4 flex items-center justify-between">
            <div class="flex items-center space-x-4">
                <div class="text-sm text-gray-400 font-medium">
                    <i class="fa-regular fa-clock mr-1"></i> 05:12 PM &nbsp;|&nbsp; 
                    <i class="fa-regular fa-calendar-days ml-2 mr-1"></i> Saturday, October 3, 2026 &nbsp;|&nbsp; 
                    <i class="fa-solid fa-crown ml-2 mr-1 text-amber-400"></i> Member for 1 month
                </div>
            </div>
            <div class="flex items-center space-x-3">
                <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="px-3 py-1.5 bg-[#5865F2]/20 text-indigo-300 border border-[#5865F2]/30 rounded-lg text-xs font-semibold flex items-center space-x-2 hover:bg-[#5865F2] hover:text-white transition">
                    <i class="fa-brands fa-discord"></i>
                    <span>Join Discord</span>
                </a>
            </div>
        </header>

        <!-- Dynamic Content Container -->
        <div class="p-6 md:p-8 max-w-7xl mx-auto w-full flex-grow space-y-8">

            <!-- TAB 1: DASHBOARD -->
            <div id="tab-dashboard" class="space-y-8">
                <!-- Welcome Section (Matching Screenshot) -->
                <div class="bg-gradient-to-r from-dark-800 to-dark-700 border border-dark-600 rounded-3xl p-8 relative overflow-hidden shadow-xl">
                    <div class="relative z-10">
                        <div class="text-xs font-bold tracking-wider text-blue-400 uppercase mb-2">GOOD EVENING</div>
                        <h1 class="text-3xl md:text-4xl font-extrabold text-white mb-3">Welcome back, Iskandar 👋[cite: 4]</h1>
                        <p class="text-gray-400 text-sm max-w-xl">Everything about your services, invoices and support in one place.</p>
                        
                        <!-- Verified User Card inside banner -->
                        <div class="mt-6 inline-flex items-center space-x-4 bg-dark-900/90 border border-dark-600 px-5 py-3 rounded-2xl">
                            <div class="w-10 h-10 rounded-full bg-dark-700 border border-dark-600 flex items-center justify-center font-bold text-white">I</div>
                            <div>
                                <div class="text-sm font-semibold text-white flex items-center space-x-2">
                                    <span>Iskandar</span>
                                    <span class="text-xs text-pink-400">✨</span>
                                </div>
                                <div class="text-xs text-emerald-400 font-bold flex items-center space-x-1 mt-0.5">
                                    <i class="fa-solid fa-circle-check text-[10px]"></i>
                                    <span>VERIFIED</span>
                                </div>
                            </div>
                            <button onclick="alert('Opening account management...')" class="ml-8 px-4 py-1.5 bg-dark-700 hover:bg-dark-600 text-gray-200 rounded-xl text-xs font-semibold transition border border-dark-600">Manage</button>
                        </div>
                    </div>
                </div>

                <!-- 4 Bottom Cards Grid (Matching Screenshot) -->
                <div class="grid md:grid-cols-4 gap-6">
                    <!-- Card 1: Active Services -->
                    <div class="bg-dark-800 border border-dark-700 rounded-2xl p-6 flex flex-col justify-between hover:border-blue-500/40 transition">
                        <div>
                            <div class="w-10 h-10 rounded-xl bg-blue-600/10 border border-blue-500/20 text-blue-400 flex items-center justify-center mb-4">
                                <i class="fa-solid fa-box text-base"></i>
                            </div>
                            <div class="text-3xl font-extrabold text-white mb-1">0</div>
                            <div class="text-sm font-semibold text-gray-200">Active Services</div>
                            <div class="text-xs text-gray-500 mt-2">No upcoming renewals</div>
                        </div>
                    </div>

                    <!-- Card 2: Unpaid Invoices -->
                    <div class="bg-dark-800 border border-dark-700 rounded-2xl p-6 flex flex-col justify-between hover:border-amber-500/40 transition">
                        <div>
                            <div class="w-10 h-10 rounded-xl bg-amber-500/10 border border-amber-500/20 text-amber-400 flex items-center justify-center mb-4">
                                <i class="fa-solid fa-file-invoice text-base"></i>
                            </div>
                            <div class="text-3xl font-extrabold text-white mb-1">0</div>
                            <div class="text-sm font-semibold text-gray-200">Unpaid Invoices</div>
                            <div class="text-xs text-gray-500 mt-2">Nothing outstanding</div>
                        </div>
                    </div>

                    <!-- Card 3: Open Tickets -->
                    <div class="bg-dark-800 border border-emerald-500/40 rounded-2xl p-6 flex flex-col justify-between shadow-lg shadow-emerald-950/20">
                        <div>
                            <div class="flex items-center justify-between mb-4">
                                <div class="w-10 h-10 rounded-xl bg-emerald-500/10 border border-emerald-500/20 text-emerald-400 flex items-center justify-center">
                                    <i class="fa-solid fa-headset text-base"></i>
                                </div>
                                <i class="fa-solid fa-arrow-up-right-from-square text-gray-500 text-xs"></i>
                            </div>
                            <div class="text-3xl font-extrabold text-white mb-1">0</div>
                            <div class="text-sm font-semibold text-gray-200">Open Tickets</div>
                            <div class="text-xs text-emerald-400 mt-2 font-medium">All caught up</div>
                        </div>
                    </div>

                    <!-- Card 4: Credits / Discord Community -->
                    <div class="bg-dark-800 border border-dark-700 rounded-2xl p-6 flex flex-col justify-between hover:border-blue-500/40 transition">
                        <div>
                            <div class="flex items-center justify-between mb-4">
                                <div class="w-10 h-10 rounded-xl bg-indigo-500/10 border border-indigo-500/20 text-indigo-400 flex items-center justify-center">
                                    <i class="fa-solid fa-wallet text-base"></i>
                                </div>
                                <i class="fa-regular fa-eye-slash text-gray-500 text-xs cursor-pointer"></i>
                            </div>
                            <div class="text-2xl font-extrabold text-white mb-1 font-mono">€2,000</div>
                            <div class="text-sm font-semibold text-gray-200">Credits</div>
                            <a href="https://dash.pedrahosting.top" target="_blank" class="text-xs text-blue-400 hover:underline mt-2 inline-block font-medium">Deposit more</a>
                        </div>
                    </div>
                </div>

                <!-- Discord Community Banner Card -->
                <div class="bg-dark-800 border border-dark-700 rounded-2xl p-6 flex flex-col md:flex-row items-center justify-between gap-4">
                    <div class="flex items-center space-x-4">
                        <div class="w-12 h-12 rounded-2xl bg-[#5865F2] flex items-center justify-center text-white text-2xl shadow-lg shadow-[#5865F2]/30 flex-shrink-0">
                            <i class="fa-brands fa-discord"></i>
                        </div>
                        <div>
                            <h3 class="text-lg font-bold text-white">Discord Community</h3>
                            <p class="text-sm text-gray-400">Need instant technical support or network status alerts? Join our Discord community.</p>
                        </div>
                    </div>
                    <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="px-6 py-3 bg-[#5865F2] hover:bg-[#4752C4] text-white font-medium rounded-xl text-sm transition shadow-lg shadow-[#5865F2]/20 whitespace-nowrap flex items-center space-x-2">
                        <span>Join Discord</span>
                        <i class="fa-solid fa-arrow-right text-xs"></i>
                    </a>
                </div>
            </div>

            <!-- TAB 2: SERVICES -->
            <div id="tab-services" class="space-y-6 hidden">
                <div class="flex justify-between items-center">
                    <div>
                        <h2 class="text-2xl font-bold text-white">Services</h2>
                        <p class="text-sm text-gray-400">Manage your active VPS and game server nodes.</p>
                    </div>
                    <a href="https://dash.pedrahosting.top" target="_blank" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 text-white rounded-xl text-sm font-semibold transition">Open VPS Panel</a>
                </div>
                
                <div class="bg-dark-800 border border-dark-700 rounded-2xl p-6 flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                    <div class="flex items-center space-x-4">
                        <div class="w-12 h-12 rounded-2xl bg-blue-600/20 border border-blue-500/30 text-blue-400 flex items-center justify-center text-xl">
                            <i class="fa-solid fa-server"></i>
                        </div>
                        <div>
                            <h4 class="text-base font-bold text-white">VPS #1 #867</h4>
                            <p class="text-xs text-gray-400">Services: Root Server - Every month &bull; Expires: 28 Sep 2026</p>
                        </div>
                    </div>
                    <div class="flex items-center space-x-3">
                        <span class="px-3 py-1 rounded-full text-xs font-semibold bg-red-500/10 text-red-400 border border-red-500/20">Cancelled</span>
                        <a href="https://dash.pedrahosting.top" target="_blank" class="p-2 bg-dark-700 hover:bg-dark-600 text-white rounded-xl transition"><i class="fa-solid fa-chevron-right text-xs"></i></a>
                    </div>
                </div>
            </div>

        </div>

        <!-- Footer -->
        <footer class="border-t border-dark-700 bg-dark-800/30 py-4 px-6 text-center text-xs text-gray-500">
            <p>&copy; 2026 Pedra Hosting. All rights reserved. &bull; <a href="https://discord.gg/Spbt6mxzFD" target="_blank" class="text-blue-400 hover:underline">Discord Support</a></p>
        </footer>

    </main>

    <!-- JavaScript Navigation Script -->
    <script>
        function switchTab(tabName) {
            document.getElementById('tab-dashboard').classList.add('hidden');
            document.getElementById('tab-services').classList.add('hidden');
            document.getElementById('nav-dashboard').classList.remove('bg-blue-600/10', 'text-blue-400', 'border', 'border-blue-500/20');
            document.getElementById('nav-services').classList.remove('bg-blue-600/10', 'text-blue-400', 'border', 'border-blue-500/20');

            if (tabName === 'dashboard') {
                document.getElementById('tab-dashboard').classList.remove('hidden');
                document.getElementById('nav-dashboard').classList.add('bg-blue-600/10', 'text-blue-400', 'border', 'border-blue-500/20');
            } else if (tabName === 'services') {
                document.getElementById('tab-services').classList.remove('hidden');
                document.getElementById('nav-services').classList.add('bg-blue-600/10', 'text-blue-400', 'border', 'border-blue-500/20');
            }
        }

        function logout() {
            alert('Logged out successfully.');
            location.reload();
        }
    </script>
</body>
</html>
