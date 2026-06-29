# sushan-store
Official website for Sushanxio — Art meets Gaming

<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sushanxio Store — Art Meets Gaming</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <script src="https://code.iconify.design/3/3.1.0/iconify.min.js"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: { 'inter': ['Inter', 'sans-serif'] },
                    colors: {
                        neon: { green: '#00ff88', purple: '#a855f7', 'purple-dark': '#7c3aed', 'purple-light': '#c084fc' },
                        surface: { 50: '#1a1a2e', 100: '#16162a', 200: '#121225', 300: '#0f0f1e', 400: '#0a0a15', 500: '#07070f' }
                    }
                }
            }
        }
    </script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Inter', sans-serif; background: #07070f; color: #e5e5e5; overflow-x: hidden; }
        ::selection { background: #a855f7; color: white; }
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #0a0a15; }
        ::-webkit-scrollbar-thumb { background: #a855f7; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #c084fc; }

        .glow-green { text-shadow: 0 0 10px rgba(0,255,136,0.5), 0 0 20px rgba(0,255,136,0.3), 0 0 40px rgba(0,255,136,0.15); }
        .glow-purple { text-shadow: 0 0 10px rgba(168,85,247,0.5), 0 0 20px rgba(168,85,247,0.3), 0 0 40px rgba(168,85,247,0.15); }
        .glow-box-green { box-shadow: 0 0 15px rgba(0,255,136,0.15), 0 0 30px rgba(0,255,136,0.08), inset 0 0 15px rgba(0,255,136,0.03); }
        .glow-box-purple { box-shadow: 0 0 15px rgba(168,85,247,0.15), 0 0 30px rgba(168,85,247,0.08), inset 0 0 15px rgba(168,85,247,0.03); }
        .glow-box-mixed { box-shadow: 0 0 15px rgba(0,255,136,0.1), 0 0 30px rgba(168,85,247,0.1); }

        .btn-glow-green {
            background: linear-gradient(135deg, #00ff88, #00cc6a);
            box-shadow: 0 0 20px rgba(0,255,136,0.3), 0 0 40px rgba(0,255,136,0.15);
            transition: all 0.3s ease;
        }
        .btn-glow-green:hover {
            box-shadow: 0 0 30px rgba(0,255,136,0.5), 0 0 60px rgba(0,255,136,0.25), 0 0 90px rgba(0,255,136,0.1);
            transform: translateY(-2px);
        }
        .btn-glow-purple {
            background: linear-gradient(135deg, #a855f7, #7c3aed);
            box-shadow: 0 0 20px rgba(168,85,247,0.3), 0 0 40px rgba(168,85,247,0.15);
            transition: all 0.3s ease;
        }
        .btn-glow-purple:hover {
            box-shadow: 0 0 30px rgba(168,85,247,0.5), 0 0 60px rgba(168,85,247,0.25), 0 0 90px rgba(168,85,247,0.1);
            transform: translateY(-2px);
        }
        .btn-outline-glow {
            border: 1px solid rgba(0,255,136,0.4);
            color: #00ff88;
            transition: all 0.3s ease;
        }
        .btn-outline-glow:hover {
            background: rgba(0,255,136,0.1);
            border-color: #00ff88;
            box-shadow: 0 0 20px rgba(0,255,136,0.2);
            transform: translateY(-2px);
        }

        .grid-bg {
            background-image:
                linear-gradient(rgba(168,85,247,0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(168,85,247,0.03) 1px, transparent 1px);
            background-size: 60px 60px;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            border-radius: 50%;
            animation: float-particle linear infinite;
        }
        @keyframes float-particle {
            0% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(50px); opacity: 0; }
        }

        .product-card {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(255,255,255,0.05);
        }
        .product-card:hover {
            transform: translateY(-8px);
            border-color: rgba(168,85,247,0.3);
            box-shadow: 0 0 30px rgba(168,85,247,0.1), 0 20px 40px rgba(0,0,0,0.4);
        }
        .product-card:hover .card-image {
            transform: scale(1.08);
        }
        .product-card:hover .card-overlay {
            opacity: 1;
        }

        .gallery-card {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            overflow: hidden;
        }
        .gallery-card:hover {
            transform: scale(1.03);
            box-shadow: 0 0 40px rgba(0,255,136,0.1), 0 0 80px rgba(168,85,247,0.08);
        }
        .gallery-card:hover img {
            transform: scale(1.1);
        }

        .scanline::after {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0;
            height: 2px;
            background: linear-gradient(90deg, transparent, rgba(0,255,136,0.4), transparent);
            animation: scanline 4s linear infinite;
        }
        @keyframes scanline {
            0% { top: 0; opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { top: 100%; opacity: 0; }
        }

        .pulse-ring {
            animation: pulse-ring 2s ease-out infinite;
        }
        @keyframes pulse-ring {
            0% { box-shadow: 0 0 0 0 rgba(0,255,136,0.4); }
            100% { box-shadow: 0 0 0 20px rgba(0,255,136,0); }
        }

        .fade-up {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.7s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .fade-up.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .gradient-text {
            background: linear-gradient(135deg, #00ff88, #a855f7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-blur {
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
        }

        .mobile-menu {
            transform: translateX(100%);
            transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .mobile-menu.open {
            transform: translateX(0);
        }

        .glow-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            pointer-events: none;
        }

        .neon-line {
            height: 1px;
            background: linear-gradient(90deg, transparent, #00ff88, #a855f7, transparent);
            opacity: 0.4;
        }

        .toast {
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.4s ease;
        }
        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }
    </style>
</head>
<body class="font-inter grid-bg">

    <div id="particles" class="fixed inset-0 pointer-events-none z-0"></div>

    <!-- Navigation -->
    <nav id="navbar" class="fixed top-0 left-0 right-0 z-50 nav-blur bg-surface-500/80 border-b border-white/5 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-6 h-16 flex items-center justify-between">
            <a href="#hero" class="flex items-center gap-2 group">
                <div class="w-8 h-8 rounded-lg bg-gradient-to-br from-neon-green to-neon-purple flex items-center justify-center pulse-ring">
                    <span class="text-black font-black text-sm">S</span>
                </div>
                <span class="font-bold text-lg tracking-tight">
                    <span class="text-white">Sushan</span><span class="text-neon-green">xio</span>
                </span>
            </a>
            <div class="hidden md:flex items-center gap-8">
                <a href="#hero" class="text-sm text-neutral-400 hover:text-neon-green transition-colors duration-200">Home</a>
                <a href="#products" class="text-sm text-neutral-400 hover:text-neon-green transition-colors duration-200">Products</a>
                <a href="#gallery" class="text-sm text-neutral-400 hover:text-neon-green transition-colors duration-200">Gallery</a>
                <a href="#about" class="text-sm text-neutral-400 hover:text-neon-green transition-colors duration-200">About</a>
                <a href="#contact" class="text-sm text-neutral-400 hover:text-neon-green transition-colors duration-200">Contact</a>
                <a href="https://www.redbubble.com/shop/ap/181849825?asc=u" target="_blank" rel="noopener" class="btn-glow-green text-black text-sm font-semibold px-5 py-2 rounded-lg">
                    Shop Now
                </a>
            </div>
            <button id="menuBtn" class="md:hidden w-10 h-10 flex flex-col items-center justify-center gap-1.5 group" aria-label="Menu">
                <span class="w-6 h-0.5 bg-white transition-all duration-300 origin-center group-[.active]:rotate-45 group-[.active]:translate-y-2"></span>
                <span class="w-6 h-0.5 bg-white transition-all duration-300 group-[.active]:opacity-0"></span>
                <span class="w-6 h-0.5 bg-white transition-all duration-300 origin-center group-[.active]:-rotate-45 group-[.active]:-translate-y-2"></span>
            </button>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div id="mobileMenu" class="mobile-menu fixed top-0 right-0 bottom-0 w-72 z-[60] bg-surface-400/95 nav-blur border-l border-white/5 p-8 flex flex-col">
        <div class="flex justify-end mb-10">
            <button id="closeMenu" class="w-10 h-10 flex items-center justify-center text-neutral-400 hover:text-white transition-colors">
                <span class="iconify" data-icon="lucide:x" data-width="24"></span>
            </button>
        </div>
        <div class="flex flex-col gap-6">
            <a href="#hero" class="mobile-link text-lg text-neutral-300 hover:text-neon-green transition-colors">Home</a>
            <a href="#products" class="mobile-link text-lg text-neutral-300 hover:text-neon-green transition-colors">Products</a>
            <a href="#gallery" class="mobile-link text-lg text-neutral-300 hover:text-neon-green transition-colors">Gallery</a>
            <a href="#about" class="mobile-link text-lg text-neutral-300 hover:text-neon-green transition-colors">About</a>
            <a href="#contact" class="mobile-link text-lg text-neutral-300 hover:text-neon-green transition-colors">Contact</a>
            <div class="neon-line my-4"></div>
            <a href="https://www.redbubble.com/shop/ap/181849825?asc=u" target="_blank" rel="noopener" class="btn-glow-green text-black text-center font-semibold px-5 py-3 rounded-lg">
                Shop Now
            </a>
        </div>
    </div>
    <div id="menuOverlay" class="fixed inset-0 bg-black/60 z-[55] hidden"></div>

    <!-- Hero Section -->
    <section id="hero" class="relative min-h-screen flex items-center justify-center overflow-hidden pt-16">
        <div class="glow-orb w-96 h-96 bg-neon-purple/20 -top-48 -left-48"></div>
        <div class="glow-orb w-80 h-80 bg-neon-green/15 -bottom-40 -right-40"></div>
        <div class="glow-orb w-64 h-64 bg-neon-purple/10 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"></div>

        <div class="relative z-10 max-w-5xl mx-auto px-6 text-center">
            <div class="fade-up inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-neon-purple/30 bg-neon-purple/5 mb-8">
                <span class="w-2 h-2 rounded-full bg-neon-green animate-pulse"></span>
                <span class="text-xs font-medium text-neon-purple-light tracking-wide uppercase">Now Available on Redbubble</span>
            </div>

            <h1 class="fade-up text-5xl md:text-7xl lg:text-8xl font-black tracking-tight leading-[0.95] mb-6">
                <span class="text-white">Art Meets</span><br>
                <span class="gradient-text">Gaming</span>
            </h1>

            <p class="fade-up text-lg md:text-xl text-neutral-400 max-w-2xl mx-auto mb-10 leading-relaxed">
                Unique digital art and gaming merchandise crafted with passion. 
                From custom prints to wearable art — level up your style.
            </p>

            <div class="fade-up flex flex-col sm:flex-row items-center justify-center gap-4">
                <a href="https://www.redbubble.com/shop/ap/181849825?asc=u" target="_blank" rel="noopener" class="btn-glow-green text-black font-bold px-8 py-4 rounded-xl text-base flex items-center gap-2">
                    <span class="iconify" data-icon="lucide:shopping-bag" data-width="20"></span>
                    Shop Now
                </a>
                <a href="#gallery" class="btn-outline-glow px-8 py-4 rounded-xl text-base font-semibold flex items-center gap-2">
                    <span class="iconify" data-icon="lucide:eye" data-width="20"></span>
                    View Gallery
                </a>
            </div>

            <div class="fade-up flex items-center justify-center gap-8 md:gap-16 mt-16">
                <div class="text-center">
                    <div class="text-2xl md:text-3xl font-bold text-neon-green glow-green">50+</div>
                    <div class="text-xs text-neutral-500 mt-1 uppercase tracking-wider">Designs</div>
                </div>
                <div class="w-px h-10 bg-white/10"></div>
                <div class="text-center">
                    <div class="text-2xl md:text-3xl font-bold text-neon-purple glow-purple">5</div>
                    <div class="text-xs text-neutral-500 mt-1 uppercase tracking-wider">Categories</div>
                </div>
                <div class="w-px h-10 bg-white/10"></div>
                <div class="text-center">
                    <div class="text-2xl md:text-3xl font-bold text-neon-green glow-green">100%</div>
                    <div class="text-xs text-neutral-500 mt-1 uppercase tracking-wider">Original</div>
                </div>
            </div>
        </div>

        <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 animate-bounce">
            <span class="text-xs text-neutral-500 uppercase tracking-widest">Scroll</span>
            <span class="iconify text-neutral-500" data-icon="lucide:chevron-down" data-width="16"></span>
        </div>
    </section>

    <div class="neon-line mx-auto max-w-4xl"></div>

    <!-- Products Section -->
    <section id="products" class="relative py-24 md:py-32">
        <div class="glow-orb w-72 h-72 bg-neon-green/10 top-20 right-0"></div>

        <div class="max-w-7xl mx-auto px-6 relative z-10">
            <div class="text-center mb-16 fade-up">
                <span class="text-xs font-semibold text-neon-purple-light uppercase tracking-[0.2em] mb-3 block">Merchandise</span>
                <h2 class="text-3xl md:text-5xl font-bold tracking-tight mb-4">
                    <span class="text-white">Explore Our </span><span class="gradient-text">Products</span>
                </h2>
                <p class="text-neutral-400 max-w-xl mx-auto">Premium quality merchandise featuring original digital art, designed for gamers and art lovers.</p>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">

                <!-- Gaming Accessories -->
                <div class="product-card rounded-2xl bg-surface-300/80 overflow-hidden group fade-up">
                    <div class="relative aspect-[4/3] overflow-hidden">
                        <img src="https://picsum.photos/seed/gaming-accessories-neon/600/450.jpg" alt="Gaming Accessories" class="card-image w-full h-full object-cover transition-transform duration-700">
                        <div class="card-overlay absolute inset-0 bg-gradient-to-t from-surface-500 via-surface-500/50 to-transparent opacity-0 transition-opacity duration-300 flex items-end p-6">
                            <a href="https://www.redbubble.com/shop/ap/181849825?asc=u" target="_blank" rel="noopener" class="btn-glow-green text-black text-sm font-semibold px-5 py-2.5 rounded-lg flex items-center gap-2">
                                <span class="iconify" data-icon="lucide:external-link" data-width="14"></span>
                                Browse
                            </a>
                        </div>
                        <div class="absolute top-4 left-4 px-3 py-1 rounded-full bg-neon-green/10 border border-neon-green/30 text-neon-green text-xs font-semibold">Popular</div>
                    </div>
                    <div class="p-6">
                        <div class="flex items-center gap-3 mb-2">
                            <span class="iconify text-neon-green" data-icon="lucide:gamepad-2" data-width="20"></span>
                            <h3 class="text-lg font-bold text-white">Gaming Accessories</h3>
                        </div>
                        <p class="text-sm text-neutral-400 leading-relaxed">Mousepads, desk mats, and gaming gear featuring original neon art designs.</p>
                    </div>
                </div>

                <!-- Custom Art Prints -->
                <div class="product-card rounded-2xl bg-surface-300/80 overflow-hidden group fade-up" style="transition-delay: 0.1s">
                    <div class="relative aspect-[4/3] overflow-hidden">
                        <img src="https://picsum.photos/seed/art-prints-galaxy/600/450.jpg" alt="Custom Art Prints" class="card-image w-full h-full object-cover transition-transform duration-700">
                        <div class="card-overlay absolute inset-0 bg-gradient-to-t from-surface-500 via-surface-500/50 to-transparent opacity-0 transition-opacity duration-300 flex items-end p-6">
                            <a href="https://www.redbubble.com/shop/ap/181849825?asc=u" target="_blank" rel="noopener" class="btn-glow-green text-black text-sm font-semibold px-5 py-2.5 rounded-lg flex items-center gap-2">
                                <span class="iconify" data-icon="lucide:external-link" data-width="14"></span>
                                Browse
                            </a>
                        </div>
                        <div class="absolute top-4 left-4 px-3 py-1 rounded-full bg-neon-purple/10 border border-neon-purple/30 text-neon-purple-light text-xs font-semibold">New</div>
                    </div>
                    <div class="p-6">
                        <div class="flex items-center gap-3 mb-2">
                            <span class="iconify text-neon-purple" data-icon="lucide:palette" data-width="20"></span>
                            <h3 class="text-lg font-bold text-white">Custom Art Prints</h3>
                        </div>
                        <p class="text-sm text-neutral-400 leading-relaxed">High-quality poster prints and wall art with vibrant sci-fi and gaming themes.</p>
                    </div>
                </div>

                <!-- T-Shirts -->
                <div class="product-card rounded-2xl bg-surface-300/80 overflow-hidden group fade-up" style="transition-delay: 0.2s">
                    <div class="relative aspect-[4/3] overflow-hidden">
                        <img src="https://picsum.photos/seed/neon-tshirt-design/600/450.jpg" alt="T-Shirts" class="card-image w-full h-full object-cover transition-transform duration-700">
                        <div class="card-overlay absolute inset-0 bg-gradient-to-t from-surface-500 via-surface-500/50 to-transparent opacity-0 transition-opacity duration-300 flex items-end p-6">
                            <a href="https://www.redbubble.com/shop/ap/181849825?asc=u" target="_b