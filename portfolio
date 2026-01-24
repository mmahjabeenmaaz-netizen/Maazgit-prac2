<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Of Photography | RGB Pro Edition</title>
    
    <!-- External Libraries -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;500;700&display=swap" rel="stylesheet">

    <style>
        /* =========================================
           1. CORE VARIABLES & RESET
           ========================================= */
        :root {
            --primary-rgb-red: #ff003c;
            --primary-rgb-green: #00ff9f;
            --primary-rgb-blue: #00f0ff;
            --bg-dark: #050505;
            --bg-panel: #111111;
            --text-main: #e0e0e0;
            --text-muted: #888888;
            --font-head: 'Orbitron', sans-serif;
            --font-body: 'Rajdhani', sans-serif;
        }

        * {
            box-sizing: border-box;
            scrollbar-width: thin;
            scrollbar-color: var(--primary-rgb-blue) var(--bg-dark);
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: var(--font-body);
            overflow-x: hidden;
            cursor: none; /* Hiding default cursor for custom one */
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-dark);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--primary-rgb-blue);
            border-radius: 4px;
        }

        /* =========================================
           2. CUSTOM CURSOR
           ========================================= */
        #cursor-dot, #cursor-outline {
            position: fixed;
            top: 0;
            left: 0;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            z-index: 9999;
            pointer-events: none;
        }
        #cursor-dot {
            width: 8px;
            height: 8px;
            background-color: var(--primary-rgb-green);
        }
        #cursor-outline {
            width: 40px;
            height: 40px;
            border: 2px solid var(--primary-rgb-blue);
            transition: width 0.2s, height 0.2s, background-color 0.2s;
        }
        body.hovering #cursor-outline {
            width: 60px;
            height: 60px;
            background-color: rgba(0, 240, 255, 0.1);
            border-color: var(--primary-rgb-green);
        }

        /* =========================================
           3. ANIMATIONS & KEYFRAMES
           ========================================= */
        @keyframes glow-red {
            0% { box-shadow: 0 0 5px var(--primary-rgb-red); }
            50% { box-shadow: 0 0 20px var(--primary-rgb-red), 0 0 10px var(--primary-rgb-red) inset; }
            100% { box-shadow: 0 0 5px var(--primary-rgb-red); }
        }
        @keyframes glow-blue {
            0% { box-shadow: 0 0 5px var(--primary-rgb-blue); }
            50% { box-shadow: 0 0 20px var(--primary-rgb-blue), 0 0 10px var(--primary-rgb-blue) inset; }
            100% { box-shadow: 0 0 5px var(--primary-rgb-blue); }
        }
        @keyframes rgb-border-flow {
            0% { border-color: var(--primary-rgb-red); }
            33% { border-color: var(--primary-rgb-green); }
            66% { border-color: var(--primary-rgb-blue); }
            100% { border-color: var(--primary-rgb-red); }
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }
        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }
        @keyframes reveal {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .reveal-on-scroll {
            opacity: 0;
            transition: all 0.8s ease-out;
        }
        .reveal-on-scroll.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* =========================================
           4. TYPOGRAPHY & UTILITIES
           ========================================= */
        h1, h2, h3, h4, h5, h6 {
            font-family: var(--font-head);
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .text-gradient {
            background: linear-gradient(90deg, var(--primary-rgb-red), var(--primary-rgb-green), var(--primary-rgb-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% auto;
            animation: gradient-flow 3s linear infinite;
        }

        @keyframes gradient-flow {
            0% { background-position: 0% 50%; }
            100% { background-position: 200% 50%; }
        }

        .section-padding {
            padding: 100px 0;
        }

        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--primary-rgb-blue), transparent);
            width: 50%;
            margin: 40px auto;
        }

        /* =========================================
           5. NAVBAR
           ========================================= */
        .navbar {
            background: rgba(5, 5, 5, 0.8);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s ease;
            padding: 20px 0;
        }
        .navbar.scrolled {
            padding: 10px 0;
            background: rgba(5, 5, 5, 0.95);
            box-shadow: 0 5px 20px rgba(0, 240, 255, 0.1);
        }
        .navbar-brand {
            font-family: var(--font-head);
            font-size: 1.8rem;
            font-weight: 900;
            color: white !important;
        }
        .nav-link {
            color: var(--text-main) !important;
            font-weight: 500;
            font-size: 1.1rem;
            margin: 0 10px;
            position: relative;
        }
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-rgb-green);
            transition: width 0.3s;
        }
        .nav-link:hover::after {
            width: 100%;
        }

        /* =========================================
           6. HERO SECTION
           ========================================= */
        #hero {
            position: relative;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        /* Particle Canvas */
        #hero-canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            max-width: 900px;
            padding: 20px;
        }

        .hero-title {
            font-size: 5rem;
            line-height: 1.1;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(0,0,0,0.8);
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 40px;
            color: var(--primary-rgb-blue);
            letter-spacing: 5px;
        }

        .btn-glow {
            padding: 15px 40px;
            font-size: 1.2rem;
            font-family: var(--font-head);
            text-transform: uppercase;
            background: transparent;
            border: 2px solid var(--primary-rgb-red);
            color: white;
            position: relative;
            overflow: hidden;
            transition: all 0.3s;
        }
        .btn-glow:hover {
            background: var(--primary-rgb-red);
            box-shadow: 0 0 30px var(--primary-rgb-red);
            color: white;
            border-color: var(--primary-rgb-red);
        }

        /* =========================================
           7. STATS BAR
           ========================================= */
        .stats-bar {
            background: #000;
            border-bottom: 1px solid var(--primary-rgb-green);
            padding: 30px 0;
        }
        .stat-item h3 {
            font-size: 2.5rem;
            margin: 0;
            color: var(--primary-rgb-green);
        }
        .stat-item p {
            margin: 0;
            color: var(--text-muted);
            letter-spacing: 2px;
        }

        /* =========================================
           8. GALLERY / PORTFOLIO
           ========================================= */
        .filter-btn {
            background: #111;
            border: 1px solid #333;
            color: white;
            padding: 10px 25px;
            margin: 5px;
            border-radius: 0;
            font-family: var(--font-head);
            transition: 0.3s;
        }
        .filter-btn.active, .filter-btn:hover {
            background: var(--primary-rgb-blue);
            border-color: var(--primary-rgb-blue);
            color: black;
            box-shadow: 0 0 15px var(--primary-rgb-blue);
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 20px;
        }

        .gallery-card {
            position: relative;
            height: 300px;
            overflow: hidden;
            border: 1px solid transparent;
            cursor: none; /* using custom cursor */
        }
        
        .gallery-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
            filter: grayscale(40%);
        }

        .gallery-card:hover img {
            transform: scale(1.1);
            filter: grayscale(0%);
        }

        .gallery-overlay {
            position: absolute;
            bottom: -100%;
            left: 0;
            width: 100%;
            padding: 20px;
            background: linear-gradient(to top, rgba(0,0,0,0.9), transparent);
            transition: bottom 0.4s ease;
        }

        .gallery-card:hover .gallery-overlay {
            bottom: 0;
        }

        /* =========================================
           9. VIDEO SECTION (CINEMATIC)
           ========================================= */
        .video-wrapper {
            position: relative;
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            border: 2px solid var(--primary-rgb-red);
            box-shadow: 0 0 30px rgba(255, 0, 60, 0.2);
            animation: glow-red 4s infinite alternate;
        }
        .video-overlay-ui {
            position: absolute;
            top: 20px;
            left: 20px;
            border: 1px solid var(--primary-rgb-red);
            padding: 5px 15px;
            color: var(--primary-rgb-red);
            font-family: var(--font-head);
            font-size: 0.8rem;
            background: rgba(0,0,0,0.7);
        }

        /* =========================================
           10. SERVICES & PRICING
           ========================================= */
        .service-card {
            background: #111;
            border: 1px solid #333;
            padding: 40px;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }
        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--primary-rgb-red), var(--primary-rgb-blue));
        }
        .service-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary-rgb-blue);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        .service-icon {
            font-size: 3rem;
            color: var(--primary-rgb-green);
            margin-bottom: 20px;
        }

        /* =========================================
           11. FEEDBACK / TESTIMONIALS
           ========================================= */
        .testimonial-card {
            background: #0f0f0f;
            border-left: 4px solid var(--primary-rgb-green);
            padding: 30px;
            margin: 20px 0;
            position: relative;
        }
        .testimonial-card i {
            position: absolute;
            top: -15px;
            left: 20px;
            background: #0f0f0f;
            color: var(--primary-rgb-green);
            padding: 5px;
            font-size: 1.5rem;
        }

        /* =========================================
           12. AUTH & FORMS
           ========================================= */
        .rgb-input {
            background: #0a0a0a;
            border: 1px solid #333;
            color: white;
            padding: 15px;
            margin-bottom: 20px;
        }
        .rgb-input:focus {
            border-color: var(--primary-rgb-blue);
            box-shadow: 0 0 10px rgba(0, 240, 255, 0.3);
            background: #111;
        }

        /* =========================================
           13. AI ASSISTANT
           ========================================= */
        .ai-container {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 9999;
        }
        .ai-toggle {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary-rgb-blue), #001eff);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 20px var(--primary-rgb-blue);
            animation: float 3s infinite ease-in-out;
            cursor: pointer;
        }
        .ai-toggle:hover {
            transform: scale(1.1);
        }
        .ai-toggle i {
            font-size: 2rem;
            color: white;
        }
        .ai-window {
            position: absolute;
            bottom: 90px;
            right: 0;
            width: 350px;
            height: 500px;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            border: 1px solid var(--primary-rgb-blue);
            border-radius: 10px;
            display: none;
            flex-direction: column;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.8);
        }
        .ai-header {
            background: linear-gradient(90deg, var(--primary-rgb-blue), #001eff);
            padding: 15px;
            color: white;
            font-family: var(--font-head);
            display: flex;
            justify-content: space-between;
        }
        .ai-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            font-size: 0.9rem;
        }
        .msg-bubble {
            padding: 10px 15px;
            border-radius: 15px;
            margin-bottom: 10px;
            max-width: 80%;
            line-height: 1.4;
        }
        .msg-bot {
            background: #222;
            color: #ddd;
            border-bottom-left-radius: 2px;
        }
        .msg-user {
            background: var(--primary-rgb-blue);
            color: black;
            margin-left: auto;
            border-bottom-right-radius: 2px;
        }
        .ai-input-wrap {
            padding: 10px;
            background: #050505;
            display: flex;
            border-top: 1px solid #333;
        }

        /* =========================================
           14. LIGHTBOX MODAL
           ========================================= */
        .lightbox-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            z-index: 10000;
            display: none;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s;
        }
        .lightbox-modal.active {
            display: flex;
            opacity: 1;
        }
        .lightbox-content {
            max-width: 90%;
            max-height: 90%;
            border: 2px solid var(--primary-rgb-red);
            box-shadow: 0 0 30px rgba(255, 0, 60, 0.4);
        }
        .lightbox-close {
            position: absolute;
            top: 30px;
            right: 30px;
            color: white;
            font-size: 3rem;
            cursor: pointer;
            transition: color 0.3s;
        }
        .lightbox-close:hover {
            color: var(--primary-rgb-red);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-title { font-size: 3rem; }
            .gallery-grid { grid-template-columns: 1fr; }
            #cursor-dot, #cursor-outline { display: none; } /* Disable custom cursor on touch */
        }

    </style>
