<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NeoForge - Premium Digital Platforms for Acquisition</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --accent-blue: #4f46e5;
            --accent-purple: #7c3aed;
            --text-primary: #1f2937;
            --text-secondary: #6b7280;
            --bg-primary: #ffffff;
            --bg-secondary: #f8fafc;
            --border-color: #e2e8f0;
            --shadow: 0 20px 25px -5px rgba(0, 0,0, 0.1), 0 10px 10px -5px rgba(0, 0,0, 0.04);
        }

        [data-theme="dark"] {
            --text-primary: #f8fafc;
            --text-secondary: #cbd5e1;
            --bg-primary: #0f172a;
            --bg-secondary: #1e293b;
            --border-color: #334155;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--text-primary);
            background: var(--bg-primary);
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Smooth Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        [data-theme="dark"] header {
            background: rgba(15, 23, 42, 0.95);
        }

        nav {
            max-width: 1400px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-primary);
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent-blue);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--primary-gradient);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .theme-toggle {
            background: none;
            border: 2px solid var(--border-color);
            border-radius: 50px;
            padding: 0.5rem 1rem;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .theme-toggle:hover {
            border-color: var(--accent-blue);
            color: var(--accent-blue);
        }

        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            z-index: 2;
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 5rem);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, var(--text-primary), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 3rem;
            max-width: 600px;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            background: var(--primary-gradient);
            color: white;
            padding: 1.2rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            box-shadow: var(--shadow);
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 30px 40px -10px rgba(102, 126, 234, 0.4);
        }

        .hero-bg {
            position: absolute;
            top: 0;
            right: 0;
            width: 60%;
            height: 100%;
            background: var(--primary-gradient);
            border-radius: 0 0 0 100px;
            opacity: 0.1;
            z-index: 1;
        }

        /* Sections */
        section {
            padding: 8rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 800;
            text-align: center;
            margin-bottom: 4rem;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text p {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
        }

        .about-features {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .feature {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }

        .feature-icon {
            width: 50px;
            height: 50px;
            background: var(--primary-gradient);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            flex-shrink: 0;
        }

        /* Products Section */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: var(--bg-secondary);
            border-radius: 24px;
            padding: 2.5rem;
            border: 1px solid var(--border-color);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
        }

        [data-theme="dark"] .product-card {
            background: rgba(30, 41, 59, 0.5);
            border-color: var(--border-color);
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow);
            border-color: var(--accent-blue);
        }

        .product-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--primary-gradient);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .product-card:hover::before {
            transform: scaleX(1);
        }

        .product-icon {
            width: 80px;
            height: 80px;
            background: var(--primary-gradient);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
            margin-bottom: 1.5rem;
        }

        /* Stats Section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .stat {
            padding: 2rem;
        }

        .stat-number {
            font-size: 4rem;
            font-weight: 800;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        /* Partnership Section */
        .partnership-content {
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem 1.5rem;
            border: 2px solid var(--border-color);
            border-radius: 12px;
            font-size: 1rem;
            transition: all 0.3s ease;
            background: var(--bg-secondary);
            color: var(--text-primary);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent-blue);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.1);
        }

        .submit-btn {
            width: 100%;
            background: var(--primary-gradient);
            color: white;
            padding: 1.2rem;
            border: none;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        /* Footer */
        footer {
            background: var(--bg-secondary);
            text-align: center;
            padding: 3rem 2rem;
            border-top: 1px solid var(--border-color);
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu {
                display: flex;
                gap: 0.5rem;
            }

            .hero {
                text-align: center;
                flex-direction: column;
            }

            .hero h1 {
                margin-bottom: 1.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            section {
                padding: 4rem 1rem;
            }
        }

        /* Scroll Animations */
        @media (prefers-reduced-motion: no-preference) {
            .fade-in {
                scroll-snap-align: start;
            }
        }
    </style>
</head>
<body data-theme="light">
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">NeoForge</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#growth">Growth</a></li>
                <li><a href="#stats">Stats</a></li>
                <li><a href="#partnership">Partnership</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="theme-toggle" onclick="toggleTheme()">
                <i class="fas fa-moon"></i>
            </div>
            <div class="mobile-menu">
                <i class="fas fa-bars fa-2x"></i>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero fade-in">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <h1>The Future of Digital Innovation Starts Here.</h1>
            <p>Premium AI-powered platforms ready for acquisition. Scalable, profitable, and engineered for the next decade of tech dominance.</p>
            <a href="#products" class="cta-button">
                <i class="fas fa-rocket"></i>
                Explore the Platform
            </a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="fade-in">
        <h2 class="section-title">Vision for Digital Excellence</h2>
        <div class="about-content">
            <div class="about-text">
                <p>NeoForge represents the pinnacle of digital innovation - platforms built with cutting-edge AI, bulletproof scalability, and proven monetization strategies. We're not just building tools; we're creating acquisition-ready empires.</p>
                <p>Every platform is engineered with enterprise-grade infrastructure, global CDN distribution, and AI-driven personalization that drives exponential user growth and revenue.</p>
            </div>
            <div class="about-features">
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-infinity"></i>
                    </div>
                    <div>
                        <h3>Infinite Scalability</h3>
                        <p>Handle millions of users with zero downtime</p>
                    </div>
                </div>
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <div>
                        <h3>AI-First Architecture</h3>
                        <p>Next-gen intelligence built into every feature</p>
                    </div>
                </div>
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div>
                        <h3>Proven Revenue Model</h3>
                        <p>Multiple income streams optimized for acquisition</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="fade-in">
        <h2 class="section-title">Premium Digital Products</h2>
        <div class="products-grid">
            <div class="product-card">
                <div class="product-icon">
                    <i class="fas fa-robot"></i>
                </div>
                <h3>AI Content Engine</h3>
                <p>Enterprise-grade AI writing platform generating 10M+ words daily. Perfect for content agencies and marketing teams.</p>
                <div style="margin-top: 1.5rem;">
                    <span style="color: var(--accent-blue); font-weight: 600;">$250K MRR Potential</span>
                </div>
            </div>
            <div class="product-card">
                <div class="product-icon">
                    <i class="fas fa-bolt"></i>
                </div>
                <h3>Productivity Suite</h3>
                <p>All-in-one workspace with AI automation. 500K+ active users waiting for enterprise acquisition.</p>
                <div style="margin-top: 1.5rem;">
                    <span style="color: var(--accent-blue); font-weight: 600;">Global Scale Ready</span>
                </div>
            </div>
            <div class="product-card">
                <div class="product-icon">
                    <i class="fas fa-code"></i>
                </div>
                <h3>Developer Platform</h3>
                <p>Low-code AI builder for SaaS products. Perfect for tech companies expanding their ecosystem.</p>
                <div style="margin-top: 1.5rem;">
                    <span style="color: var(--accent-blue); font-weight: 600;">API-First Architecture</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Growth Potential Section -->
    <section id="growth" class="fade-in" style="background: var(--bg-secondary);">
        <h2 class="section-title">Unmatched Growth Potential</h2>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; max-width: 1000px; margin: 0 auto;">
            <div style="text-align: center; padding: 2rem;">
                <div style="font-size: 4rem; font-weight: 800; background: var(--secondary-gradient); -webkit-background-clip: text;
                
