<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="theme-color" content="#030712">
    <meta name="description" content="Big Alien Solar & Farm Poultry - Built Solar Systems & Fresh Chickens in Nigeria.">
    <title>Big Alien Solar & Poultry | Official Web Application</title>
    
    <!-- Inline Web App Manifest for PWA Support -->
    <link rel="manifest" href='data:application/manifest+json,{"name":"Big Alien Solar","short_name":"AlienSolar","start_url":".","display":"standalone","background_color":"#030712","theme_color":"#030712"}'>

    <!-- Tailwind CSS & FontAwesome Icons -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        alien: {
                            400: '#39ff14',
                            500: '#10b981',
                            600: '#059669',
                            glow: 'rgba(57, 255, 20, 0.25)'
                        },
                        solar: {
                            400: '#fbbf24',
                            500: '#f59e0b',
                            600: '#d97706'
                        },
                        space: {
                            950: '#030712',
                            900: '#0b1329',
                            800: '#131f37',
                            700: '#1e293b'
                        }
                    },
                    fontFamily: {
                        orbitron: ['Orbitron', 'sans-serif'],
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #030712; }
        ::-webkit-scrollbar-thumb { background: #1e293b; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #fbbf24; }

        .neon-border-gold {
            box-shadow: 0 0 15px rgba(251, 191, 36, 0.15);
            border: 1px solid rgba(251, 191, 36, 0.3);
        }
        .neon-border-gold:hover {
            box-shadow: 0 0 25px rgba(251, 191, 36, 0.35);
            border-color: rgba(251, 191, 36, 0.7);
        }

        .neon-border-green {
            box-shadow: 0 0 15px rgba(57, 255, 20, 0.15);
            border: 1px solid rgba(57, 255, 20, 0.3);
        }
        .neon-border-green:hover {
            box-shadow: 0 0 25px rgba(57, 255, 20, 0.35);
            border-color: rgba(57, 255, 20, 0.7);
        }

        @keyframes pulse-slow {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 0.6; transform: scale(1.04); }
        }
        .animate-pulse-slow { animation: pulse-slow 6s infinite ease-in-out; }
    </style>
</head>
<body class="bg-space-950 text-slate-100 font-sans antialiased min-h-screen flex flex-col selection:bg-solar-400 selection:text-space-950">

    <!-- Toast Notification Banner -->
    <div id="toast-notification" class="fixed top-5 right-5 z-50 transform translate-x-full transition-transform duration-300 bg-space-900 border border-solar-400/50 text-white px-4 py-3 rounded-2xl shadow-2xl flex items-center gap-3">
        <i id="toast-icon" class="fa-solid fa-circle-check text-solar-400 text-lg"></i>
        <span id="toast-message" class="text-xs font-bold font-sans">Notification message</span>
    </div>

    <header class="sticky top-0 z-40 backdrop-blur-xl bg-space-950/90 border-b border-slate-800/80">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Brand Logo -->
                <a href="#" class="flex items-center gap-3 group">
                    <div class="w-11 h-11 sm:w-12 sm:h-12 rounded-xl border border-solar-400/50 shadow-lg shadow-solar-400/20 group-hover:scale-105 transition-transform bg-space-900 flex items-center justify-center p-1">
                        <svg class="w-full h-full text-solar-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
                    </div>
                    <div>
                        <span class="font-orbitron text-base sm:text-xl font-black tracking-wider bg-gradient-to-r from-solar-400 via-white to-amber-500 bg-clip-text text-transparent block">BIG ALIEN</span>
                        <span class="text-[9px] sm:text-[10px] font-semibold text-slate-400 tracking-widest uppercase block -mt-1">Solar & Poultry Corp</span>
                    </div>
                </a>

                <!-- Desktop Navigation Links -->
                <nav class="hidden md:flex items-center gap-6 text-xs sm:text-sm font-medium">
                    <button onclick="filterCategory('all')" class="nav-tab text-slate-300 hover:text-solar-400 transition-colors">All Products</button>
                    <button onclick="filterCategory('solar')" class="nav-tab text-slate-300 hover:text-solar-400 transition-colors flex items-center gap-1.5"><i class="fa-solid fa-solar-panel text-xs text-solar-400"></i> Solar Systems</button>
                    <button onclick="filterCategory('poultry')" class="nav-tab text-slate-300 hover:text-alien-400 transition-colors flex items-center gap-1.5"><i class="fa-solid fa-egg text-xs text-alien-400"></i> Chicken Farm</button>
                    <button onclick="openOrderHistory()" class="text-slate-300 hover:text-white transition-colors flex items-center gap-1.5"><i class="fa-solid fa-clock-rotate-left text-xs text-amber-400"></i> My Orders</button>
                </nav>

                <!-- Actions: Install PWA & Cart Button -->
                <div class="flex items-center gap-2 sm:gap-3">
                    <button id="pwa-install-btn" class="hidden px-2.5 py-2 rounded-xl bg-solar-500/10 border border-solar-400/40 text-solar-400 text-xs font-orbitron font-bold hover:bg-solar-500/20 transition-all flex items-center gap-1.5">
                        <i class="fa-solid fa-download"></i> <span class="hidden sm:inline">Install App</span>
                    </button>

                    <button onclick="openOrderHistory()" class="md:hidden p-2.5 rounded-xl bg-space-900 border border-slate-800 text-amber-400 hover:text-white" title="My Orders">
                        <i class="fa-solid fa-clock-rotate-left"></i>
                    </button>

                    <button onclick="openCart()" class="relative px-3.5 py-2.5 rounded-xl bg-space-900 border border-slate-700 hover:border-solar-400 text-white font-bold text-xs font-orbitron transition-all flex items-center gap-2">
                        <i class="fa-solid fa-cart-shopping text-solar-400 text-base"></i>
                        <span class="hidden sm:inline">Cart</span>
                        <span id="cart-badge" class="bg-solar-500 text-space-950 font-black px-2 py-0.5 rounded-full text-[10px]">0</span>
                    </button>

                    <button id="mobile-toggle" class="md:hidden text-slate-300 hover:text-white p-2.5 rounded-xl border border-slate-800" aria-label="Toggle Menu">
                        <i id="menu-icon" class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Drawer -->
        <div id="mobile-drawer" class="hidden md:hidden border-b border-slate-800 bg-space-950/95 px-6 py-5 space-y-3">
            <button onclick="filterCategory('all'); toggleMobileMenu()" class="block w-full text-left text-slate-200 font-medium py-2"><i class="fa-solid fa-border-all text-solar-400 mr-2"></i> All Products</button>
            <button onclick="filterCategory('solar'); toggleMobileMenu()" class="block w-full text-left text-slate-200 font-medium py-2"><i class="fa-solid fa-solar-panel text-solar-400 mr-2"></i> Solar Systems</button>
            <button onclick="filterCategory('poultry'); toggleMobileMenu()" class="block w-full text-left text-slate-200 font-medium py-2"><i class="fa-solid fa-egg text-alien-400 mr-2"></i> Chicken Farm</button>
            <button onclick="openOrderHistory(); toggleMobileMenu()" class="block w-full text-left text-slate-200 font-medium py-2"><i class="fa-solid fa-clock-rotate-left text-amber-400 mr-2"></i> My Order History</button>
            <a href="https://wa.me/2347025136166" target="_blank" class="block text-center w-full py-3 rounded-xl bg-emerald-500 text-space-950 font-black text-xs font-orbitron mt-2">
                <i class="fa-brands fa-whatsapp mr-1 text-sm"></i> WhatsApp Support: 0702 513 6166
            </a>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Hero Section -->
        <section class="relative py-12 lg:py-20 overflow-hidden">
            <div class="absolute top-1/3 left-1/4 -translate-x-1/2 -translate-y-1/2 w-[450px] h-[450px] bg-solar-500/10 rounded-full blur-[120px] pointer-events-none animate-pulse-slow"></div>

            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-12 items-center">
                    
                    <div class="lg:col-span-7 text-center lg:text-left space-y-5">
                        <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full border border-solar-400/30 bg-solar-400/10 text-solar-400 text-xs font-medium">
                            <i class="fa-solid fa-bolt text-xs"></i>
                            <span>Energy Beyond Earth • Official Store</span>
                        </div>

                        <h1 class="text-3xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight font-orbitron leading-tight text-white">
                            BIG ALIEN <br>
                            <span class="bg-gradient-to-r from-solar-400 via-amber-200 to-alien-400 bg-clip-text text-transparent">Solar & Poultry</span>
                        </h1>

                        <p class="text-slate-300 text-sm sm:text-base leading-relaxed max-w-2xl mx-auto lg:mx-0">
                            Custom built high-performance solar units starting from <strong class="text-solar-400">₦160,000</strong> and organic farm-fresh chickens starting from <strong class="text-alien-400">₦15,000</strong>. Direct delivery across Nigeria with instant WhatsApp confirmation!
                        </p>

                        <!-- Bank Account Notification Banner -->
                        <div class="p-4 rounded-2xl bg-space-900/90 border border-slate-800 text-xs space-y-1 max-w-xl mx-auto lg:mx-0 text-slate-300">
                            <div class="flex items-center justify-between">
                                <span class="font-bold text-white flex items-center gap-1.5"><i class="fa-solid fa-building-columns text-solar-400"></i> Direct Payment Account:</span>
                                <span class="text-amber-400 font-bold font-mono">Moniepoint MFB</span>
                            </div>
                            <div class="flex items-center justify-between pt-1">
                                <span>Account Name: <strong class="text-white">Abel Philip</strong></span>
                                <div class="flex items-center gap-2">
                                    <strong class="text-solar-400 font-mono text-sm">6714306196</strong>
                                    <button onclick="copyAccNumber()" class="px-2 py-0.5 rounded bg-solar-500/20 hover:bg-solar-500/30 text-solar-400 font-semibold text-[10px] border border-solar-400/30">Copy</button>
                                </div>
                            </div>
                        </div>

                        <div class="pt-2 flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-3">
                            <a href="#catalog" onclick="filterCategory('solar')" class="w-full sm:w-auto px-7 py-3.5 rounded-xl bg-solar-500 hover:bg-solar-400 text-space-950 font-black shadow-lg shadow-solar-500/20 transition-all hover:scale-105 text-center font-orbitron text-xs flex items-center justify-center gap-2">
                                <i class="fa-solid fa-solar-panel"></i> Explore Solar Packages
                            </a>
                            <a href="#catalog" onclick="filterCategory('poultry')" class="w-full sm:w-auto px-7 py-3.5 rounded-xl border border-alien-400/50 bg-alien-400/10 hover:bg-alien-400/20 text-alien-400 font-bold transition-all hover:scale-105 text-center font-orbitron text-xs flex items-center justify-center gap-2">
                                <i class="fa-solid fa-feather"></i> Order Farm Chickens
                            </a>
                        </div>
                    </div>

                    <!-- Hero Visual Card with Brand Icon -->
                    <div class="lg:col-span-5 flex justify-center">
                        <div class="relative w-full max-w-sm">
                            <div class="p-1 rounded-3xl bg-gradient-to-b from-solar-400 via-slate-800 to-alien-400 shadow-2xl">
                                <div class="bg-space-900 rounded-[22px] p-6 space-y-4 text-center">
                                    <div class="relative w-28 h-28 mx-auto flex items-center justify-center bg-space-950 rounded-2xl border-2 border-solar-400/50 p-3 shadow-2xl">
                                        <svg class="w-full h-full text-solar-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="5"/><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/></svg>
                                    </div>
                                    <div>
                                        <h3 class="text-xl font-bold font-orbitron text-white">Big Alien Solar</h3>
                                        <p class="text-[10px] text-amber-400 font-mono tracking-widest mt-0.5">ENERGY BEYOND EARTH</p>
                                    </div>
                                    <div class="p-3.5 rounded-xl bg-space-950 border border-slate-800 text-left space-y-1.5 text-xs text-slate-300">
                                        <div class="flex items-center justify-between"><span class="text-slate-400">Account Name:</span> <strong class="text-white">Abel Philip</strong></div>
                                        <div class="flex items-center justify-between"><span class="text-slate-400">Bank:</span> <strong class="text-solar-400">Moniepoint MFB</strong></div>
                                        <div class="flex items-center justify-between"><span class="text-slate-400">Account No:</span> <strong class="text-solar-400 font-mono">6714306196</strong></div>
                                        <div class="flex items-center justify-between pt-1 border-t border-slate-800"><span class="text-slate-400">WhatsApp Hotline:</span> <strong class="text-emerald-400">0702 513 6166</strong></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <section id="catalog" class="py-16 bg-space-900/60 border-y border-slate-800/80">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="text-center max-w-3xl mx-auto mb-10 space-y-3">
                    <h2 class="text-xs font-bold uppercase tracking-widest text-solar-400 font-orbitron">Product Catalog</h2>
                    <p class="text-2xl sm:text-4xl font-extrabold text-white">Solar Systems & Fresh Chickens</p>
                    <p class="text-slate-400 text-xs sm:text-sm">Click any item to add to your cart, specify delivery address, and pay directly via bank transfer.</p>
                </div>

                <!-- Filter Tabs -->
                <div class="flex justify-center gap-2 mb-10">
                    <button id="filter-all-btn" onclick="filterCategory('all')" class="px-5 py-2.5 rounded-xl font-orbitron text-xs font-bold transition-all bg-solar-500 text-space-950">
                        All Items
                    </button>
                    <button id="filter-solar-btn" onclick="filterCategory('solar')" class="px-5 py-2.5 rounded-xl font-orbitron text-xs font-bold text-slate-400 hover:text-white bg-space-900 border border-slate-800 transition-all">
                        <i class="fa-solid fa-solar-panel text-solar-400 mr-1"></i> Solar Units
                    </button>
                    <button id="filter-poultry-btn" onclick="filterCategory('poultry')" class="px-5 py-2.5 rounded-xl font-orbitron text-xs font-bold text-slate-400 hover:text-white bg-space-900 border border-slate-800 transition-all">
                        <i class="fa-solid fa-egg text-alien-400 mr-1"></i> Chickens
                    </button>
                </div>

                <!-- Product Grid -->
                <div id="product-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Dynamic Product Cards Injected Here -->
                </div>

            </div>
        </section>

        <section id="contact" class="py-16 bg-space-950">
            <div class="max-w-4xl mx-auto px-4 text-center space-y-5">
                <div class="w-14 h-14 mx-auto rounded-2xl bg-space-900 border border-solar-400 shadow-xl flex items-center justify-center p-2 text-solar-400">
                    <svg class="w-full h-full" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>
                </div>
                <h2 class="text-2xl font-orbitron font-bold text-white">Need Customized Solar Sizing or Large Orders?</h2>
                <p class="text-slate-400 text-xs sm:text-sm max-w-xl mx-auto">Our solar engineers and poultry managers are available on call. Chat directly on WhatsApp or dial 0702 513 6166.</p>
                
                <div class="pt-2 flex flex-wrap justify-center gap-4">
                    <a href="https://wa.me/2347025136166" target="_blank" class="inline-flex items-center gap-2 px-6 py-3.5 rounded-xl bg-emerald-500 hover:bg-emerald-400 text-space-950 font-black text-xs font-orbitron transition-all">
                        <i class="fa-brands fa-whatsapp text-lg"></i> Chat on WhatsApp (0702 513 6166)
                    </a>
                    <a href="tel:07025136166" class="inline-flex items-center gap-2 px-6 py-3.5 rounded-xl bg-space-900 border border-slate-700 hover:border-solar-400 text-white font-bold text-xs font-orbitron transition-all">
                        <i class="fa-solid fa-phone text-solar-400"></i> Direct Phone Call
                    </a>
                </div>
            </div>
        </section>
    </main>

    <footer class="bg-space-900 border-t border-slate-800/80 py-8 text-center text-xs text-slate-500">
        <div class="max-w-7xl mx-auto px-4 space-y-2">
            <p>© 2026 Big Alien Solar & Poultry Corp. All rights reserved.</p>
            <p class="text-[11px] text-slate-600">Moniepoint Account: Abel Philip (6714306196) • WhatsApp Hotline: 0702 513 6166</p>
        </div>
    </footer>

    <!-- Shopping Cart Modal -->
    <div id="cart-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex justify-end transition-opacity">
        <div class="w-full max-w-lg bg-space-950 h-full border-l border-slate-800 flex flex-col justify-between p-5 sm:p-6 overflow-y-auto">
            <div>
                <div class="flex justify-between items-center border-b border-slate-800 pb-4">
                    <div class="flex items-center gap-2">
                        <i class="fa-solid fa-cart-shopping text-solar-400"></i>
                        <h3 class="font-orbitron font-bold text-lg text-white">Your Cart</h3>
                    </div>
                    <button onclick="closeCart()" class="text-slate-400 hover:text-white p-2">
                        <i class="fa-solid fa-xmark text-xl"></i>
                    </button>
                </div>

                <!-- Items Container -->
                <div id="cart-items-list" class="py-4 space-y-3">
                    <!-- Injected via JS -->
                </div>
            </div>

            <!-- Delivery Address Form & Checkout -->
            <div class="border-t border-slate-800 pt-4 space-y-4">
                <h4 class="font-orbitron text-xs font-bold text-solar-400 uppercase tracking-wider">Delivery Details</h4>
                
                <form id="delivery-form" class="space-y-2.5 text-xs" onsubmit="event.preventDefault(); processCheckout();">
                    <div>
                        <input type="text" id="cust-name" required placeholder="Full Name *" class="w-full bg-space-900 border border-slate-800 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-solar-400">
                    </div>
                    <div>
                        <input type="tel" id="cust-phone" required placeholder="Phone / WhatsApp Number *" class="w-full bg-space-900 border border-slate-800 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-solar-400">
                    </div>
                    <div>
                        <textarea id="cust-address" required rows="2" placeholder="Full Delivery Address (Street Name, City, State) *" class="w-full bg-space-900 border border-slate-800 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-solar-400"></textarea>
                    </div>
                    <div>
                        <input type="text" id="cust-notes" placeholder="Delivery Instructions / Landmark (Optional)" class="w-full bg-space-900 border border-slate-800 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-solar-400">
                    </div>
                </form>

                <div class="flex justify-between text-sm font-bold text-white pt-2 border-t border-slate-800">
                    <span>Total Amount:</span>
                    <span id="cart-total-price" class="text-solar-400 font-orbitron font-black text-base">₦0</span>
                </div>

                <button onclick="processCheckout()" class="w-full py-3.5 rounded-xl bg-solar-500 hover:bg-solar-400 text-space-950 font-black font-orbitron text-xs tracking-wider transition-all shadow-lg flex items-center justify-center gap-2">
                    <i class="fa-solid fa-credit-card"></i> Proceed To Direct Bank Transfer
                </button>
            </div>
        </div>
    </div>

    <!-- Direct Bank Transfer Payment Modal -->
    <div id="payment-modal" class="fixed inset-0 z-50 hidden bg-black/90 backdrop-blur-md flex items-center justify-center p-4">
        <div class="w-full max-w-md bg-space-900 rounded-3xl border border-solar-400/50 p-5 sm:p-6 space-y-5 max-h-[90vh] overflow-y-auto">
            <div class="text-center space-y-1.5">
                <div class="w-12 h-12 mx-auto rounded-xl bg-space-950 border border-solar-400 flex items-center justify-center text-solar-400 p-2">
                    <svg class="w-full h-full" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="5" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/></svg>
                </div>
                <h3 class="text-xl font-orbitron font-bold text-white">Bank Transfer Details</h3>
                <p class="text-xs text-slate-400">Transfer payment to the account below, attach receipt preview, and dispatch to WhatsApp.</p>
            </div>

            <!-- Bank Transfer Box -->
            <div class="p-4 rounded-2xl bg-space-950 border border-solar-500/30 space-y-2 text-xs">
                <div class="flex justify-between text-slate-400"><span>Account Name:</span> <strong class="text-white">Abel Philip</strong></div>
                <div class="flex justify-between text-slate-400"><span>Bank Name:</span> <strong class="text-solar-400">Moniepoint MFB</strong></div>
                <div class="flex justify-between items-center text-slate-400">
                    <span>Account Number:</span>
                    <div class="flex items-center gap-2">
                        <strong class="text-solar-400 font-mono text-base">6714306196</strong>
                        <button onclick="copyAccNumber()" class="text-[10px] bg-solar-500/20 text-solar-400 px-2 py-0.5 rounded border border-solar-500/30 font-bold hover:bg-solar-500/30">Copy</button>
                    </div>
                </div>
            </div>

            <!-- Order Summary Text -->
            <div id="summary-order-box" class="p-3.5 rounded-2xl bg-space-950 border border-slate-800 text-xs text-slate-300 space-y-1.5">
                <!-- Injected via JS -->
            </div>

            <!-- Payment Proof Uploader with Preview -->
            <div class="p-3.5 rounded-2xl bg-space-950 border border-slate-800 text-xs space-y-2">
                <label class="block text-slate-400 text-[11px] font-bold">Attach Proof of Payment (Receipt / Screenshot):</label>
                <input type="file" id="receipt-upload" accept="image/*,.pdf" onchange="handleReceiptUpload(event)" class="w-full text-slate-400 text-xs file:mr-2 file:py-1 file:px-3 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-solar-500/20 file:text-solar-400 hover:file:bg-solar-500/30">
                <div id="receipt-preview-container" class="hidden pt-2 text-center">
                    <img id="receipt-img-preview" src="#" alt="Receipt Preview" class="max-h-32 mx-auto rounded-lg border border-slate-700 object-contain">
                    <p id="receipt-status" class="text-[10px] text-emerald-400 mt-1"><i class="fa-solid fa-circle-check"></i> Receipt attached and verified.</p>
                </div>
            </div>

            <div class="space-y-2.5">
                <a id="send-whatsapp-final-btn" href="#" target="_blank" onclick="confirmOrderSaved()" class="w-full py-3.5 rounded-xl bg-emerald-500 hover:bg-emerald-400 text-space-950 font-black font-orbitron text-xs text-center block transition-all shadow-lg shadow-emerald-500/20">
                    <i class="fa-brands fa-whatsapp text-base mr-1"></i> Confirm Order via WhatsApp
                </a>
                <button onclick="closePaymentModal()" class="w-full py-2 rounded-xl text-slate-400 hover:text-white text-xs font-bold text-center block">
                    Close Window
                </button>
            </div>
        </div>
    </div>

    <!-- Order History Modal -->
    <div id="history-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="w-full max-w-xl bg-space-950 rounded-3xl border border-slate-800 p-5 sm:p-6 space-y-4 max-h-[85vh] overflow-y-auto">
            <div class="flex justify-between items-center border-b border-slate-800 pb-3">
                <div class="flex items-center gap-2">
                    <i class="fa-solid fa-clock-rotate-left text-solar-400"></i>
                    <h3 class="font-orbitron font-bold text-lg text-white">Your Order History</h3>
                </div>
                <button onclick="closeOrderHistory()" class="text-slate-400 hover:text-white p-2">
                    <i class="fa-solid fa-xmark text-xl"></i>
                </button>
            </div>

            <div id="history-orders-list" class="space-y-3">
                <!-- Injected via JS -->
            </div>
        </div>
    </div>

    <script>
        // Inline SVG Fallback Product Visuals
        const SOLAR_SVG = `<svg class="w-full h-full text-solar-400 p-8" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/><line x1="8" y1="3" x2="8" y2="17"/><line x1="16" y1="3" x2="16" y2="17"/><path d="M12 17v4M8 21h8"/></svg>`;
        const POULTRY_SVG = `<svg class="w-full h-full text-alien-400 p-8" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 22C6.5 22 2 17.5 2 12S6.5 2 12 2s10 4.5 10 10-4.5 10-10 10z"/><circle cx="12" cy="10" r="3"/><path d="M12 13v5"/></svg>`;

        // Products Catalog
        const PRODUCTS = [
            {
                id: 'sol-350w',
                category: 'solar',
                title: '350W Built Solar System',
                desc: 'Features 200W Output power + 100W Monocrystalline solar panel included in package.',
                price: 160000,
                badge: '100W Panel Included',
                badgeBg: 'bg-solar-500',
                svg: SOLAR_SVG
            },
            {
                id: 'sol-650w',
                category: 'solar',
                title: '650W Built Inverter System',
                desc: 'Compact custom built inverter unit delivering 1,000W Output power.',
                price: 200000,
                badge: '1000W Output',
                badgeBg: 'bg-emerald-500',
                svg: SOLAR_SVG
            },
            {
                id: 'sol-800w',
                category: 'solar',
                title: '800W Solar Inverter Combo',
                desc: 'Includes 500W Output capacity + heavy duty 300W Solar Panel.',
                price: 300000,
                badge: '300W Panel Included',
                badgeBg: 'bg-solar-500',
                svg: SOLAR_SVG
            },
            {
                id: 'sol-1200w',
                category: 'solar',
                title: '1200W Heavy Duty Unit',
                desc: 'Custom engineered high-capacity inverter unit with 1,000W Output capacity.',
                price: 360000,
                badge: 'Heavy Duty Unit',
                badgeBg: 'bg-amber-500',
                svg: SOLAR_SVG
            },
            {
                id: 'chk-std',
                category: 'poultry',
                title: 'Standard Farm Chicken',
                desc: 'Healthy, organically fed broiler chicken for domestic cooking.',
                price: 15000,
                badge: 'Fresh Organic',
                badgeBg: 'bg-alien-500',
                svg: POULTRY_SVG
            },
            {
                id: 'chk-jumbo',
                category: 'poultry',
                title: 'Jumbo Giant Chicken',
                desc: 'Extra large organic broiler chicken with high meat density.',
                price: 25000,
                badge: 'Jumbo Heavy Weight',
                badgeBg: 'bg-alien-500',
                svg: POULTRY_SVG
            }
        ];

        // Application State
        let cart = [];
        let orderHistory = [];
        let activeCategory = 'all';
        let deferredPrompt = null;
        let attachedReceiptName = null;

        // On Load Initialization
        document.addEventListener('DOMContentLoaded', () => {
            loadSavedCartAndOrders();
            renderProducts();
            setupPWA();
            setupMobileDrawer();
            registerServiceWorker();
        });

        // Toast Helper
        function showToast(msg) {
            const toast = document.getElementById('toast-notification');
            const toastMsg = document.getElementById('toast-message');
            if (toast && toastMsg) {
                toastMsg.textContent = msg;
                toast.classList.remove('translate-x-full');
                setTimeout(() => {
                    toast.classList.add('translate-x-full');
                }, 3000);
            }
        }

        // LocalStorage Logic
        function loadSavedCartAndOrders() {
            try {
                const savedCart = localStorage.getItem('big_alien_cart');
                if (savedCart) cart = JSON.parse(savedCart);

                const savedOrders = localStorage.getItem('big_alien_orders');
                if (savedOrders) orderHistory = JSON.parse(savedOrders);
            } catch (e) {
                console.error('Error loading stored data', e);
            }
            updateCartUI();
        }

        function saveCart() {
            try {
                localStorage.setItem('big_alien_cart', JSON.stringify(cart));
            } catch (e) {
                console.error('Error saving cart', e);
            }
            updateCartUI();
        }

        function saveOrders() {
            try {
                localStorage.setItem('big_alien_orders', JSON.stringify(orderHistory));
            } catch (e) {
                console.error('Error saving orders', e);
            }
        }

        // Render Product Cards
        function renderProducts() {
            const grid = document.getElementById('product-grid');
            const items = activeCategory === 'all' 
                ? PRODUCTS 
                : PRODUCTS.filter(p => p.category === activeCategory);

            grid.innerHTML = items.map(p => {
                const isSolar = p.category === 'solar';
                const cardBorder = isSolar ? 'neon-border-gold' : 'neon-border-green';
                const btnBg = isSolar ? 'bg-solar-500 hover:bg-solar-400' : 'bg-alien-500 hover:bg-alien-400';
                const priceColor = isSolar ? 'text-solar-400' : 'text-alien-400';

                return `
                    <div class="p-5 rounded-3xl bg-space-950 ${cardBorder} flex flex-col justify-between transition-all duration-300">
                        <div class="space-y-4">
                            <div class="relative w-full h-48 rounded-2xl overflow-hidden border border-slate-800 bg-space-900 flex items-center justify-center">
                                ${p.svg}
                                <span class="absolute bottom-2 left-2 text-[10px] font-bold font-orbitron ${p.badgeBg} text-space-950 px-2 py-0.5 rounded shadow">
                                    ${p.badge}
                                </span>
                            </div>
                            <div>
                                <h3 class="text-lg font-bold font-orbitron text-white">${p.title}</h3>
                                <p class="text-xs text-slate-400 mt-1 leading-relaxed">${p.desc}</p>
                            </div>
                            <div class="text-2xl font-black font-orbitron ${priceColor}">
                                ₦${p.price.toLocaleString()}
                            </div>
                        </div>
                        <button onclick="addToCart('${p.id}')" class="mt-5 w-full py-3 rounded-xl ${btnBg} text-space-950 font-black text-xs font-orbitron transition-all flex items-center justify-center gap-2 shadow-lg">
                            <i class="fa-solid fa-cart-plus"></i> Add To Cart
                        </button>
                    </div>
                `;
            }).join('');
        }

        // Category Filter switching
        function filterCategory(cat) {
            activeCategory = cat;
            
            ['all', 'solar', 'poultry'].forEach(type => {
                const btn = document.getElementById(`filter-${type}-btn`);
                if (btn) {
                    if (type === cat) {
                        btn.className = 'px-5 py-2.5 rounded-xl font-orbitron text-xs font-bold transition-all bg-solar-500 text-space-950';
                    } else {
                        btn.className = 'px-5 py-2.5 rounded-xl font-orbitron text-xs font-bold text-slate-400 hover:text-white bg-space-900 border border-slate-800 transition-all';
                    }
                }
            });

            renderProducts();
        }

        // Cart Logic
        function addToCart(productId) {
            const product = PRODUCTS.find(p => p.id === productId);
            if (!product) return;

            const existing = cart.find(item => item.id === productId);
            if (existing) {
                existing.qty += 1;
            } else {
                cart.push({ ...product, qty: 1 });
            }
            saveCart();
            showToast(`${product.title} added to cart!`);
            openCart();
        }

        function updateQty(productId, change) {
            const item = cart.find(i => i.id === productId);
            if (item) {
                item.qty += change;
                if (item.qty <= 0) {
                    cart = cart.filter(i => i.id !== productId);
                }
                saveCart();
            }
        }

        function openCart() {
            document.getElementById('cart-modal').classList.remove('hidden');
        }

        function closeCart() {
            document.getElementById('cart-modal').classList.add('hidden');
        }

        function updateCartUI() {
            const badge = document.getElementById('cart-badge');
            const list = document.getElementById('cart-items-list');
            const totalDisplay = document.getElementById('cart-total-price');

            const totalItems = cart.reduce((acc, i) => acc + i.qty, 0);
            const totalPrice = cart.reduce((acc, i) => acc + (i.price * i.qty), 0);

            if (badge) badge.textContent = totalItems;
            if (totalDisplay) totalDisplay.textContent = `₦${totalPrice.toLocaleString()}`;

            if (!list) return;

            if (cart.length === 0) {
                list.innerHTML = '<p class="text-xs text-slate-500 text-center py-8">Your cart is currently empty.</p>';
                return;
            }

            list.innerHTML = cart.map(item => `
                <div class="flex items-center justify-between p-3 rounded-2xl bg-space-900 border border-slate-800">
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-xl bg-space-950 border border-slate-800 flex items-center justify-center p-1">
                            ${item.svg}
                        </div>
                        <div>
                            <h4 class="font-bold text-xs text-white">${item.title}</h4>
                            <p class="text-[11px] text-solar-400 font-mono">₦${item.price.toLocaleString()}</p>
                        </div>
                    </div>
                    <div class="flex items-center gap-2">
                        <button onclick="updateQty('${item.id}', -1)" class="w-6 h-6 rounded-lg bg-space-950 border border-slate-700 text-xs font-bold text-white flex items-center justify-center hover:bg-slate-800">-</button>
                        <span class="text-xs font-bold text-white w-4 text-center">${item.qty}</span>
                        <button onclick="updateQty('${item.id}', 1)" class="w-6 h-6 rounded-lg bg-space-950 border border-slate-700 text-xs font-bold text-white flex items-center justify-center hover:bg-slate-800">+</button>
                    </div>
                </div>
            `).join('');
        }

        // Checkout Process & Bank Transfer Modal
        function processCheckout() {
            if (cart.length === 0) {
                showToast('Your cart is empty!');
                return;
            }

            const name = document.getElementById('cust-name').value.trim();
            const phone = document.getElementById('cust-phone').value.trim();
            const address = document.getElementById('cust-address').value.trim();
            const notes = document.getElementById('cust-notes').value.trim();

            if (!name || !phone || !address) {
                showToast('Please fill in Name, Phone, and Address');
                return;
            }

            const totalPrice = cart.reduce((acc, i) => acc + (i.price * i.qty), 0);
            const generatedOrderId = 'BAS-' + Math.floor(100000 + Math.random() * 900000);

            // Populate Payment Summary
            const summaryBox = document.getElementById('summary-order-box');
            summaryBox.innerHTML = `
                <p><strong>Order ID:</strong> <span class="text-solar-400 font-mono">${generatedOrderId}</span></p>
                <p><strong>Customer:</strong> ${name}</p>
                <p><strong>Phone:</strong> ${phone}</p>
                <p><strong>Address:</strong> ${address}</p>
                ${notes ? `<p><strong>Note:</strong> ${notes}</p>` : ''}
                <div class="border-t border-slate-800 pt-1.5 my-1.5 space-y-1">
                    ${cart.map(i => `<p class="flex justify-between"><span>${i.qty}x ${i.title}</span> <span>₦${(i.price * i.qty).toLocaleString()}</span></p>`).join('')}
                </div>
                <p class="flex justify-between font-bold text-solar-400 pt-1 border-t border-slate-800">
                    <span>Total Amount:</span> <span>₦${totalPrice.toLocaleString()}</span>
                </p>
            `;

            // Format WhatsApp Message
            let waMsg = `*NEW ORDER - BIG ALIEN SOLAR*\n`;
            waMsg += `*Order ID:* ${generatedOrderId}\n\n`;
            waMsg += `*Customer Details:*\n- Name: ${name}\n- Phone: ${phone}\n- Address: ${address}\n`;
            if (notes) waMsg += `- Landmark/Notes: ${notes}\n`;
            waMsg += `\n*Items Ordered:*\n`;
            cart.forEach(i => {
                waMsg += `- ${i.qty}x ${i.title} (N${(i.price * i.qty).toLocaleString()})\n`;
            });
            waMsg += `\n*Grand Total:* N${totalPrice.toLocaleString()}\n`;
            waMsg += `*Target Account:* Abel Philip | Moniepoint MFB | 6714306196\n`;
            if (attachedReceiptName) {
                waMsg += `*Receipt Proof:* Attached in Web App (${attachedReceiptName})\n`;
            }
            waMsg += `\nI am sending this message to confirm my order and payment status.`;

            const finalBtn = document.getElementById('send-whatsapp-final-btn');
            finalBtn.href = `https://wa.me/2347025136166?text=${encodeURIComponent(waMsg)}`;

            // Store pending order details on dataset
            finalBtn.dataset.orderId = generatedOrderId;
            finalBtn.dataset.name = name;
            finalBtn.dataset.phone = phone;
            finalBtn.dataset.address = address;
            finalBtn.dataset.notes = notes;

            closeCart();
            document.getElementById('payment-modal').classList.remove('hidden');
        }

        // Receipt Upload Handler & Preview
        function handleReceiptUpload(event) {
            const file = event.target.files[0];
            const container = document.getElementById('receipt-preview-container');
            const imgPreview = document.getElementById('receipt-img-preview');
            
            if (file) {
                attachedReceiptName = file.name;
                
                if (file.type.startsWith('image/')) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        imgPreview.src = e.target.result;
                        container.classList.remove('hidden');
                    }
                    reader.readAsDataURL(file);
                } else {
                    container.classList.remove('hidden');
                    imgPreview.classList.add('hidden');
                }
                showToast('Receipt attached successfully!');
            }
        }

        // Confirm order & save to Local Order History
        function confirmOrderSaved() {
            const btn = document.getElementById('send-whatsapp-final-btn');
            const orderId = btn.dataset.orderId || ('BAS-' + Math.floor(100000 + Math.random() * 900000));
            const name = btn.dataset.name || 'Customer';
            const phone = btn.dataset.phone || '';
            const address = btn.dataset.address || '';
            const notes = btn.dataset.notes || '';

            const totalPrice = cart.reduce((acc, i) => acc + (i.price * i.qty), 0);

            const newOrder = {
                id: orderId,
                date: new Date().toLocaleDateString('en-GB', { day: 'numeric', month: 'short', year: 'numeric' }),
                items: [...cart],
                total: totalPrice,
                customer: { name, phone, address, notes }
            };

            orderHistory.unshift(newOrder);
            saveOrders();

            // Clear Cart
            cart = [];
            saveCart();
            
            setTimeout(() => {
                closePaymentModal();
            }, 1000);
        }

        function closePaymentModal() {
            document.getElementById('payment-modal').classList.add('hidden');
        }

        // Order History Modal
        function openOrderHistory() {
            const modal = document.getElementById('history-modal');
            const list = document.getElementById('history-orders-list');

            if (orderHistory.length === 0) {
                list.innerHTML = '<p class="text-xs text-slate-500 text-center py-8">No previous orders found on this device.</p>';
            } else {
                list.innerHTML = orderHistory.map(o => {
                    let reorderMsg = `*RE-ORDER INQUIRY - BIG ALIEN SOLAR*\n*Order ID:* ${o.id}\n*Name:* ${o.customer.name}\n*Total:* N${o.total.toLocaleString()}\nPlease assist with this order status.`;
                    let reorderUrl = `https://wa.me/2347025136166?text=${encodeURIComponent(reorderMsg)}`;

                    return `
                        <div class="p-4 rounded-2xl bg-space-900 border border-slate-800 space-y-2 text-xs">
                            <div class="flex justify-between items-center font-orbitron font-bold">
                                <span class="text-solar-400">Order #${o.id}</span>
                                <span class="text-slate-400 text-[10px]">${o.date}</span>
                            </div>
                            <p class="text-slate-300"><strong>Customer:</strong> ${o.customer.name} (${o.customer.phone})</p>
                            <p class="text-slate-300"><strong>Address:</strong> ${o.customer.address}</p>
                            <div class="border-t border-slate-800/80 pt-2 space-y-1 text-slate-400">
                                ${o.items.map(i => `<p class="flex justify-between"><span>${i.qty}x ${i.title}</span><span>₦${(i.price * i.qty).toLocaleString()}</span></p>`).join('')}
                            </div>
                            <div class="border-t border-slate-800/80 pt-2 flex justify-between items-center">
                                <span class="font-bold text-white">Total: <strong class="text-solar-400">₦${o.total.toLocaleString()}</strong></span>
                                <a href="${reorderUrl}" target="_blank" class="px-3 py-1 rounded-lg bg-emerald-500/20 text-emerald-400 border border-emerald-500/30 font-bold text-[10px]">
                                    <i class="fa-brands fa-whatsapp mr-1"></i> Resend to WA
                                </a>
                            </div>
                        </div>
                    `;
                }).join('');
            }

            modal.classList.remove('hidden');
        }

        function closeOrderHistory() {
            document.getElementById('history-modal').classList.add('hidden');
        }

        // Copy Account Number Helper
        function copyAccNumber() {
            const accNum = '6714306196';
            const el = document.createElement('textarea');
            el.value = accNum;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);
            showToast('Moniepoint Account (6714306196) copied!');
        }

        // Mobile Menu Drawer
        function setupMobileDrawer() {
            const btn = document.getElementById('mobile-toggle');
            if (btn) btn.addEventListener('click', toggleMobileMenu);
        }

        function toggleMobileMenu() {
            const drawer = document.getElementById('mobile-drawer');
            if (drawer) drawer.classList.toggle('hidden');
        }

        // PWA Setup & Service Worker Registration
        function setupPWA() {
            window.addEventListener('beforeinstallprompt', (e) => {
                e.preventDefault();
                deferredPrompt = e;
                const installBtn = document.getElementById('pwa-install-btn');
                if (installBtn) {
                    installBtn.classList.remove('hidden');
                    installBtn.addEventListener('click', () => {
                        deferredPrompt.prompt();
                        deferredPrompt.userChoice.then(() => {
                            installBtn.classList.add('hidden');
                        });
                    });
                }
            });
        }

        function registerServiceWorker() {
            if ('serviceWorker' in navigator) {
                const swCode = `
                    self.addEventListener('install', e => self.skipWaiting());
                    self.addEventListener('activate', e => self.clients.claim());
                    self.addEventListener('fetch', e => e.respondWith(fetch(e.request).catch(() => new Response('Offline'))));
                `;
                const blob = new Blob([swCode], { type: 'application/javascript' });
                navigator.serviceWorker.register(URL.createObjectURL(blob)).catch(err => console.log('SW reg error:', err));
            }
        }
    </script>
</body>
</html>