</head>
<body>

    <!-- Custom Cursor -->
    <div id="cursor-dot"></div>
    <div id="cursor-outline"></div>

    <!-- Lightbox Modal -->
    <div id="lightbox" class="lightbox-modal">
        <div class="lightbox-close" onclick="closeLightbox()">&times;</div>
        <img id="lightbox-img" class="lightbox-content" src="" alt="Full view">
    </div>

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg fixed-top" id="navbar">
        <div class="container">
            <a class="navbar-brand" href="#"><i class="fas fa-camera-retro me-2"></i>PRIME<span style="color:var(--primary-rgb-red)">.RGB</span></a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <i class="fas fa-bars text-white"></i>
            </button>
            <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
                <ul class="navbar-nav align-items-center">
                    <li class="nav-item"><a class="nav-link" href="#hero">Home</a></li>
                    <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
                    <li class="nav-item"><a class="nav-link" href="#portfolio">Portfolio</a></li>
                    <li class="nav-item"><a class="nav-link" href="#video-section">Reels</a></li>
                    <li class="nav-item"><a class="nav-link" href="#pricing">Pricing</a></li>
                    <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
                    <li class="nav-item ms-lg-3">
                        <a href="#auth-section" class="btn btn-glow" style="font-size: 0.9rem; padding: 8px 20px;">Login</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="hero">
        <canvas id="hero-canvas"></canvas>
        <div class="hero-content reveal-on-scroll">
            <h5 class="hero-subtitle glitch-text">WELCOME TO THE FUTURE OF ART</h5>
            <h1 class="hero-title text-gradient">CAPTURE REALITY<br>IN RGB</h1>
            <p class="lead mb-5" style="color: #ccc; max-width: 600px; margin: 0 auto 40px auto;">
                Professional photography services for Weddings, Events, and Portraits. 
                Experience the world through a neon lens.
            </p>
            <a href="#portfolio" class="btn btn-glow me-3">View Gallery</a>
            <a href="#contact" class="btn btn-glow" style="border-color: var(--primary-rgb-blue);">Book Now</a>
        </div>
    </section>

    <!-- Stats Section -->
    <div class="stats-bar">
        <div class="container">
            <div class="row text-center">
                <div class="col-md-3 col-6 mb-3 mb-md-0 stat-item reveal-on-scroll">
                    <h3 data-target="1500">0</h3>
                    <p>PHOTOS SHOTS</p>
                </div>
                <div class="col-md-3 col-6 mb-3 mb-md-0 stat-item reveal-on-scroll">
                    <h3 data-target="350">0</h3>
                    <p>HAPPY CLIENTS</p>
                </div>
                <div class="col-md-3 col-6 stat-item reveal-on-scroll">
                    <h3 data-target="120">0</h3>
                    <p>EVENTS COVERED</p>
                </div>
                <div class="col-md-3 col-6 stat-item reveal-on-scroll">
                    <h3 data-target="15">0</h3>
                    <p>YEARS EXP.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- About Section -->
    <section id="about" class="section-padding" style="background: #0a0a0a;">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-6 mb-5 mb-lg-0 reveal-on-scroll">
                    <div class="position-relative">
                        <img src="https://images.unsplash.com/photo-1554048612-b6a482bc67e5?q=80&w=1000&auto=format&fit=crop" alt="Photographer" class="img-fluid rounded" style="border: 2px solid var(--primary-rgb-green);">
                        <div style="position: absolute; bottom: -20px; right: -20px; background: var(--primary-rgb-blue); color: black; padding: 20px; font-weight: bold; font-family: var(--font-head);">
                            RGB<br>MASTER
                        </div>
                    </div>
                </div>
                <div class="col-lg-6 ps-lg-5 reveal-on-scroll">
                    <h4 class="text-gradient mb-3">About The Studio</h4>
                    <h2 class="mb-4">WE ARE <span style="color: white;">PRIME</span></h2>
                    <p class="text-muted mb-4">
                        Founded in 2020, Prime Of Photography isn't just a studio; it's a visual experiment. 
                        We combine traditional photography techniques with modern, high-contrast aesthetics 
                        to create images that pop off the screen.
                    </p>
                    <p class="text-muted mb-4">
                        Whether it's the subtle tear at a wedding or the electric energy of a concert, 
                        our lenses capture the raw emotion in vivid detail.
                    </p>
                    
                    <div class="row mb-4">
                        <div class="col-6">
                            <i class="fas fa-check-circle me-2" style="color: var(--primary-rgb-green)"></i> 4K Resolution
                        </div>
                        <div class="col-6">
                            <i class="fas fa-check-circle me-2" style="color: var(--primary-rgb-green)"></i> Fast Delivery
                        </div>
                        <div class="col-6">
                            <i class="fas fa-check-circle me-2" style="color: var(--primary-rgb-green)"></i> Drone Shots
                        </div>
                        <div class="col-6">
                            <i class="fas fa-check-circle me-2" style="color: var(--primary-rgb-green)"></i> RGB Editing
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="section-padding">
        <div class="container">
            <div class="text-center mb-5 reveal-on-scroll">
                <h2 class="text-gradient">Featured Works</h2>
                <p class="text-muted">Explore our captured moments across different categories.</p>
                <div class="divider"></div>
            </div>

            <!-- Filter Controls -->
            <div class="text-center mb-5 reveal-on-scroll">
                <button class="btn filter-btn active" onclick="filterGallery('all')">ALL</button>
                <button class="btn filter-btn" onclick="filterGallery('wedding')">WEDDING</button>
                <button class="btn filter-btn" onclick="filterGallery('birthday')">BIRTHDAY</button>
                <button class="btn filter-btn" onclick="filterGallery('anniversary')">ANNIVERSARY</button>
                <button class="btn filter-btn" onclick="filterGallery('events')">EVENTS</button>
            </div>

            <!-- Gallery Grid -->
            <div class="gallery-grid" id="gallery-container">
                <!-- Images are loaded via JS for cleaner HTML, but structure is here -->
            </div>
        </div>
    </section>

    <!-- Video Section -->
    <section id="video-section" class="section-padding" style="background: #080808;">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-5 mb-4 mb-lg-0 reveal-on-scroll">
                    <h2 class="text-gradient">Behind The Scenes</h2>
                    <h3 class="mb-4 text-white">THE REEL</h3>
                    <p class="text-muted">
                        Watch how we work. We have compiled a showreel of our best shots, 
                        editing processes, and the vibrant atmosphere of our shoots.
                    </p>
                    <ul class="list-unstyled text-white mt-4">
                        <li class="mb-2"><i class="fas fa-film me-2" style="color: var(--primary-rgb-red)"></i> Cinematic 4K Editing</li>
                        <li class="mb-2"><i class="fas fa-music me-2" style="color: var(--primary-rgb-red)"></i> Sound Design Integration</li>
                        <li class="mb-2"><i class="fas fa-shutter me-2" style="color: var(--primary-rgb-red)"></i> Slow Motion Captures</li>
                    </ul>
                </div>
                <div class="col-lg-7 reveal-on-scroll">
                    <div class="video-wrapper">
                        <div class="video-overlay-ui">REC ● <span id="video-timer">00:00:00</span></div>
                        <!-- Using a Pexels video link that is reliable and royalty free -->
                        <video id="mainVideo" class="w-100" style="display: block;" loop muted controls poster="https://images.pexels.com/videos/3195394/free-video-3195394.jpg?auto=compress&cs=tinysrgb&dpr=1&w=500">
                            <source src="https://videos.pexels.com/video-files/3195394/3195394-hd_1920_1080_25fps.mp4" type="video/mp4">
                            Your browser does not support the video tag.
                        </video>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services & Pricing -->
    <section id="pricing" class="section-padding" style="background: #0a0a0a;">
        <div class="container">
            <div class="text-center mb-5 reveal-on-scroll">
                <h2 class="text-gradient">Our Packages</h2>
                <div class="divider"></div>
            </div>
            
            <div class="row">
                <!-- Basic -->
                <div class="col-lg-4 mb-4 reveal-on-scroll">
                    <div class="service-card text-center h-100">
                        <i class="fas fa-camera service-icon"></i>
                        <h3 class="mb-4">ESSENTIAL</h3>
                        <h1 class="display-4 fw-bold text-white mb-4">$500</h1>
                        <ul class="list-unstyled text-start mb-4" style="color: #aaa; line-height: 2;">
                            <li><i class="fas fa-check me-2 text-success"></i> 2 Hours Coverage</li>
                            <li><i class="fas fa-check me-2 text-success"></i> 50 Edited Photos</li>
                            <li><i class="fas fa-check me-2 text-success"></i> Online Gallery</li>
                            <li><i class="fas fa-times me-2 text-danger"></i> Prints</li>
                        </ul>
                        <button class="btn btn-outline-light w-100 rounded-0" style="border-radius: 0;" onclick="openContact('Essential')">Select</button>
                    </div>
                </div>

                <!-- Prime (Popular) -->
                <div class="col-lg-4 mb-4 reveal-on-scroll">
                    <div class="service-card text-center h-100" style="border-color: var(--primary-rgb-red); box-shadow: 0 0 20px rgba(255,0,60,0.2);">
                        <div style="position: absolute; top:0; right:0; background: var(--primary-rgb-red); color: white; padding: 5px 15px; font-weight: bold; font-size: 0.8rem;">POPULAR</div>
                        <i class="fas fa-gem service-icon" style="color: var(--primary-rgb-red)"></i>
                        <h3 class="mb-4">PRIME</h3>
                        <h1 class="display-4 fw-bold text-white mb-4">$1,200</h1>
                        <ul class="list-unstyled text-start mb-4" style="color: #aaa; line-height: 2;">
                            <li><i class="fas fa-check me-2 text-success"></i> 6 Hours Coverage</li>
                            <li><i class="fas fa-check me-2 text-success"></i> 300 Edited Photos</li>
                            <li><i class="fas fa-check me-2 text-success"></i> 1 Highlight Video</li>
                            <li><i class="fas fa-check me-2 text-success"></i> 20 Prints</li>
                        </ul>
                        <button class="btn btn-glow w-100" onclick="openContact('Prime')">Select</button>
                    </div>
                </div>

                <!-- Elite -->
                <div class="col-lg-4 mb-4 reveal-on-scroll">
                    <div class="service-card text-center h-100">
                        <i class="fas fa-crown service-icon"></i>
                        <h3 class="mb-4">ELITE</h3>
                        <h1 class="display-4 fw-bold text-white mb-4">$2,500</h1>
                        <ul class="list-unstyled text-start mb-4" style="color: #aaa; line-height: 2;">
                            <li><i class="fas fa-check me-2 text-success"></i> Full Day Coverage</li>
                            <li><i class="fas fa-check me-2 text-success"></i> Unlimited Photos</li>
                            <li><i class="fas fa-check me-2 text-success"></i> Drone Footage</li>
                            <li><i class="fas fa-check me-2 text-success"></i> Photobook Album</li>
                        </ul>
                        <button class="btn btn-outline-light w-100 rounded-0" style="border-radius: 0;" onclick="openContact('Elite')">Select</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Feedback Section -->
    <section id="feedback" class="section-padding">
        <div class="container">
            <div class="row">
                <div class="col-lg-5 mb-5 mb-lg-0 reveal-on-scroll">
                    <h2 class="text-gradient mb-4">Client Feedback</h2>
                    <p class="text-muted mb-4">Don't just take our word for it. Here is what our clients say about our RGB-themed shoots.</p>
                    
                    <div id="testimonial-carousel" class="carousel slide" data-bs-ride="carousel">
                        <div class="carousel-inner">
                            <div class="carousel-item active">
                                <div class="testimonial-card">
                                    <i class="fas fa-quote-left"></i>
                                    <p class="mt-3 text-white">"The photos were out of this world. The RGB editing added such a unique vibe to our wedding. Absolutely loved it!"</p>
                                    <h5 class="mt-3 text-gradient">Sarah & James</h5>
                                    <small class="text-muted">Wedding Shoot</small>
                                </div>
                            </div>
                            <div class="carousel-item">
                                <div class="testimonial-card">
                                    <i class="fas fa-quote-left"></i>
                                    <p class="mt-3 text-white">"Prime Photography captured the energy of my birthday party perfectly. The shots were crisp and colorful."</p>
                                    <h5 class="mt-3 text-gradient">Mike Ross</h5>
                                    <small class="text-muted">Birthday Event</small>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="col-lg-7 reveal-on-scroll">
                    <div class="p-5" style="background: #111; border: 1px solid #333; border-radius: 10px;">
                        <h4 class="text-white mb-4">Write a Review</h4>
                        <form onsubmit="submitFeedback(event)">
                            <div class="row">
                                <div class="col-md-6 mb-3">
                                    <input type="text" class="form-control rgb-input" placeholder="Your Name" required>
                                </div>
                                <div class="col-md-6 mb-3">
                                    <select class="form-control rgb-input" style="color: #aaa;">
                                        <option>Rating</option>
                                        <option>5 Stars</option>
                                        <option>4 Stars</option>
                                        <option>3 Stars</option>
                                    </select>
                                </div>
                            </div>
                            <div class="mb-3">
                                <textarea class="form-control rgb-input" rows="4" placeholder="Your Experience..." required></textarea>
                            </div>
                            <button type="submit" class="btn btn-glow w-100">Submit Review</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Auth & Contact Combined Section -->
    <section id="contact" class="section-padding" style="background: #050505;">
        <div class="container">
            <div class="text-center mb-5 reveal-on-scroll">
                <h2 class="text-gradient">Get In Touch</h2>
                <p class="text-muted">Ready to book? Have questions? Reach out to the Prime team.</p>
            </div>

            <div class="row">
                <!-- Auth/Login Panel -->
                <div class="col-lg-5 mb-5 mb-lg-0 reveal-on-scroll" id="auth-section">
                    <div class="card p-4" style="background: #111; border: 1px solid var(--primary-rgb-blue); height: 100%;">
                        <ul class="nav nav-pills mb-3 justify-content-center" id="pills-tab" role="tablist">
                            <li class="nav-item">
                                <button class="nav-link active rounded-0" id="pills-login-tab" data-bs-toggle="pill" data-bs-target="#pills-login" type="button">Login</button>
                            </li>
                            <li class="nav-item">
                                <button class="nav-link rounded-0" id="pills-signup-tab" data-bs-toggle="pill" data-bs-target="#pills-signup" type="button">Sign Up</button>
                            </li>
                        </ul>
                        <div class="tab-content" id="pills-tabContent">
                            <div class="tab-pane fade show active" id="pills-login">
                                <form onsubmit="handleAuth(event, 'Logged In Successfully!')">
                                    <input type="email" class="form-control rgb-input" placeholder="Email" required>
                                    <input type="password" class="form-control rgb-input" placeholder="Password" required>
                                    <button type="submit" class="btn btn-glow w-100">Login</button>
                                </form>
                            </div>
                            <div class="tab-pane fade" id="pills-signup">
                                <form onsubmit="handleAuth(event, 'Account Created!')">
                                    <input type="text" class="form-control rgb-input" placeholder="Full Name" required>
                                    <input type="email" class="form-control rgb-input" placeholder="Email" required>
                                    <input type="password" class="form-control rgb-input" placeholder="Password" required>
                                    <button type="submit" class="btn btn-glow w-100">Create Account</button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Contact Form -->
                <div class="col-lg-7 reveal-on-scroll">
                    <form onsubmit="handleContact(event)">
                        <div class="row">
                            <div class="col-md-6 mb-3">
                                <input type="text" class="form-control rgb-input" placeholder="Your Name" required>
                            </div>
                            <div class="col-md-6 mb-3">
                                <input type="email" class="form-control rgb-input" placeholder="Your Email" required>
                            </div>
                        </div>
                        <div class="mb-3">
                            <input type="text" id="contact-subject" class="form-control rgb-input" placeholder="Subject / Package Interest" required>
                        </div>
                        <div class="mb-3">
                            <textarea class="form-control rgb-input" rows="5" placeholder="Tell us about your event..." required></textarea>
                        </div>
                        <button type="submit" class="btn btn-glow w-100" style="border-color: var(--primary-rgb-green); color: var(--primary-rgb-green);">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer style="background: black; padding: 60px 0; border-top: 1px solid #333;">
        <div class="container">
            <div class="row">
                <div class="col-md-4 mb-4">
                    <h3 class="text-white mb-3">PRIME.RGB</h3>
                    <p class="text-muted">Bringing your memories to life with high-contrast, vibrant photography. The future of visual art is here.</p>
                </div>
                <div class="col-md-4 mb-4">
                    <h5 class="text-white mb-3">Quick Links</h5>
                    <ul class="list-unstyled">
                        <li><a href="#hero" class="text-muted text-decoration-none">Home</a></li>
                        <li><a href="#portfolio" class="text-muted text-decoration-none">Gallery</a></li>
                        <li><a href="#pricing" class="text-muted text-decoration-none">Pricing</a></li>
                        <li><a href="#contact" class="text-muted text-decoration-none">Contact</a></li>
                    </ul>
                </div>
                <div class="col-md-4 mb-4">
                    <h5 class="text-white mb-3">Connect</h5>
                    <div class="d-flex gap-3">
                        <a href="#" class="text-white fs-4"><i class="fab fa-facebook"></i></a>
                        <a href="#" class="text-white fs-4"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="text-white fs-4"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="text-white fs-4"><i class="fab fa-linkedin"></i></a>
                    </div>
                    <p class="text-muted mt-3"><i class="fas fa-envelope me-2"></i> hello@primergb.com</p>
                </div>
            </div>
            <div class="text-center mt-5 text-muted">
                &copy; 2023 Prime Of Photography. All Rights Reserved.
            </div>
        </div>
    </footer>

    <!-- AI Assistant -->
    <div class="ai-container">
        <div class="ai-window" id="ai-window">
            <div class="ai-header">
                <span>PRIME AI</span>
                <i class="fas fa-times" style="cursor: pointer;" onclick="toggleAI()"></i>
            </div>
            <div class="ai-messages" id="ai-messages">
                <div class="msg-bubble msg-bot">Hello! I am the Prime AI assistant. Ask me about pricing, wedding packages, or availability!</div>
            </div>
            <div class="ai-input-wrap">
                <input type="text" id="ai-input" class="form-control" style="background: #111; border: none; color: white;" placeholder="Type a message..." onkeypress="handleAIEnter(event)">
                <button class="btn text-white" style="color: var(--primary-rgb-blue);" onclick="sendAIMessage()"><i class="fas fa-paper-plane"></i></button>
            </div>
        </div>
        <div class="ai-toggle" onclick="toggleAI()">
            <i class="fas fa-robot"></i>
        </div>
    </div>

    <!-- JavaScript Logic -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // --- 1. GALLERY DATA & LOGIC ---
        const galleryData = [
            { src: "https://images.unsplash.com/photo-1519741497674-611481863552?w=600", cat: "wedding", title: "Summer Vows" },
            { src: "https://images.unsplash.com/photo-1530103862676-de3c9da59af7?w=600", cat: "birthday", title: "Sweet 16" },
            { src: "https://images.unsplash.com/photo-1511285560982-1356c11d4606?w=600", cat: "anniversary", title: "Golden Years" },
            { src: "https://images.unsplash.com/photo-1540575467063-178a50c2df87?w=600", cat: "events", title: "Tech Conf" },
            { src: "https://images.unsplash.com/photo-1606800052052-a08af7148866?w=600", cat: "wedding", title: "The Groom" },
            { src: "https://images.unsplash.com/photo-1530103862676-de8c9debad1d?w=600", cat: "birthday", title: "Cake Time" },
            { src: "https://images.unsplash.com/photo-1522673607200-1645062ac975?w=600", cat: "wedding", title: "First Dance" },
            { src: "https://images.unsplash.com/photo-1492684223066-81342ee5ff30?w=600", cat: "events", title: "Festival Crowd" },
            { src: "https://images.unsplash.com/photo-1529634597503-139d3726fed5?w=600", cat: "anniversary", title: "Dinner Date" },
        ];

        const galleryContainer = document.getElementById('gallery-container');

        function renderGallery(filter) {
            galleryContainer.innerHTML = '';
            galleryData.forEach(item => {
                if (filter === 'all' || item.cat === filter) {
                    const card = document.createElement('div');
                    card.className = 'gallery-card';
                    card.innerHTML = `
                        <img src="${item.src}" alt="${item.title}" onclick="openLightbox('${item.src}')">
                        <div class="gallery-overlay">
                            <h5 class="text-white text-uppercase">${item.title}</h5>
                            <span class="badge bg-transparent border border-light text-light">${item.cat}</span>
                        </div>
                    `;
                    galleryContainer.appendChild(card);
                }
            });
        }

        function filterGallery(cat) {
            // Update buttons
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            renderGallery(cat);
        }

        // Initialize Gallery
        renderGallery('all');

        // --- 2. LIGHTBOX LOGIC ---
        const lightbox = document.getElementById('lightbox');
        const lightboxImg = document.getElementById('lightbox-img');

        function openLightbox(src) {
            lightboxImg.src = src;
            lightbox.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeLightbox() {
            lightbox.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        lightbox.addEventListener('click', (e) => {
            if (e.target === lightbox) closeLightbox();
        });

        // --- 3. CUSTOM CURSOR LOGIC ---
        const cursorDot = document.getElementById('cursor-dot');
        const cursorOutline = document.getElementById('cursor-outline');

        window.addEventListener('mousemove', (e) => {
            const posX = e.clientX;
            const posY = e.clientY;

            // Dot follows instantly
            cursorDot.style.left = `${posX}px`;
            cursorDot.style.top = `${posY}px`;

            // Outline follows with slight delay (handled by CSS transition usually, but JS sets pos)
            cursorOutline.animate({
                left: `${posX}px`,
                top: `${posY}px`
            }, { duration: 500, fill: "forwards" });
        });

        // Hover effect for links/buttons
        const interactables = document.querySelectorAll('a, button, .gallery-card');
        interactables.forEach(el => {
            el.addEventListener('mouseenter', () => document.body.classList.add('hovering'));
            el.addEventListener('mouseleave', () => document.body.classList.remove('hovering'));
        });

        // --- 4. SCROLL REVEAL & STATS ---
        const observerOptions = { threshold: 0.1 };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    
                    // Trigger number counter if it's a stat item
                    if (entry.target.classList.contains('stat-item')) {
                        const h3 = entry.target.querySelector('h3');
                        const target = +h3.getAttribute('data-target');
                        let count = 0;
                        const inc = target / 100;
                        const updateCount = () => {
                            count += inc;
                            if (count < target) {
                                h3.innerText = Math.ceil(count);
                                requestAnimationFrame(updateCount);
                            } else {
                                h3.innerText = target + "+";
                            }
                        };
                        updateCount();
                        observer.unobserve(entry.target); // Only count once
                    }
                }
            });
        }, observerOptions);

        document.querySelectorAll('.reveal-on-scroll, .stat-item').forEach(el => observer.observe(el));

        // Navbar Scroll Effect
        window.addEventListener('scroll', () => {
            const nav = document.getElementById('navbar');
            if (window.scrollY > 50) nav.classList.add('scrolled');
            else nav.classList.remove('scrolled');
        });

        // --- 5. VIDEO TIMER LOGIC ---
        const video = document.getElementById('mainVideo');
        const timerDisplay = document.getElementById('video-timer');
        
        video.addEventListener('play', () => {
            const updateTime = () => {
                if(!video.paused && !video.ended){
                    let mins = Math.floor(video.currentTime / 60);
                    let secs = Math.floor(video.currentTime % 60);
                    if(mins < 10) mins = "0" + mins;
                    if(secs < 10) secs = "0" + secs;
                    timerDisplay.innerText = `00:${mins}:${secs}`;
                    requestAnimationFrame(updateTime);
                }
            };
            updateTime();
        });

        // --- 6. AI ASSISTANT ---
        const aiWindow = document.getElementById('ai-window');
        const aiInput = document.getElementById('ai-input');
        const aiMessages = document.getElementById('ai-messages');

        function toggleAI() {
            aiWindow.style.display = aiWindow.style.display === 'flex' ? 'none' : 'flex';
        }

        function handleAIEnter(e) {
            if (e.key === 'Enter') sendAIMessage();
        }

        function sendAIMessage() {
            const txt = aiInput.value.trim();
            if (!txt) return;

            // User Message
            addMsg(txt, 'user');
            aiInput.value = '';

            // Bot Response Simulation
            setTimeout(() => {
                let response = "I'm sorry, I didn't quite catch that.";
                const lower = txt.toLowerCase();
                
                if (lower.includes('price') || lower.includes('cost') || lower.includes('package')) {
                    response = "Our packages start at $500 for the Essential plan. The Prime package ($1200) is our most popular for weddings!";
                } else if (lower.includes('wedding')) {
                    response = "We love weddings! We cover everything from preparation to the reception. Check out our gallery for examples.";
                } else if (lower.includes('book') || lower.includes('contact')) {
                    response = "You can book a session by scrolling to the Contact section and filling out the form.";
                } else if (lower.includes('hello') || lower.includes('hi')) {
                    response = "Hello! Welcome to Prime Photography. How can I help you today?";
                }

                addMsg(response, 'bot');
            }, 1000);
        }

        function addMsg(txt, type) {
            const div = document.createElement('div');
            div.className = `msg-bubble msg-${type}`;
            div.innerText = txt;
            aiMessages.appendChild(div);
            aiMessages.scrollTop = aiMessages.scrollHeight;
        }

        // --- 7. FORM HANDLING ---
        function handleAuth(e, msg) {
            e.preventDefault();
            alert(msg); // Simple alert for auth, could be toast
            e.target.reset();
        }

        function handleContact(e) {
            e.preventDefault();
            alert("Message Sent! Our team will contact you shortly.");
            e.target.reset();
        }

        function openContact(packageName) {
            document.getElementById('contact-subject').value = `Interested in ${packageName} Package`;
            document.getElementById('contact').scrollIntoView({ behavior: 'smooth' });
        }

        function submitFeedback(e) {
            e.preventDefault();
            alert("Thank you for your review!");
            e.target.reset();
        }

        // --- 8. CANVAS PARTICLE ANIMATION (The "Wow" Factor) ---
        const canvas = document.getElementById('hero-canvas');
        const ctx = canvas.getContext('2d');
        
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        let particlesArray;

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 1;
                this.speedX = Math.random() * 1 - 0.5;
                this.speedY = Math.random() * 1 - 0.5;
                this.color = Math.random() > 0.5 ? '#ff003c' : '#00f0ff'; // Red or Blue
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.x > canvas.width || this.x < 0) this.speedX = -this.speedX;
                if (this.y > canvas.height || this.y < 0) this.speedY = -this.speedY;
            }
            draw() {
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particlesArray = [];
            const numberOfParticles = (canvas.width * canvas.height) / 15000;
            for (let i = 0; i < numberOfParticles; i++) {
                particlesArray.push(new Particle());
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let i = 0; i < particlesArray.length; i++) {
                particlesArray[i].update();
                particlesArray[i].draw();
            }
            requestAnimationFrame(animateParticles);
        }

        // Handle Resize
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            initParticles();
        });

        initParticles();
        animateParticles();

    </script>
</body>
</html>

