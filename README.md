<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Syhdhuda - Web Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #ff6f61;
            --secondary: #ffd369;
            --accent: #61dafb;
            --dark: #1a1a2e;
            --darker: #0d0d1a;
            --light: #f8f9fa;
            --gray: #cccccc;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(135deg, var(--darker), var(--dark));
            color: var(--light);
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
            background-attachment: fixed;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header Styles */
        .header {
            text-align: center;
            padding: 50px 0 30px;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at top right, rgba(255, 111, 97, 0.1), transparent 70%);
            z-index: -1;
        }
        
        .header h1 {
            font-family: 'Poppins', sans-serif;
            font-size: 3.5rem;
            color: var(--primary);
            margin-bottom: 15px;
            animation: fadeIn 1s ease-in, glow 2s infinite alternate;
        }
        
        .header h1 span {
            color: var(--secondary);
            position: relative;
        }
        
        .header h1 span::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--secondary), transparent);
            animation: underline 3s infinite;
        }
        
        .header p {
            font-size: 1.4rem;
            color: var(--gray);
            max-width: 800px;
            margin: 0 auto 30px;
        }
        
        .header p strong {
            color: var(--secondary);
            font-weight: 600;
        }
        
        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid rgba(255, 211, 105, 0.3);
            box-shadow: 0 0 30px rgba(255, 111, 97, 0.5);
            margin: 20px auto;
            display: block;
            transition: var(--transition);
        }
        
        .profile-img:hover {
            transform: scale(1.05);
            box-shadow: 0 0 40px rgba(255, 111, 97, 0.8);
        }
        
        /* Section Styles */
        .section {
            background: rgba(26, 26, 46, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
        }
        
        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
        }
        
        .section-title {
            font-family: 'Poppins', sans-serif;
            color: var(--accent);
            font-size: 2rem;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .section-title i {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 1.8rem;
        }
        
        /* Grid Layout */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }
        
        .card {
            background: rgba(30, 30, 50, 0.6);
            border-radius: 15px;
            padding: 25px;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .card:hover {
            background: rgba(40, 40, 60, 0.8);
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .card h3 {
            color: var(--secondary);
            font-size: 1.4rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card h3 i {
            color: var(--primary);
        }
        
        .card ul {
            padding-left: 25px;
        }
        
        .card li {
            margin-bottom: 10px;
            position: relative;
        }
        
        .card li::before {
            content: "▹";
            color: var(--accent);
            position: absolute;
            left: -20px;
        }
        
        /* Projects Section */
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 20px;
        }
        
        .project-card {
            background: linear-gradient(135deg, rgba(26, 26, 46, 0.8), rgba(30, 30, 50, 0.9));
            border-radius: 15px;
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
        }
        
        .project-img {
            height: 180px;
            background: linear-gradient(45deg, #2c3e50, #4a4e69);
            display: flex;
            align-items: center;
            justify-content: center;
            border-bottom: 2px solid var(--primary);
        }
        
        .project-img i {
            font-size: 5rem;
            color: var(--accent);
            opacity: 0.7;
        }
        
        .project-content {
            padding: 20px;
        }
        
        .project-content h3 {
            color: var(--secondary);
            font-size: 1.5rem;
            margin-bottom: 10px;
        }
        
        .project-content p {
            color: var(--gray);
            margin-bottom: 15px;
            min-height: 60px;
        }
        
        .project-link {
            display: inline-block;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: var(--darker);
            padding: 8px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }
        
        .project-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 111, 97, 0.4);
        }
        
        /* Tech Stack */
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .tech-item {
            background: rgba(40, 40, 60, 0.8);
            padding: 12px 25px;
            border-radius: 30px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .tech-item:hover {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: var(--darker);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 111, 97, 0.3);
        }
        
        /* Stats */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .stat-card {
            background: linear-gradient(135deg, rgba(26, 26, 46, 0.8), rgba(30, 30, 50, 0.9));
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .stat-value {
            font-size: 3rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--accent), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 10px 0;
        }
        
        .stat-label {
            color: var(--gray);
            font-size: 1.1rem;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 30px 0;
            color: var(--gray);
            font-size: 1.1rem;
        }
        
        .visitor-badge {
            display: inline-block;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: var(--darker);
            padding: 8px 20px;
            border-radius: 30px;
            font-weight: 600;
            margin-top: 15px;
            box-shadow: 0 5px 15px rgba(255, 111, 97, 0.3);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes glow {
            0% { text-shadow: 0 0 5px rgba(255, 111, 97, 0.5); }
            100% { text-shadow: 0 0 20px rgba(255, 111, 97, 0.8), 0 0 30px rgba(255, 211, 105, 0.6); }
        }
        
        @keyframes underline {
            0% { transform: scaleX(0); opacity: 0; }
            50% { transform: scaleX(1); opacity: 1; }
            100% { transform: scaleX(0); opacity: 0; }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .header p {
                font-size: 1.1rem;
            }
            
            .section-title {
                font-size: 1.7rem;
            }
            
            .grid, .projects, .stats {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <h1>👋 Halo, Saya <span>Syhdhuda</span>!</h1>
            <p>Seorang <strong>Web Developer</strong> yang antusias membangun solusi digital dengan <strong>HTML</strong>, <strong>CSS</strong>, <strong>PHP</strong>, dan <strong>Laravel</strong> 🚀</p>
            <img src="https://media.giphy.com/media/L1R1tvI9svkIWwpVYr/giphy.gif" class="profile-img" alt="Coding Animation">
        </header>

        <!-- Working On Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-hammer"></i> Sedang Mengerjakan</h2>
            <div class="grid">
                <div class="card">
                    <h3><i class="fas fa-rocket"></i> Proyek Laravel</h3>
                    <ul>
                        <li>Aplikasi berbasis Laravel dan Livewire</li>
                        <li>Pengembangan arsitektur modular</li>
                        <li>Integrasi sistem pembayaran</li>
                    </ul>
                </div>
                <div class="card">
                    <h3><i class="fas fa-paint-brush"></i> Desain UI/UX</h3>
                    <ul>
                        <li>Desain modern & responsif dengan Tailwind CSS</li>
                        <li>Optimasi pengalaman pengguna</li>
                        <li>Animasi interaktif dengan GSAP</li>
                    </ul>
                </div>
                <div class="card">
                    <h3><i class="fas fa-code"></i> Pengembangan API</h3>
                    <ul>
                        <li>Eksplorasi arsitektur REST API</li>
                        <li>Pengembangan SPA sederhana</li>
                        <li>Integrasi dengan layanan third-party</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Learning Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-book-open"></i> Sedang Dipelajari</h2>
            <div class="grid">
                <div class="card">
                    <h3><i class="fas fa-tachometer-alt"></i> Optimasi Performa</h3>
                    <ul>
                        <li>Optimasi performa Laravel & caching</li>
                        <li>Database indexing & query optimization</li>
                        <li>Load balancing & server scaling</li>
                    </ul>
                </div>
                <div class="card">
                    <h3><i class="fas fa-palette"></i> Desain Lanjutan</h3>
                    <ul>
                        <li>Advanced Tailwind customization</li>
                        <li>Animasi dengan GSAP & Anime.js</li>
                        <li>Responsive design patterns</li>
                    </ul>
                </div>
                <div class="card">
                    <h3><i class="fas fa-lock"></i> Keamanan</h3>
                    <ul>
                        <li>Autentikasi Laravel Fortify & Sanctum</li>
                        <li>Pencegahan serangan web umum</li>
                        <li>Enkripsi data & best practices</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Collaboration Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-handshake"></i> Terbuka untuk Kolaborasi</h2>
            <div class="grid">
                <div class="card">
                    <h3><i class="fab fa-laravel"></i> Proyek Open-Source</h3>
                    <ul>
                        <li>Pengembangan paket Laravel</li>
                        <li>Kontribusi ke proyek open-source</li>
                        <li>Tooling untuk developer</li>
                    </ul>
                </div>
                <div class="card">
                    <h3><i class="fas fa-laptop-code"></i> Website Kreatif</h3>
                    <ul>
                        <li>Website dengan UX menarik</li>
                        <li>Platform edukasi digital</li>
                        <li>Solusi e-commerce inovatif</li>
                    </ul>
                </div>
                <div class="card">
                    <h3><i class="fas fa-chart-line"></i> Sistem Manajemen</h3>
                    <ul>
                        <li>Dashboard analitik data</li>
                        <li>Sistem manajemen konten</li>
                        <li>Aplikasi manajemen bisnis</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-star"></i> Proyek Unggulan</h2>
            <div class="projects">
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-tasks"></i>
                    </div>
                    <div class="project-content">
                        <h3>To-Do App</h3>
                        <p>Aplikasi manajemen tugas dengan Laravel, Livewire, dan Tailwind CSS. Fitur drag & drop, reminder, dan kolaborasi tim.</p>
                        <a href="[tautan-repo]" class="project-link">Lihat di GitHub</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <div class="project-content">
                        <h3>E-Commerce</h3>
                        <p>Platform toko online dengan PHP & MySQL. Lengkap dengan manajemen produk, keranjang belanja, dan integrasi pembayaran.</p>
                        <a href="https://kasir.syahda.web.id/login" target="_blank" class="project-link">Lihat Demo</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-laptop-code"></i> Tech Stack</h2>
            <div class="tech-stack">
                <div class="tech-item"><i class="fab fa-html5"></i> HTML5</div>
                <div class="tech-item"><i class="fab fa-css3-alt"></i> CSS3</div>
                <div class="tech-item"><i class="fab fa-php"></i> PHP</div>
                <div class="tech-item"><i class="fab fa-laravel"></i> Laravel</div>
                <div class="tech-item"><i class="fab fa-js"></i> JavaScript</div>
                <div class="tech-item"><i class="fab fa-vuejs"></i> Vue.js</div>
                <div class="tech-item"><i class="fas fa-bolt"></i> Livewire</div>
                <div class="tech-item"><i class="fas fa-wind"></i> Tailwind CSS</div>
                <div class="tech-item"><i class="fas fa-database"></i> MySQL</div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-chart-bar"></i> GitHub Statistik</h2>
            <div class="stats">
                <div class="stat-card">
                    <div class="stat-value">1500+</div>
                    <div class="stat-label">Komit Kode</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">25+</div>
                    <div class="stat-label">Proyek</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">10+</div>
                    <div class="stat-label">Kontribusi</div>
                </div>
            </div>
        </section>

        <!-- Fun Facts Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-lightbulb"></i> Fakta Menarik</h2>
            <div class="grid">
                <div class="card">
                    <h3><i class="fas fa-puzzle-piece"></i> Problem Solving</h3>
                    <p>Saya suka memecah logika kompleks menjadi UI yang elegan dan mudah digunakan. Tantangan teknis adalah motivator terbaik saya.</p>
                </div>
                <div class="card">
                    <h3><i class="fas fa-moon"></i> Coding Malam</h3>
                    <p>Pecinta kopi + coding malam = ide kreatif tak terbendung! Beberapa solusi terbaik saya muncul saat larut malam.</p>
                </div>
                <div class="card">
                    <h3><i class="fas fa-cogs"></i> Rasa Ingin Tahu</h3>
                    <p>Selalu penasaran dengan cara kerja hal-hal di balik layar. Saya senang mengutak-atik teknologi baru untuk memahami prinsip dasarnya.</p>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>© 2023 Syhdhuda | Web Developer</p>
            <div class="visitor-badge">
                <i class="fas fa-eye"></i> Pengunjung: 1,247
            </div>
        </footer>
    </div>
</body>
</html>
