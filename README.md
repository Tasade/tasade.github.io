# tasade.github.io

<!DOCTYPE html>
<html lang="tr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selin Yılmaz | Kişisel Blog & Portfolyo</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#fbf7f5',
                            100: '#f6ede8',
                            200: '#edd9ce',
                            500: '#d97757',
                            600: '#c25a38',
                            900: '#3d251e',
                        },
                        darkbg: '#121214',
                        darkcard: '#1c1c21',
                        darkborder: '#2d2d35'
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                        heading: ['Outfit', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            transition: background-color 0.3s ease, color 0.3s ease;
        }
        h1, h2, h3, h4, .font-heading {
            font-family: 'Outfit', sans-serif;
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: transparent;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        .dark ::-webkit-scrollbar-thumb {
            background: #334155;
        }
        /* Modal Backdrop blur animation */
        .modal-animate {
            animation: fadeIn 0.25s cubic-bezier(0.16, 1, 0.3, 1);
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.97); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-800 dark:bg-darkbg dark:text-stone-200 antialiased min-h-screen flex flex-col selection:bg-brand-500 selection:text-white">

    <!-- HEADER / NAVIGATION -->
    <header class="sticky top-0 z-40 w-full backdrop-blur-md bg-stone-50/80 dark:bg-darkbg/80 border-b border-stone-200/60 dark:border-darkborder transition-colors duration-300">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16 sm:h-20">
                <!-- Logo -->
                <a href="#hero" class="group flex items-center gap-2 text-xl font-heading font-bold tracking-tight text-stone-900 dark:text-white">
                    <span class="w-8 h-8 rounded-full bg-brand-500 text-white flex items-center justify-center font-bold text-sm shadow-md shadow-brand-500/20 group-hover:scale-105 transition-transform">SY</span>
                    <span>Selin<span class="text-brand-500">.</span></span>
                </a>

                <!-- Desktop Nav Navigation Links -->
                <nav class="hidden md:flex items-center space-x-8 text-sm font-medium text-stone-600 dark:text-stone-300">
                    <a href="#hero" class="hover:text-brand-500 dark:hover:text-brand-500 transition-colors">Ana Sayfa</a>
                    <a href="#about" class="hover:text-brand-500 dark:hover:text-brand-500 transition-colors">Hakkımda</a>
                    <a href="#blog" class="hover:text-brand-500 dark:hover:text-brand-500 transition-colors">Yazılarım</a>
                    <a href="#contact" class="hover:text-brand-500 dark:hover:text-brand-500 transition-colors">İletişim</a>
                </nav>

                <!-- Actions (Dark Mode Toggle & Mobile Menu Btn) -->
                <div class="flex items-center space-x-3">
                    <!-- Dark Mode Toggle Button -->
                    <button id="themeToggle" class="p-2.5 rounded-full text-stone-600 dark:text-stone-300 hover:bg-stone-200/60 dark:hover:bg-stone-800 transition-colors focus:outline-none" aria-label="Karanlık Mod Değiştir">
                        <i id="themeIcon" class="fa-solid fa-moon text-lg"></i>
                    </button>

                    <!-- Mobile Menu Button -->
                    <button id="mobileMenuBtn" class="md:hidden p-2.5 rounded-lg text-stone-600 dark:text-stone-300 hover:bg-stone-200/60 dark:hover:bg-stone-800 focus:outline-none" aria-label="Menüyü Aç">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobileMenu" class="hidden md:hidden border-b border-stone-200 dark:border-darkborder bg-stone-50/95 dark:bg-darkbg/95 backdrop-blur-lg px-4 pt-2 pb-6 space-y-3">
            <a href="#hero" class="mobile-nav-link block py-2 text-base font-medium text-stone-700 dark:text-stone-200 hover:text-brand-500">Ana Sayfa</a>
            <a href="#about" class="mobile-nav-link block py-2 text-base font-medium text-stone-700 dark:text-stone-200 hover:text-brand-500">Hakkımda</a>
            <a href="#blog" class="mobile-nav-link block py-2 text-base font-medium text-stone-700 dark:text-stone-200 hover:text-brand-500">Yazılarım</a>
            <a href="#contact" class="mobile-nav-link block py-2 text-base font-medium text-stone-700 dark:text-stone-200 hover:text-brand-500">İletişim</a>
        </div>
    </header>

    <main class="flex-grow">
        <!-- HERO SECTION -->
        <section id="hero" class="py-20 sm:py-32 relative overflow-hidden">
            <!-- Decorative Subtle Shapes -->
            <div class="absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-brand-500/10 dark:bg-brand-500/5 rounded-full blur-3xl -z-10 pointer-events-none"></div>
            
            <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
                <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-brand-50 dark:bg-brand-900/30 text-brand-600 dark:text-brand-200 text-xs font-semibold tracking-wide uppercase mb-6 border border-brand-200/50 dark:border-brand-500/20">
                    <span class="w-2 h-2 rounded-full bg-brand-500 animate-pulse"></span>
                    Tasarım & Yazılım Blogu
                </div>
                
                <h1 class="text-4xl sm:text-6xl font-heading font-extrabold text-stone-900 dark:text-white tracking-tight leading-tight mb-6">
                    Fikirler, Kodlar ve <br class="hidden sm:inline"/>
                    <span class="bg-gradient-to-r from-brand-500 to-amber-600 bg-clip-text text-transparent">Dijital Deneyimler.</span>
                </h1>
                
                <p class="max-w-2xl mx-auto text-lg sm:text-xl text-stone-600 dark:text-stone-400 mb-10 leading-relaxed font-light">
                    Merhaba, ben Selin. Web teknolojileri, kullanıcı arayüzü tasarımı ve kişisel gelişim üzerine deneyimlerimi ve öğrendiklerimi paylaşıyorum.
                </p>
                
                <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                    <a href="#blog" class="w-full sm:w-auto px-7 py-3.5 rounded-xl bg-brand-500 hover:bg-brand-600 text-white font-medium text-base shadow-lg shadow-brand-500/25 hover:shadow-brand-500/40 hover:-translate-y-0.5 transition-all flex items-center justify-center gap-2">
                        <span>Blog'u Oku</span>
                        <i class="fa-solid fa-arrow-down text-sm"></i>
                    </a>
                    <a href="#contact" class="w-full sm:w-auto px-7 py-3.5 rounded-xl bg-stone-200/80 dark:bg-stone-800 hover:bg-stone-300/80 dark:hover:bg-stone-700 text-stone-800 dark:text-stone-200 font-medium text-base hover:-translate-y-0.5 transition-all flex items-center justify-center gap-2">
                        <span>İletişime Geç</span>
                        <i class="fa-regular fa-envelope text-sm"></i>
                    </a>
                </div>
            </div>
        </section>

        <!-- ABOUT ME SECTION -->
        <section id="about" class="py-16 sm:py-24 bg-stone-100/60 dark:bg-darkcard/50 border-y border-stone-200/60 dark:border-darkborder">
            <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 md:grid-cols-12 gap-10 lg:gap-12 items-center">
                    <!-- Profile Image / Avatar -->
                    <div class="md:col-span-5 flex justify-center">
                        <div class="relative group">
                            <div class="absolute -inset-1 bg-gradient-to-r from-brand-500 to-amber-500 rounded-3xl blur opacity-30 group-hover:opacity-60 transition duration-500"></div>
                            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80" 
                                 alt="Selin Yılmaz Profile" 
                                 class="relative w-64 h-64 sm:w-72 sm:h-72 object-cover rounded-2xl shadow-xl border-2 border-white dark:border-stone-800"
                                 onerror="this.onerror=null; this.src='https://placehold.co/400x400/d97757/ffffff?text=SY';">
                        </div>
                    </div>

                    <!-- Content -->
                    <div class="md:col-span-7">
                        <span class="text-brand-500 font-semibold text-sm tracking-wider uppercase">Hakkımda</span>
                        <h2 class="text-3xl sm:text-4xl font-heading font-bold text-stone-900 dark:text-white mt-2 mb-4">
                            Tasarım ve teknolojinin kesişim noktasındayım.
                        </h2>
                        <p class="text-stone-600 dark:text-stone-300 leading-relaxed mb-6">
                            Yaklaşık 5 yıldır Frontend Geliştirici ve UI/UX tasarımcısı olarak çalışıyorum. Minimalist estetiğe, kullanıcı dostu arayüzlere ve temiz kod standartlarına büyük önem veriyorum. Boş zamanlarımda teknoloji makaleleri yazıyor, açık kaynak projelere katkıda bulunuyor ve yeni kahve demleme yöntemleri deniyorum.
                        </p>

                        <!-- Skill Tags -->
                        <div>
                            <h3 class="text-xs font-semibold text-stone-500 dark:text-stone-400 uppercase tracking-wider mb-3">İlgi Alanları & Yetenekler</h3>
                            <div class="flex flex-wrap gap-2">
                                <span class="px-3 py-1.5 rounded-lg text-xs font-medium bg-white dark:bg-stone-800 text-stone-700 dark:text-stone-300 shadow-sm border border-stone-200 dark:border-stone-700/60">UI/UX Design</span>
                                <span class="px-3 py-1.5 rounded-lg text-xs font-medium bg-white dark:bg-stone-800 text-stone-700 dark:text-stone-300 shadow-sm border border-stone-200 dark:border-stone-700/60">JavaScript / React</span>
                                <span class="px-3 py-1.5 rounded-lg text-xs font-medium bg-white dark:bg-stone-800 text-stone-700 dark:text-stone-300 shadow-sm border border-stone-200 dark:border-stone-700/60">Tailwind CSS</span>
                                <span class="px-3 py-1.5 rounded-lg text-xs font-medium bg-white dark:bg-stone-800 text-stone-700 dark:text-stone-300 shadow-sm border border-stone-200 dark:border-stone-700/60">Teknik Yazarlık</span>
                                <span class="px-3 py-1.5 rounded-lg text-xs font-medium bg-white dark:bg-stone-800 text-stone-700 dark:text-stone-300 shadow-sm border border-stone-200 dark:border-stone-700/60">Açık Kaynak</span>
                                <span class="px-3 py-1.5 rounded-lg text-xs font-medium bg-white dark:bg-stone-800 text-stone-700 dark:text-stone-300 shadow-sm border border-stone-200 dark:border-stone-700/60">Kahve Kültürü</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- BLOG SECTION -->
        <section id="blog" class="py-20 sm:py-28">
            <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
                <!-- Section Header -->
                <div class="flex flex-col md:flex-row md:items-end justify-between mb-12 gap-6">
                    <div>
                        <span class="text-brand-500 font-semibold text-sm tracking-wider uppercase">Son İçerikler</span>
                        <h2 class="text-3xl sm:text-4xl font-heading font-bold text-stone-900 dark:text-white mt-1">
                            Blog Yazıları
                        </h2>
                    </div>

                    <!-- Search Bar & Category Filters -->
                    <div class="w-full md:w-auto flex flex-col sm:flex-row gap-3">
                        <div class="relative min-w-[240px]">
                            <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-1/2 -translate-y-1/2 text-stone-400 text-sm"></i>
                            <input type="text" id="searchInput" placeholder="Yazılarda ara..." 
                                   class="w-full pl-10 pr-4 py-2.5 rounded-xl border border-stone-200 dark:border-darkborder bg-white dark:bg-darkcard text-sm focus:outline-none focus:ring-2 focus:ring-brand-500/50 transition-all">
                        </div>
                        <select id="categoryFilter" class="px-4 py-2.5 rounded-xl border border-stone-200 dark:border-darkborder bg-white dark:bg-darkcard text-sm text-stone-700 dark:text-stone-300 focus:outline-none focus:ring-2 focus:ring-brand-500/50 transition-all cursor-pointer">
                            <option value="all">Tüm Kategoriler</option>
                            <option value="tasarim">Tasarım</option>
                            <option value="yazilim">Yazılım</option>
                            <option value="verimlilik">Verimlilik</option>
                        </select>
                    </div>
                </div>

                <!-- Blog Grid -->
                <div id="blogGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Posts will be injected dynamically via JS -->
                </div>

                <!-- Empty State Message -->
                <div id="emptyState" class="hidden text-center py-16">
                    <i class="fa-solid fa-pen-nib text-4xl text-stone-300 dark:text-stone-600 mb-3"></i>
                    <p class="text-stone-500 dark:text-stone-400 text-lg">Aramanıza uygun blog yazısı bulunamadı.</p>
                </div>
            </div>
        </section>

        <!-- CONTACT & FEEDBACK FORM SECTION -->
        <section id="contact" class="py-20 sm:py-28 bg-stone-100/60 dark:bg-darkcard/50 border-t border-stone-200/60 dark:border-darkborder">
            <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <span class="text-brand-500 font-semibold text-sm tracking-wider uppercase">Bana Ulaşın</span>
                    <h2 class="text-3xl sm:text-4xl font-heading font-bold text-stone-900 dark:text-white mt-1 mb-4">
                        Bir Mesaj Bırakın
                    </h2>
                    <p class="text-stone-600 dark:text-stone-400">
                        Projeler, iş birlikleri veya sadece merhaba demek için aşağıdaki formu doldurabilirsiniz.
                    </p>
                </div>

                <!-- Form Card -->
                <div class="bg-white dark:bg-darkcard rounded-2xl p-6 sm:p-10 shadow-xl border border-stone-200/80 dark:border-darkborder relative">
                    
                    <!-- Alert Notification (Success Message) -->
                    <div id="successAlert" class="hidden mb-6 p-4 rounded-xl bg-emerald-50 dark:bg-emerald-950/40 border border-emerald-200 dark:border-emerald-800/50 text-emerald-800 dark:text-emerald-300 flex items-start gap-3 transition-all duration-300">
                        <i class="fa-solid fa-circle-check text-xl text-emerald-500 mt-0.5"></i>
                        <div>
                            <h4 class="font-semibold text-sm">Mesajınız başarıyla iletildi!</h4>
                            <p class="text-xs text-emerald-700 dark:text-emerald-400 mt-0.5">En kısa sürede e-posta adresiniz üzerinden dönüş yapacağım. Teşekkürler!</p>
                        </div>
                    </div>

                    <form id="contactForm" onsubmit="handleFormSubmit(event)" class="space-y-6">
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                            <!-- Ad Soyad -->
                            <div>
                                <label for="name" class="block text-sm font-medium text-stone-700 dark:text-stone-300 mb-2">Ad Soyad *</label>
                                <input type="text" id="name" required placeholder="Ahmet Yılmaz" 
                                       class="w-full px-4 py-3 rounded-xl border border-stone-200 dark:border-stone-700/80 bg-stone-50 dark:bg-stone-900/50 text-stone-900 dark:text-white text-sm focus:outline-none focus:ring-2 focus:ring-brand-500/50 focus:bg-white dark:focus:bg-stone-900 transition-all">
                            </div>

                            <!-- E-posta -->
                            <div>
                                <label for="email" class="block text-sm font-medium text-stone-700 dark:text-stone-300 mb-2">E-posta Adresi *</label>
                                <input type="email" id="email" required placeholder="ahmet@example.com" 
                                       class="w-full px-4 py-3 rounded-xl border border-stone-200 dark:border-stone-700/80 bg-stone-50 dark:bg-stone-900/50 text-stone-900 dark:text-white text-sm focus:outline-none focus:ring-2 focus:ring-brand-500/50 focus:bg-white dark:focus:bg-stone-900 transition-all">
                            </div>
                        </div>

                        <!-- Konu -->
                        <div>
                            <label for="subject" class="block text-sm font-medium text-stone-700 dark:text-stone-300 mb-2">Konu *</label>
                            <input type="text" id="subject" required placeholder="Proje Daveti / Soru" 
                                   class="w-full px-4 py-3 rounded-xl border border-stone-200 dark:border-stone-700/80 bg-stone-50 dark:bg-stone-900/50 text-stone-900 dark:text-white text-sm focus:outline-none focus:ring-2 focus:ring-brand-500/50 focus:bg-white dark:focus:bg-stone-900 transition-all">
                        </div>

                        <!-- Mesaj -->
                        <div>
                            <label for="message" class="block text-sm font-medium text-stone-700 dark:text-stone-300 mb-2">Mesajınız *</label>
                            <textarea id="message" rows="4" required placeholder="Düşüncelerinizi veya projenizi detaylandırın..." 
                                      class="w-full px-4 py-3 rounded-xl border border-stone-200 dark:border-stone-700/80 bg-stone-50 dark:bg-stone-900/50 text-stone-900 dark:text-white text-sm focus:outline-none focus:ring-2 focus:ring-brand-500/50 focus:bg-white dark:focus:bg-stone-900 transition-all resize-none"></textarea>
                        </div>

                        <!-- Submit Button -->
                        <button type="submit" id="submitBtn" 
                                class="w-full py-3.5 px-6 rounded-xl bg-brand-500 hover:bg-brand-600 text-white font-medium text-sm shadow-lg shadow-brand-500/20 transition-all flex items-center justify-center gap-2 group">
                            <span>Mesajı Gönder</span>
                            <i class="fa-solid fa-paper-plane text-xs group-hover:translate-x-1 transition-transform"></i>
                        </button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer class="bg-stone-900 text-stone-400 py-12 border-t border-stone-800">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col sm:flex-row items-center justify-between gap-6">
                <!-- Branding -->
                <div>
                    <a href="#hero" class="text-xl font-heading font-bold text-white tracking-tight">
                        Selin<span class="text-brand-500">.</span>
                    </a>
                    <p class="text-xs text-stone-500 mt-1">© 2026 Selin Yılmaz. Tüm hakları saklıdır.</p>
                </div>

                <!-- Social Links -->
                <div class="flex items-center space-x-4">
                    <a href="#" class="w-9 h-9 rounded-full bg-stone-800 flex items-center justify-center text-stone-400 hover:text-white hover:bg-brand-500 transition-all" aria-label="GitHub">
                        <i class="fa-brands fa-github"></i>
                    </a>
                    <a href="#" class="w-9 h-9 rounded-full bg-stone-800 flex items-center justify-center text-stone-400 hover:text-white hover:bg-brand-500 transition-all" aria-label="Twitter">
                        <i class="fa-brands fa-x-twitter"></i>
                    </a>
                    <a href="#" class="w-9 h-9 rounded-full bg-stone-800 flex items-center justify-center text-stone-400 hover:text-white hover:bg-brand-500 transition-all" aria-label="LinkedIn">
                        <i class="fa-brands fa-linkedin-in"></i>
                    </a>
                    <a href="#" class="w-9 h-9 rounded-full bg-stone-800 flex items-center justify-center text-stone-400 hover:text-white hover:bg-brand-500 transition-all" aria-label="Medium">
                        <i class="fa-brands fa-medium"></i>
                    </a>
                </div>
            </div>
        </div>
    </footer>

    <!-- BLOG POST MODAL READER -->
    <div id="blogModal" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 sm:p-6 bg-stone-900/60 backdrop-blur-sm">
        <div class="bg-white dark:bg-darkcard rounded-2xl w-full max-w-2xl max-h-[85vh] overflow-y-auto shadow-2xl border border-stone-200 dark:border-darkborder modal-animate flex flex-col">
            <!-- Modal Header -->
            <div class="sticky top-0 bg-white/90 dark:bg-darkcard/90 backdrop-blur-md px-6 py-4 border-b border-stone-100 dark:border-darkborder flex items-center justify-between z-10">
                <span id="modalCategory" class="px-2.5 py-1 rounded-md text-xs font-semibold uppercase bg-brand-50 dark:bg-brand-900/30 text-brand-600 dark:text-brand-300">
                    Kategori
                </span>
                <button onclick="closeModal()" class="w-8 h-8 rounded-full bg-stone-100 dark:bg-stone-800 text-stone-500 hover:text-stone-900 dark:hover:text-white flex items-center justify-center transition-colors">
                    <i class="fa-solid fa-xmark text-base"></i>
                </button>
            </div>

            <!-- Modal Content Body -->
            <div class="p-6 sm:p-8 space-y-4">
                <div class="flex items-center gap-3 text-xs text-stone-400 dark:text-stone-400">
                    <span id="modalDate"><i class="fa-regular fa-calendar mr-1"></i> Tarih</span>
                    <span>•</span>
                    <span id="modalReadTime"><i class="fa-regular fa-clock mr-1"></i> Okuma süresi</span>
                </div>

                <h2 id="modalTitle" class="text-2xl sm:text-3xl font-heading font-bold text-stone-900 dark:text-white leading-snug">
                    Post Başlığı
                </h2>

                <div class="w-full h-48 sm:h-64 rounded-xl overflow-hidden my-4">
                    <img id="modalImage" src="" alt="Blog Görseli" class="w-full h-full object-cover">
                </div>

                <div id="modalBody" class="text-stone-600 dark:text-stone-300 leading-relaxed space-y-4 text-base">
                    <!-- Dynamic Body Content -->
                </div>
            </div>

            <!-- Modal Footer -->
            <div class="p-4 bg-stone-50 dark:bg-stone-900/40 border-t border-stone-100 dark:border-darkborder flex justify-end">
                <button onclick="closeModal()" class="px-5 py-2 rounded-xl bg-stone-200 dark:bg-stone-800 hover:bg-stone-300 dark:hover:bg-stone-700 text-stone-800 dark:text-stone-200 text-sm font-medium transition-colors">
                    Kapat
                </button>
            </div>
        </div>
    </div>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // --- 1. SAMPLE BLOG DATA ---
        const blogPosts = [
            {
                id: 1,
                title: "2026'da Modern Minimalist Web Tasarım Trendleri",
                category: "tasarim",
                categoryLabel: "Tasarım",
                date: "14 Ekim 2026",
                readTime: "4 dk okuma",
                image: "https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?auto=format&fit=crop&w=600&q=80",
                excerpt: "Kullanıcı deneyimini ön plana çıkaran sade, tipografi odaklı ve mikro-etkileşimlerle zenginleştirilmiş yeni nesil tasarım anlayışları.",
                content: `
                    <p>Günümüz dijital dünyasında kullanıcıların dikkat süreleri her geçen gün kısalıyor. Bu durum, karmaşık arayüzler yerine yalın ve amaca yönelik tasarımların öne çıkmasını sağladı.</p>
                    <p> Minimalizm sadece nesneleri azaltmak değildir; doğru bilgiyi doğru tipografi ve alan yönetimiyle sunmaktır. 2026 yılında göz yormayan doğal renk paletleri, akıcı mikro animasyonlar ve yüksek erişilebilirlik standartları ön planda kalmaya devam ediyor.</p>
                    <p>Özellikle mobil deneyimlerde gereksiz visual gürültüyü temizlemek, dönüşüm oranlarını doğrudan artıran en kritik faktörlerden biridir.</p>
                `
            },
            {
                id: 2,
                title: "Tailwind CSS ile Performanslı ve Temiz Arayüzler",
                category: "yazilim",
                categoryLabel: "Yazılım",
                date: "02 Eylül 2026",
                readTime: "6 dk okuma",
                image: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?auto=format&fit=crop&w=600&q=80",
                excerpt: "Utility-first yaklaşımının projelerinize kattığı hız, standartlaşma ve dosya boyutu avantajlarını detaylarıyla inceliyoruz.",
                content: `
                    <p>Tailwind CSS, geleneksel CSS yazım alışkanlıklarını kökten değiştiren en güçlü araçlardan biri oldu. HTML içerisinde direkt olarak styling yapabilmek, projedeki CSS dosya boyutunu inanılmaz derecede küçültüyor.</p>
                    <p>JIT (Just-In-Time) derleyicisi sayesinde yalnızca kullandığınız sınıflar nihai pakete dahil edilir. Bu da milisaniyeler seviyesinde yüklenme süreleri sunar.</p>
                    <p>Ayrıca tasarım sisteminizi Tailwind konfigürasyon dosyasında tek bir yerden yönetebilmeniz, ekip çalışmasında tam bir tutarlılık sağlar.</p>
                `
            },
            {
                id: 3,
                title: "Geliştiriciler İçin Günlük Odaklanma ve Verimlilik",
                category: "verimlilik",
                categoryLabel: "Verimlilik",
                date: "18 Ağustos 2026",
                readTime: "5 dk okuma",
                image: "https://images.unsplash.com/photo-1499750310107-5fef28a66643?auto=format&fit=crop&w=600&q=80",
                excerpt: "Derin çalışma (Deep Work) alışkanlığı kazanarak kod kalitesini artırma ve zihinsel yorgunluğu önleme yöntemleri.",
                content: `
                    <p>Kod yazmak yalnızca klavyeye basmak değil, sürekli problem çözme sürecidir. Bu süreçte dikkat dağıtıcı unsurlar (bildirimler, e-postalar) derinleşme sürenizi kesintiye uğratır.</p>
                    <p>Pomodoro tekniği ve Zaman Bloklama (Time Blocking) metodolojilerini birlikte kullanarak gününüzü planlamak, daha kısa sürede daha kaliteli kod üretmenize yardımcı olur.</p>
                    <p>Günün ilk 2 saatini hiçbir bildirime bakmadan en zorlu göreve ayırmak (Eat the Frog) günün geri kalanını çok daha huzurlu geçirmenizi sağlar.</p>
                `
            }
        ];

        // --- 2. RENDER BLOG POSTS ---
        function renderBlogPosts(posts) {
            const grid = document.getElementById('blogGrid');
            const emptyState = document.getElementById('emptyState');
            
            grid.innerHTML = '';

            if (posts.length === 0) {
                emptyState.classList.remove('hidden');
                return;
            } else {
                emptyState.classList.add('hidden');
            }

            posts.forEach(post => {
                const card = document.createElement('article');
                card.className = "bg-white dark:bg-darkcard rounded-2xl overflow-hidden border border-stone-200/80 dark:border-darkborder shadow-sm hover:shadow-xl hover:-translate-y-1 transition-all duration-300 flex flex-col cursor-pointer group";
                card.onclick = () => openModal(post.id);

                card.innerHTML = `
                    <div class="relative h-48 overflow-hidden bg-stone-100 dark:bg-stone-800">
                        <img src="${post.image}" alt="${post.title}" 
                             class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500"
                             onerror="this.onerror=null; this.src='https://placehold.co/600x400/d97757/ffffff?text=Blog';">
                        <span class="absolute top-3 left-3 px-2.5 py-1 rounded-md text-xs font-semibold bg-white/90 dark:bg-darkcard/90 backdrop-blur-md text-stone-800 dark:text-stone-200 shadow-sm">
                            ${post.categoryLabel}
                        </span>
                    </div>
                    <div class="p-6 flex flex-col flex-grow">
                        <div class="flex items-center gap-3 text-xs text-stone-400 mb-3">
                            <span><i class="fa-regular fa-calendar mr-1"></i>${post.date}</span>
                            <span>•</span>
                            <span><i class="fa-regular fa-clock mr-1"></i>${post.readTime}</span>
                        </div>
                        <h3 class="text-xl font-heading font-bold text-stone-900 dark:text-white group-hover:text-brand-500 dark:group-hover:text-brand-500 transition-colors mb-2 leading-snug">
                            ${post.title}
                        </h3>
                        <p class="text-stone-600 dark:text-stone-400 text-sm line-clamp-3 mb-6 flex-grow leading-relaxed">
                            ${post.excerpt}
                        </p>
                        <div class="flex items-center text-brand-500 font-medium text-sm group-hover:translate-x-1 transition-transform">
                            <span>Devamını Oku</span>
                            <i class="fa-solid fa-arrow-right text-xs ml-1.5"></i>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // --- 3. FILTER & SEARCH LOGIC ---
        const searchInput = document.getElementById('searchInput');
        const categoryFilter = document.getElementById('categoryFilter');

        function filterPosts() {
            const query = searchInput.value.toLowerCase().trim();
            const selectedCategory = categoryFilter.value;

            const filtered = blogPosts.filter(post => {
                const matchesQuery = post.title.toLowerCase().includes(query) || post.excerpt.toLowerCase().includes(query);
                const matchesCategory = selectedCategory === 'all' || post.category === selectedCategory;
                return matchesQuery && matchesCategory;
            });

            renderBlogPosts(filtered);
        }

        searchInput.addEventListener('input', filterPosts);
        categoryFilter.addEventListener('change', filterPosts);

        // --- 4. MODAL READER LOGIC ---
        function openModal(postId) {
            const post = blogPosts.find(p => p.id === postId);
            if (!post) return;

            document.getElementById('modalTitle').innerText = post.title;
            document.getElementById('modalCategory').innerText = post.categoryLabel;
            document.getElementById('modalDate').innerHTML = `<i class="fa-regular fa-calendar mr-1"></i> ${post.date}`;
            document.getElementById('modalReadTime').innerHTML = `<i class="fa-regular fa-clock mr-1"></i> ${post.readTime}`;
            document.getElementById('modalImage').src = post.image;
            document.getElementById('modalBody').innerHTML = post.content;

            const modal = document.getElementById('blogModal');
            modal.classList.remove('hidden');
            document.body.style.overflow = 'hidden'; // Lock scroll
        }

        function closeModal() {
            const modal = document.getElementById('blogModal');
            modal.classList.add('hidden');
            document.body.style.overflow = 'auto'; // Unlock scroll
        }

        // Close modal on outer overlay click
        document.getElementById('blogModal').addEventListener('click', (e) => {
            if (e.target === document.getElementById('blogModal')) {
                closeModal();
            }
        });

        // --- 5. CONTACT FORM HANDLER ---
        function handleFormSubmit(e) {
            e.preventDefault();
            const btn = document.getElementById('submitBtn');
            const alertBox = document.getElementById('successAlert');

            // Simulate loading state
            btn.disabled = true;
            btn.innerHTML = `<i class="fa-solid fa-spinner animate-spin text-sm"></i> Gönderiliyor...`;

            setTimeout(() => {
                btn.disabled = false;
                btn.innerHTML = `<span>Mesajı Gönder</span> <i class="fa-solid fa-paper-plane text-xs"></i>`;
                
                // Show success alert
                alertBox.classList.remove('hidden');
                document.getElementById('contactForm').reset();

                // Auto hide alert after 5 seconds
                setTimeout(() => {
                    alertBox.classList.add('hidden');
                }, 5000);
            }, 1000);
        }

        // --- 6. DARK MODE TOGGLE ---
        const themeToggleBtn = document.getElementById('themeToggle');
        const themeIcon = document.getElementById('themeIcon');

        // Check stored theme preference or system setting
        if (localStorage.getItem('color-theme') === 'dark' || (!('color-theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            document.documentElement.classList.add('dark');
            themeIcon.className = 'fa-solid fa-sun text-lg text-amber-400';
        } else {
            document.documentElement.classList.remove('dark');
            themeIcon.className = 'fa-solid fa-moon text-lg';
        }

        themeToggleBtn.addEventListener('click', () => {
            if (document.documentElement.classList.contains('dark')) {
                document.documentElement.classList.remove('dark');
                localStorage.setItem('color-theme', 'light');
                themeIcon.className = 'fa-solid fa-moon text-lg';
            } else {
                document.documentElement.classList.add('dark');
                localStorage.setItem('color-theme', 'dark');
                themeIcon.className = 'fa-solid fa-sun text-lg text-amber-400';
            }
        });

        // --- 7. MOBILE MENU TOGGLE ---
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        const mobileNavLinks = document.querySelectorAll('.mobile-nav-link');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Close mobile menu on link click
        mobileNavLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });

        // --- INITIAL RENDER ---
        window.onload = function() {
            renderBlogPosts(blogPosts);
        };
    </script>
</body>
</html>
