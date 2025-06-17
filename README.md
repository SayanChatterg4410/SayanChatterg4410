<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayan Chatterjee - Advanced GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #64ffda;
            border-radius: 50%;
            animation: float 20s infinite linear;
            opacity: 0.7;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0px);
                opacity: 0;
            }
            10% {
                opacity: 0.7;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(-100px) translateX(100px);
                opacity: 0;
            }
        }

        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header section with holographic effect */
        .header {
            text-align: center;
            padding: 60px 0;
            background: linear-gradient(45deg, transparent, rgba(100, 255, 218, 0.1), transparent);
            border-radius: 20px;
            margin-bottom: 40px;
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
            background: conic-gradient(from 0deg, transparent, #64ffda, transparent, #ff6b6b, transparent);
            animation: rotate 20s linear infinite;
            opacity: 0.1;
        }

        @keyframes rotate {
            100% {
                transform: rotate(360deg);
            }
        }

        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 30px;
            background: linear-gradient(45deg, #64ffda, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            font-weight: bold;
            position: relative;
            z-index: 3;
            box-shadow: 0 0 50px rgba(100, 255, 218, 0.5);
            animation: pulse 2s ease-in-out infinite alternate;
        }

        @keyframes pulse {
            0% {
                box-shadow: 0 0 50px rgba(100, 255, 218, 0.5);
            }
            100% {
                box-shadow: 0 0 80px rgba(100, 255, 218, 0.8);
            }
        }

        .name {
            font-size: 3.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #64ffda, #ff6b6b, #4ecdc4, #64ffda);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite;
            margin-bottom: 20px;
            position: relative;
            z-index: 3;
        }

        @keyframes gradientShift {
            0%, 100% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
        }

        .typing-animation {
            font-size: 1.5rem;
            color: #64ffda;
            position: relative;
            z-index: 3;
        }

        /* 3D Cards */
        .section {
            margin: 40px 0;
            perspective: 1000px;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            margin: 20px 0;
            transition: all 0.3s ease;
            transform-style: preserve-3d;
        }

        .card:hover {
            transform: rotateX(5deg) rotateY(5deg) translateZ(10px);
            box-shadow: 0 20px 40px rgba(100, 255, 218, 0.2);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            color: #64ffda;
            margin-bottom: 30px;
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
            height: 3px;
            background: linear-gradient(90deg, #64ffda, #ff6b6b);
            border-radius: 2px;
        }

        /* Tech Stack with hover effects */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .tech-item {
            background: rgba(100, 255, 218, 0.1);
            border: 2px solid transparent;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(100, 255, 218, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .tech-item:hover::before {
            left: 100%;
        }

        .tech-item:hover {
            border-color: #64ffda;
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.3);
        }

        .tech-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
        }

        /* Projects with interactive elements */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin: 30px 0;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(100, 255, 218, 0.2);
            border-radius: 20px;
            padding: 25px;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #64ffda, #ff6b6b, #4ecdc4);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(100, 255, 218, 0.2);
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #64ffda;
            margin-bottom: 15px;
        }

        .project-desc {
            color: #b8b8b8;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tech-tag {
            background: rgba(100, 255, 218, 0.2);
            color: #64ffda;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Interactive stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            background: rgba(100, 255, 218, 0.05);
            border: 1px solid rgba(100, 255, 218, 0.2);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #64ffda;
            display: block;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #b8b8b8;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Contact section with glassmorphism */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .contact-item {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            text-decoration: none;
            color: inherit;
        }

        .contact-item:hover {
            background: rgba(100, 255, 218, 0.1);
            border-color: #64ffda;
            transform: translateY(-5px);
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 15px;
            color: #64ffda;
        }

        /* Terminal-style quote */
        .terminal {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 10px;
            padding: 20px;
            margin: 30px 0;
            font-family: 'Courier New', monospace;
            position: relative;
        }

        .terminal::before {
            content: '● ● ●';
            position: absolute;
            top: 10px;
            left: 15px;
            color: #ff6b6b;
            font-size: 0.8rem;
        }

        .terminal-content {
            margin-top: 25px;
            color: #64ffda;
        }

        .cursor {
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% {
                opacity: 1;
            }
            51%, 100% {
                opacity: 0;
            }
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .typing-animation {
                font-size: 1.2rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
        }

        /* Scroll indicator */
        .scroll-indicator {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: rgba(255, 255, 255, 0.1);
            z-index: 1000;
        }

        .scroll-progress {
            height: 100%;
            background: linear-gradient(90deg, #64ffda, #ff6b6b);
            width: 0%;
            transition: width 0.1s ease;
        }
    </style>
</head>
<body>
    <!-- Scroll Progress Indicator -->
    <div class="scroll-indicator">
        <div class="scroll-progress" id="scrollProgress"></div>
    </div>

    <!-- Animated Background Particles -->
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="avatar">SC</div>
            <h1 class="name">Sayan Chatterjee</h1>
            <div class="typing-animation" id="typingText"></div>
        </header>

        <!-- About Section -->
        <section class="section">
            <div class="card">
                <h2 class="section-title">💻 About Me</h2>
                <p style="font-size: 1.2rem; line-height: 1.8; text-align: center; color: #b8b8b8;">
                    I'm a <strong style="color: #64ffda;">Full-Stack Developer</strong> passionate about building clean, performant, and responsive web applications. 
                    Skilled in modern technologies and frameworks, I focus on creating intuitive interfaces and smooth user experiences. 
                    Currently working on cutting-edge web projects involving <strong style="color: #ff6b6b;">authentication systems</strong>, 
                    <strong style="color: #4ecdc4;">advanced animations</strong>, and <strong style="color: #64ffda;">complex billing logic</strong>.
                </p>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section class="section">
            <div class="card">
                <h2 class="section-title">🛠️ Tech Stack</h2>
                <div class="tech-grid">
                    <div class="tech-item" data-tech="React">
                        <span class="tech-icon">⚛️</span>
                        <div>React</div>
                    </div>
                    <div class="tech-item" data-tech="Next.js">
                        <span class="tech-icon">🔺</span>
                        <div>Next.js</div>
                    </div>
                    <div class="tech-item" data-tech="JavaScript">
                        <span class="tech-icon">🟨</span>
                        <div>JavaScript</div>
                    </div>
                    <div class="tech-item" data-tech="HTML5">
                        <span class="tech-icon">🌐</span>
                        <div>HTML5</div>
                    </div>
                    <div class="tech-item" data-tech="CSS3">
                        <span class="tech-icon">🎨</span>
                        <div>CSS3</div>
                    </div>
                    <div class="tech-item" data-tech="Tailwind">
                        <span class="tech-icon">💨</span>
                        <div>Tailwind</div>
                    </div>
                    <div class="tech-item" data-tech="Figma">
                        <span class="tech-icon">🎯</span>
                        <div>Figma</div>
                    </div>
                    <div class="tech-item" data-tech="Git">
                        <span class="tech-icon">🌳</span>
                        <div>Git</div>
                    </div>
                    <div class="tech-item" data-tech="VS Code">
                        <span class="tech-icon">💙</span>
                        <div>VS Code</div>
                    </div>
                    <div class="tech-item" data-tech=".NET">
                        <span class="tech-icon">🔷</span>
                        <div>.NET</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="section">
            <div class="card">
                <h2 class="section-title">🚀 Featured Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-title">🏨 Luxury Hotel Platform</div>
                        <div class="project-desc">
                            A sophisticated hotel booking platform featuring JWT authentication, token-based security, 
                            and seamless user experience with modern animations and responsive design.
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Next.js</span>
                            <span class="tech-tag">JWT</span>
                            <span class="tech-tag">Tailwind CSS</span>
                        </div>
                    </div>
                    <div class="project-card">
                        <div class="project-title">🍕 Smart Food Ordering</div>
                        <div class="project-desc">
                            Lightning-fast food delivery application built with React and Vite, featuring real-time order tracking, 
                            payment integration, and an intuitive user interface.
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Vite</span>
                            <span class="tech-tag">API Integration</span>
                            <span class="tech-tag">Real-time</span>
                        </div>
                    </div>
                    <div class="project-card">
                        <div class="project-title">☕ Coffee Shop POS</div>
                        <div class="project-desc">
                            Advanced point-of-sale system for coffee shops with inventory management, 
                            sales analytics, and automated billing calculations built with VB.NET.
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">VB.NET</span>
                            <span class="tech-tag">SQL Server</span>
                            <span class="tech-tag">WinForms</span>
                            <span class="tech-tag">Analytics</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="section">
            <div class="card">
                <h2 class="section-title">📊 GitHub Stats</h2>
                <div class="stats-grid">
                    <div class="stat-card">
                        <span class="stat-number" data-target="150">0</span>
                        <div class="stat-label">Repositories</div>
                    </div>
                    <div class="stat-card">
                        <span class="stat-number" data-target="2500">0</span>
                        <div class="stat-label">Commits</div>
                    </div>
                    <div class="stat-card">
                        <span class="stat-number" data-target="50">0</span>
                        <div class="stat-label">Projects</div>
                    </div>
                    <div class="stat-card">
                        <span class="stat-number" data-target="98">0</span>
                        <div class="stat-label">Code Quality</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Terminal Quote -->
        <section class="section">
            <div class="terminal">
                <div class="terminal-content">
                    <div>💭 Developer Philosophy:</div>
                    <div style="margin-top: 10px; color: #ffffff;">
                        "Code is like humor. When you have to explain it, it's bad." 
                        <span style="color: #64ffda;">— Cory House</span>
                        <span class="cursor">|</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="section">
            <div class="card">
                <h2 class="section-title">📫 Let's Connect</h2>
                <div class="contact-grid">
                    <a href="mailto:sayanchatterjee@example.com" class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div>Email</div>
                        <div style="font-size: 0.9rem; color: #64ffda;">Get in touch</div>
                    </a>
                    <a href="https://yourwebsite.com" class="contact-item">
                        <div class="contact-icon">🌐</div>
                        <div>Portfolio</div>
                        <div style="font-size: 0.9rem; color: #64ffda;">View my work</div>
                    </a>
                    <a href="https://linkedin.com/in/yourprofile" class="contact-item">
                        <div class="contact-icon">💼</div>
                        <div>LinkedIn</div>
                        <div style="font-size: 0.9rem; color: #64ffda;">Connect professionally</div>
                    </a>
                    <a href="https://github.com/yourusername" class="contact-item">
                        <div class="contact-icon">🐱</div>
                        <div>GitHub</div>
                        <div style="font-size: 0.9rem; color: #64ffda;">Explore repositories</div>
                    </a>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Typing animation
        const texts = [
            "Full-Stack Developer",
            "Frontend Specialist", 
            "UI/UX Enthusiast",
            "Clean Code Advocate",
            "Always Learning",
            "Problem Solver"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typingText');
        
        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }
            
            let typeSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && charIndex === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                typeSpeed = 500;
            }
            
            setTimeout(type, typeSpeed);
        }
        
        type();

        // Particle system
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 20 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }
        
        createParticles();

        // Scroll progress indicator
        window.addEventListener('scroll', () => {
            const scrollTop = window.pageYOffset;
            const docHeight = document.body.scrollHeight - window.innerHeight;
            const scrollPercent = (scrollTop / docHeight) * 100;
            document.getElementById('scrollProgress').style.width = scrollPercent + '%';
        });

        // Animated counters
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            
            counters.forEach(counter => {
                const target = parseInt(counter.getAttribute('data-target'));
                const increment = target / 100;
                let current = 0;
                
                const updateCounter = () => {
                    if (current < target) {
                        current += increment;
                        counter.textContent = Math.ceil(current);
                        requestAnimationFrame(updateCounter);
                    } else {
                        counter.textContent = target;
                    }
                };
                
                updateCounter();
            });
        }

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                    
                    if (entry.target.querySelector('.stat-number')) {
                        animateCounters();
                    }
                }
            });
        }, observerOptions);

        // Apply animation to all cards
        document.querySelectorAll('.card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(50px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });

        // Tech item hover effects
        document.querySelectorAll('.tech-item').forEach(item => {
            item.addEventListener('mouseenter', () => {
                item.style.transform = 'translateY(-10px) scale(1.05) rotateY(5deg)';
            });
            
            item.addEventListener('mouseleave', () => {
                item.style.transform = 'translateY(0) scale(1) rotateY(0deg)';
            });
        });

        // Smooth scrolling for internal links
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

        // Dynamic background color based on scroll
        window.addEventListener('scroll', () => {
            const scrollPercent = window.pageYOffset / (document.body.scrollHeight - window.innerHeight);
            const hue = Math.floor(scrollPercent * 60) + 180; // Blue to purple range
            document.body.style.background = `linear-gradient(135deg, hsl(${hue}, 70%, 5%) 0%, hsl(${hue + 20}, 60%, 10%) 50%, hsl(${hue + 40}, 50%, 15%) 100%)`;
        });

        // Add loading animation
        window.addEventListener('load', () => {
            document.body.style.opacity = '0';
            document.body.style.transition = 'opacity 0.5s ease';
            setTimeout(() => {
                document.body.style.opacity = '1';
            }, 100);
        });
    </script>
</body>
</html>
