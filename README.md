<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Syhdhuda - Web Developer</title>
    <!-- Font Awesome untuk ikon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary-color: #ff6f61;
            --secondary-color: #ffd369;
            --accent-color: #61dafb;
            --dark-bg: #0d1117;
            --card-bg: #161b22;
            --text-color: #cccccc;
            --text-light: #8b949e;
            --border-color: #30363d;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--dark-bg);
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header Section */
        .header {
            text-align: center;
            padding: 40px 20px;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,111,97,0.1) 0%, rgba(255,111,97,0) 70%);
            z-index: -1;
            animation: pulse 8s infinite alternate;
        }
        
        .profile-pic {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid var(--primary-color);
            margin: 0 auto 20px;
            overflow: hidden;
            position: relative;
            box-shadow: 0 0 25px rgba(255, 111, 97, 0.4);
            animation: float 6s ease-in-out infinite;
        }
        
        .profile-pic img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .name {
            font-size: 2.8rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: textGlow 3s ease-in-out infinite alternate;
        }
        
        .tagline {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 30px;
            color: var(--text-light);
        }
        
        .highlight {
            color: var(--secondary-color);
            font-weight: 600;
        }
        
        /* Tech Stack */
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
        }
        
        .tech-item {
            background-color: var(--card-bg);
            padding: 10px 20px;
            border-radius: 30px;
            display: flex;
            align-items: center;
            gap: 10px;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease-out forwards;
            opacity: 0;
        }
        
        .tech-item:hover {
            transform: translateY(-5px);
            border-color: var(--primary-color);
            box-shadow: 0 5px 15px rgba(255, 111, 97, 0.2);
        }
        
        .tech-item:nth-child(1) { animation-delay: 0.1s; }
        .tech-item:nth-child(2) { animation-delay: 0.2s; }
        .tech-item:nth-child(3) { animation-delay: 0.3s; }
        .tech-item:nth-child(4) { animation-delay: 0.4s; }
        .tech-item:nth-child(5) { animation-delay: 0.5s; }
        .tech-item:nth-child(6) { animation-delay: 0.6s; }
        
        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
        .stat-card {
            background-color: var(--card-bg);
            border-radius: 12px;
            padding: 25px;
            text-align: center;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease-out forwards;
            opacity: 0;
        }
        
        .stat-card:nth-child(1) { animation-delay: 0.2s; }
        .stat-card:nth-child(2) { animation-delay: 0.4s; }
        .stat-card:nth-child(3) { animation-delay: 0.6s; }
        
        .stat-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary-color);
            box-shadow: 0 10px 25px rgba(255, 111, 97, 0.15);
        }
        
        .stat-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }
        
        .stat-number {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 5px;
            color: var(--secondary-color);
        }
        
        .stat-label {
            font-size: 1rem;
            color: var(--text-light);
        }
        
        /* Projects Section */
        .section-title {
            font-size: 2rem;
            margin: 40px 0 20px;
            color: var(--secondary-color);
            text-align: center;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 2px;
        }
        
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }
        
        .project-card {
            background-color: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease-out forwards;
            opacity: 0;
        }
        
        .project-card:nth-child(1) { animation-delay: 0.2s; }
        .project-card:nth-child(2) { animation-delay: 0.4s; }
        .project-card:nth-child(3) { animation-delay: 0.6s; }
        
        .project-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-color);
            box-shadow: 0 15px 30px rgba(97, 218, 251, 0.1);
        }
        
        .project-img {
            height: 180px;
            overflow: hidden;
        }
        
        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .project-card:hover .project-img img {
            transform: scale(1.05);
        }
        
        .project-content {
            padding: 20px;
        }
        
        .project-title {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--secondary-color);
        }
        
        .project-desc {
            font-size: 0.95rem;
            color: var(--text-light);
            margin-bottom: 15px;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }
        
        .project-tech span {
            background-color: rgba(255, 111, 97, 0.1);
            color: var(--primary-color);
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        
        .project-link {
            display: inline-block;
            color: var(--accent-color);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .project-link:hover {
            color: var(--secondary-color);
            transform: translateX(5px);
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 20px;
            margin-top: 40px;
            border-top: 1px solid var(--border-color);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--card-bg);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-color);
            font-size: 1.2rem;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background-color: var(--primary-color);
            color: white;
            transform: translateY(-5px);
        }
        
        .copyright {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-top: 20px;
        }
        
        /* Animations */
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); opacity: 0.7; }
            100% { transform: scale(1.1); opacity: 0.3; }
        }
        
        @keyframes textGlow {
            0% { text-shadow: 0 0 10px rgba(255, 111, 97, 0.5); }
            100% { text-shadow: 0 0 20px rgba(255, 111, 97, 0.8), 0 0 30px rgba(255, 111, 97, 0.4); }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .name { font-size: 2.2rem; }
            .tagline { font-size: 1rem; }
            .stats { grid-template-columns: 1fr; }
            .projects { grid-template-columns: 1fr; }
        }
        
        /* Typewriter Effect */
        .typewriter {
            overflow: hidden;
            border-right: 3px solid var(--primary-color);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 1px;
            animation: typing 3.5s steps(40, end), blink 0.75s step-end infinite;
            animation-fill-mode: both;
        }
        
        /* Floating Elements */
        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: -1;
            overflow: hidden;
        }
        
        .floating-element {
            position: absolute;
            background-color: rgba(255, 111, 97, 0.05);
            border-radius: 50%;
        }
        
        .floating-element:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 10%;
            left: 5%;
            animation: floatElement 25s infinite linear;
        }
        
        .floating-element:nth-child(2) {
            width: 120px;
            height: 120px;
            top: 60%;
            right: 10%;
            animation: floatElement 30s infinite linear reverse;
        }
        
        .floating-element:nth-child(3) {
            width: 60px;
            height: 60px;
            bottom: 20%;
            left: 15%;
            animation: floatElement 20s infinite linear;
        }
        
        @keyframes floatElement {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-1000px) rotate(720deg); }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-element"></div>
        <div class="floating-element"></div>
        <div class="floating-element"></div>
    </div>
    
    <div class="container">
        <header class="header">
            <div class="profile-pic">
                <img src="https://avatars.githubusercontent.com/u/12345678?v=4" alt="Syhdhuda">
            </div>
            
            <h1 class="name">Syhdhuda</h1>
            
            <div class="typewriter">
                <p class="tagline">Seorang <span class="highlight">Web Developer</span> yang antusias membangun solusi digital dengan <span class="highlight">Laravel</span>, <span class="highlight">PHP</span>, dan teknologi web modern 🚀</p>
            </div>
            
            <div class="tech-stack">
                <div class="tech-item">
                    <i class="fab fa-laravel"></i>
                    <span>Laravel</span>
                </div>
                <div class="tech-item">
                    <i class="fab fa-php"></i>
                    <span>PHP</span>
                </div>
                <div class="tech-item">
                    <i class="fab fa-html5"></i>
                    <span>HTML5</span>
                </div>
                <div class="tech-item">
                    <i class="fab fa-css3-alt"></i>
                    <span>CSS3</span>
                </div>
                <div class="tech-item">
                    <i class="fab fa-js"></i>
                    <span>JavaScript</span>
                </div>
                <div class="tech-item">
                    <i class="fas fa-database"></i>
                    <span>MySQL</span>
                </div>
            </div>
        </header>
        
        <section class="stats">
            <div class="stat-card">
                <div class="stat-icon">
                    <i class="fas fa-code"></i>
                </div>
                <div class="stat-number">50+</div>
                <div class="stat-label">Proyek Selesai</div>
            </div>
            
            <div class="stat-card">
                <div class="stat-icon">
                    <i class="fas fa-clock"></i>
                </div>
                <div class="stat-number">3+</div>
                <div class="stat-label">Tahun Pengalaman</div>
            </div>
            
            <div class="stat-card">
                <div class="stat-icon">
                    <i class="fas fa-users"></i>
                </div>
                <div class="stat-number">100%</div>
                <div class="stat-label">Kepuasan Klien</div>
            </div>
        </section>
        
        <h2 class="section-title">Proyek Unggulan</h2>
        
        <section class="projects">
            <div class="project-card">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="E-Commerce Project">
                </div>
                <div class="project-content">
                    <h3 class="project-title">Sistem E-Commerce</h3>
                    <p class="project-desc">Platform toko online lengkap dengan manajemen produk, keranjang belanja, checkout, dan dashboard admin.</p>
                    <div class="project-tech">
                        <span>Laravel</span>
                        <span>MySQL</span>
                        <span>Tailwind CSS</span>
                        <span>Livewire</span>
                    </div>
                    <a href="https://kasir.syahda.web.id/login" target="_blank" class="project-link">
                        Lihat Demo <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="To-Do App">
                </div>
                <div class="project-content">
                    <h3 class="project-title">Aplikasi To-Do</h3>
                    <p class="project-desc">Aplikasi manajemen tugas dengan fitur drag & drop, kategori, prioritas, dan reminder notifikasi.</p>
                    <div class="project-tech">
                        <span>Laravel</span>
                        <span>Vue.js</span>
                        <span>REST API</span>
                        <span>PWA</span>
                    </div>
                    <a href="#" class="project-link">
                        Lihat di GitHub <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Dashboard Admin">
                </div>
                <div class="project-content">
                    <h3 class="project-title">Dashboard Admin</h3>
                    <p class="project-desc">Dashboard analitik dengan grafik interaktif, manajemen pengguna, laporan, dan sistem role-based.</p>
                    <div class="project-tech">
                        <span>Laravel</span>
                        <span>Chart.js</span>
                        <span>Bootstrap</span>
                        <span>AJAX</span>
                    </div>
                    <a href="#" class="project-link">
                        Lihat Detail <i class="fas fa-arrow-right"></i>
                    </a>
                </div>
            </div>
        </section>
        
        <h2 class="section-title">Aktivitas Terbaru</h2>
        
        <section class="stats">
            <div class="stat-card">
                <div class="stat-icon">
                    <i class="fas fa-tasks"></i>
                </div>
                <div class="stat-number">🚀</div>
                <div class="stat-label">Membangun Aplikasi Laravel & Livewire</div>
            </div>
            
            <div class="stat-card">
                <div class="stat-icon">
                    <i class="fas fa-graduation-cap"></i>
                </div>
                <div class="stat-number">📘</div>
                <div class="stat-label">Mempelajari Optimasi Performa Laravel</div>
            </div>
            
            <div class="stat-card">
                <div class="stat-icon">
                    <i class="fas fa-hands-helping"></i>
                </div>
                <div class="stat-number">🤝</div>
                <div class="stat-label">Terbuka untuk Kolaborasi Proyek</div>
            </div>
        </section>
    </div>
    
    <footer class="footer">
        <div class="social-links">
            <a href="https://github.com/syhdhuda" target="_blank" class="social-link">
                <i class="fab fa-github"></i>
            </a>
            <a href="https://www.linkedin.com/in/syhdhuda" target="_blank" class="social-link">
                <i class="fab fa-linkedin-in"></i>
            </a>
            <a href="https://twitter.com/syhdhuda" target="_blank" class="social-link">
                <i class="fab fa-twitter"></i>
            </a>
            <a href="mailto:syhdhuda@example.com" class="social-link">
                <i class="fas fa-envelope"></i>
            </a>
        </div>
        
        <p class="copyright">© 2023 Syhdhuda. Dibuat dengan ❤️ menggunakan HTML, CSS, dan JavaScript.</p>
        
        <div style="margin-top: 20px;">
            <img src="https://komarev.com/ghpvc/?username=syhdhuda&style=flat-square&color=ff6f61" alt="Visitor Badge" />
        </div>
    </footer>
    
    <script>
        // Tambahkan animasi scroll
        document.addEventListener('DOMContentLoaded', function() {
            // Animasi untuk elemen saat scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);
            
            // Terapkan observer ke elemen yang ingin dianimasikan
            document.querySelectorAll('.stat-card, .project-card, .tech-item').forEach(el => {
                observer.observe(el);
            });
            
            // Efek ketik otomatis untuk tagline
            const tagline = document.querySelector('.tagline');
            const originalText = tagline.textContent;
            tagline.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < originalText.length) {
                    tagline.textContent += originalText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 30);
                }
            }
            
            // Mulai efek ketik setelah halaman dimuat
            setTimeout(typeWriter, 1000);
            
            // Animasi untuk elemen floating
            const floatingElements = document.querySelectorAll('.floating-element');
            floatingElements.forEach((el, index) => {
                // Set random position untuk mobile
                if (window.innerWidth < 768) {
                    const positions = [
                        {top: '5%', left: '2%'},
                        {top: '70%', right: '5%'},
                        {bottom: '10%', left: '5%'}
                    ];
                    
                    if (positions[index]) {
                        el.style.top = positions[index].top;
                        el.style.left = positions[index].left;
                        if (positions[index].right) {
                            el.style.right = positions[index].right;
                            el.style.left = 'auto';
                        }
                    }
                }
            });
        });
    </script>
</body>
</html>
