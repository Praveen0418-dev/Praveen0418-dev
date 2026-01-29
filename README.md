<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Praveen Kumar - Python Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated Background */
        .background {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 50%, #0a0e27 100%);
        }

        .stars {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        /* Floating particles */
        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: rgba(100, 200, 255, 0.5);
            border-radius: 50%;
            animation: float 15s infinite;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) translateX(0);
                opacity: 0;
            }
            10% {
                opacity: 0.5;
            }
            90% {
                opacity: 0.5;
            }
            100% {
                transform: translateY(-100vh) translateX(100px);
                opacity: 0;
            }
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 20px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            backdrop-filter: blur(10px);
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            animation: fadeInDown 1s ease;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 3em;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from {
                filter: drop-shadow(0 0 5px rgba(102, 126, 234, 0.5));
            }
            to {
                filter: drop-shadow(0 0 20px rgba(118, 75, 162, 0.8));
            }
        }

        .header .subtitle {
            font-size: 1.3em;
            color: #64b5f6;
            margin-bottom: 15px;
        }

        .header .location {
            color: #aaa;
            font-size: 1.1em;
        }

        /* Section Styling */
        .section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 40px;
            margin-bottom: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
            border-color: rgba(102, 126, 234, 0.5);
        }

        .section h2 {
            font-size: 2em;
            margin-bottom: 25px;
            color: #667eea;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section h2::before {
            content: '';
            width: 40px;
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            font-size: 1.1em;
            line-height: 1.8;
            color: #e0e0e0;
        }

        .about-content p {
            margin-bottom: 15px;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .skill-category {
            background: rgba(102, 126, 234, 0.1);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateX(10px);
        }

        .skill-category h3 {
            color: #64b5f6;
            margin-bottom: 10px;
            font-size: 1.2em;
        }

        .skill-category ul {
            list-style: none;
        }

        .skill-category li {
            padding: 5px 0;
            color: #ccc;
        }

        .skill-category li::before {
            content: '▹ ';
            color: #667eea;
            font-weight: bold;
        }

        /* Tech Stack Badges */
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 20px;
        }

        .tech-badge {
            padding: 8px 16px;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.2), rgba(118, 75, 162, 0.2));
            border: 1px solid rgba(102, 126, 234, 0.5);
            border-radius: 20px;
            font-size: 0.9em;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-badge:hover {
            transform: scale(1.1);
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.4), rgba(118, 75, 162, 0.4));
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-link {
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(102, 126, 234, 0.2);
            border-radius: 50%;
            color: #64b5f6;
            text-decoration: none;
            font-size: 1.5em;
            transition: all 0.3s ease;
            border: 2px solid rgba(102, 126, 234, 0.3);
        }

        .social-link:hover {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            transform: translateY(-5px) rotate(360deg);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.5);
        }

        /* GitHub Stats */
        .github-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid rgba(102, 126, 234, 0.3);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
        }

        .stat-card img {
            width: 100%;
            height: auto;
            display: block;
        }

        /* Expertise List */
        .expertise-list {
            list-style: none;
            margin-top: 20px;
        }

        .expertise-list li {
            padding: 15px;
            margin-bottom: 10px;
            background: rgba(102, 126, 234, 0.1);
            border-left: 4px solid #667eea;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .expertise-list li:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateX(10px);
        }

        .expertise-list li::before {
            content: '🔹';
            margin-right: 10px;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px;
            color: #888;
            margin-top: 50px;
        }

        .footer a {
            color: #64b5f6;
            text-decoration: none;
        }

        .footer a:hover {
            text-decoration: underline;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2em;
            }
            
            .section {
                padding: 25px;
            }

            .github-stats {
                grid-template-columns: 1fr;
            }
        }

        /* Scroll Animation */
        .fade-in {
            opacity: 0;
            animation: fadeIn 1s ease forwards;
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="background"></div>
    <div class="stars" id="stars"></div>

    <div class="container">
        <!-- Header -->
        <header class="header">
            <h1>💫 Praveen Kumar</h1>
            <p class="subtitle">Python Developer | Healthcare IT Specialist</p>
            <p class="location">📍 Pune, India</p>
            
            <div class="social-links">
                <a href="https://github.com/Praveen0418-dev" target="_blank" class="social-link" title="GitHub">
                    <span>🐙</span>
                </a>
                <a href="https://linkedin.com/in/praveen-kumar-34bb28206" target="_blank" class="social-link" title="LinkedIn">
                    <span>💼</span>
                </a>
                <a href="https://instagram.com/praveen_18__04" target="_blank" class="social-link" title="Instagram">
                    <span>📸</span>
                </a>
            </div>
        </header>

        <!-- About Section -->
        <section class="section fade-in">
            <h2>👋 About Me</h2>
            <div class="about-content">
                <p>
                    I'm a <strong>Python Developer</strong> with <strong>2+ years of experience</strong> building digital healthcare solutions.
                </p>
                <p>
                    I specialize in <strong>laboratory machine integrations</strong>, <strong>LIS/LIMS systems</strong>, and <strong>real-time data synchronization</strong> using Python. I've worked extensively with Django, Tkinter, Flask, REST APIs, and MySQL/SQLite, focusing on clean, scalable, and reliable backend systems.
                </p>
                <p>
                    🚀 Always learning and improving healthcare through technology.
                </p>
            </div>
        </section>

        <!-- What I Work On -->
        <section class="section fade-in">
            <h2>💡 What I Work On</h2>
            <ul class="expertise-list">
                <li>Integrating lab instruments (ASTM / HL7, Serial & TCP/IP)</li>
                <li>Building centralized dashboards for multi-lab data monitoring</li>
                <li>Secure API-based data sync between local systems and central servers</li>
                <li>Background schedulers, logging, and error-handling systems</li>
            </ul>
        </section>

        <!-- Tech Stack -->
        <section class="section fade-in">
            <h2>🛠️ Tech Stack</h2>
            <div class="tech-stack">
                <span class="tech-badge">Python</span>
                <span class="tech-badge">Django</span>
                <span class="tech-badge">Flask</span>
                <span class="tech-badge">Tkinter</span>
                <span class="tech-badge">REST APIs</span>
                <span class="tech-badge">MySQL</span>
                <span class="tech-badge">SQLite</span>
                <span class="tech-badge">PostgreSQL</span>
                <span class="tech-badge">MS SQL Server</span>
                <span class="tech-badge">Docker</span>
                <span class="tech-badge">Git & GitHub</span>
                <span class="tech-badge">Bitbucket</span>
                <span class="tech-badge">AWS</span>
                <span class="tech-badge">GitHub Actions</span>
                <span class="tech-badge">Pandas</span>
                <span class="tech-badge">NumPy</span>
                <span class="tech-badge">Node.js</span>
                <span class="tech-badge">JavaScript</span>
                <span class="tech-badge">HTML5</span>
                <span class="tech-badge">Bash Script</span>
                <span class="tech-badge">Postman</span>
            </div>
        </section>

        <!-- Domain Focus -->
        <section class="section fade-in">
            <h2>🎯 Domain Focus</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>Healthcare IT</h3>
                    <ul>
                        <li>Digital healthcare solutions</li>
                        <li>Patient data management</li>
                        <li>Healthcare compliance</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>LIS/LIMS Automation</h3>
                    <ul>
                        <li>Laboratory workflows</li>
                        <li>Sample tracking</li>
                        <li>Quality control</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>Laboratory Data Systems</h3>
                    <ul>
                        <li>Machine integrations</li>
                        <li>Data standardization</li>
                        <li>Real-time monitoring</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- GitHub Stats -->
        <section class="section fade-in">
            <h2>📊 GitHub Statistics</h2>
            <div class="github-stats">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=Praveen0418-dev&theme=dark&hide_border=false&include_all_commits=false&count_private=false" alt="GitHub Stats">
                </div>
                <div class="stat-card">
                    <img src="https://nirzak-streak-stats.vercel.app/?user=Praveen0418-dev&theme=dark&hide_border=false" alt="GitHub Streak">
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Praveen0418-dev&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact" alt="Top Languages">
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>
                <img src="https://visitcount.itsvg.in/api?id=Praveen0418-dev&icon=0&color=0" alt="Visit Count">
            </p>
            <p>Made with 💜 by Praveen Kumar</p>
            <p><a href="https://github.com/Praveen0418-dev" target="_blank">View on GitHub</a></p>
        </footer>
    </div>

    <script>
        // Create animated stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 200;

            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                star.style.animationDuration = (Math.random() * 3 + 2) + 's';
                starsContainer.appendChild(star);
            }
        }

        // Create floating particles
        function createParticles() {
            const background = document.querySelector('.background');
            const numberOfParticles = 30;

            for (let i = 0; i < numberOfParticles; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = '100%';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 15) + 's';
                background.appendChild(particle);
            }
        }

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationPlayState = 'running';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Initialize
        createStars();
        createParticles();

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
