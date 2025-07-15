<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Andry Ny Fitiavana - Full-Stack Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Exo+2:wght@300;400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            font-family: 'Exo 2', sans-serif;
            overflow-x: hidden;
            position: relative;
        }
        
        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: rgba(0, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.5; }
        }
        
        /* Grid background */
        .grid-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                linear-gradient(rgba(0, 255, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: -2;
            animation: gridMove 20s linear infinite;
        }
        
        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }
        
        /* Header section */
        .header {
            text-align: center;
            margin-bottom: 60px;
            padding: 40px 0;
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1), rgba(138, 43, 226, 0.1));
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 255, 0.2);
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
            background: linear-gradient(45deg, transparent, rgba(0, 255, 255, 0.05), transparent);
            animation: shimmer 3s ease-in-out infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        .name {
            font-family: 'Orbitron', monospace;
            font-size: 3.5rem;
            font-weight: 900;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #ffff00, #00ffff);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite;
            margin-bottom: 10px;
        }
        
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .title {
            font-size: 1.8rem;
            color: #00ffff;
            font-weight: 300;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
        }
        
        .description {
            font-size: 1.1rem;
            line-height: 1.6;
            color: #b0b0b0;
            max-width: 800px;
            margin: 0 auto 30px;
        }
        
        .location {
            font-size: 1rem;
            color: #ff6b6b;
            margin-bottom: 10px;
        }
        
        .email {
            font-size: 1rem;
            color: #4ecdc4;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .email:hover {
            color: #00ffff;
            text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
        }
        
        /* Skills sections */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        
        .skill-category {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.05), rgba(138, 43, 226, 0.05));
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.2);
        }
        
        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 255, 0.1), transparent);
            transition: left 0.5s ease;
        }
        
        .skill-category:hover::before {
            left: 100%;
        }
        
        .skill-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.5rem;
            font-weight: 700;
            color: #00ffff;
            margin-bottom: 20px;
            text-align: center;
            text-shadow: 0 0 10px rgba(0, 255, 255, 0.3);
        }
        
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
        }
        
        .skill-item {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1), rgba(138, 43, 226, 0.1));
            border: 1px solid rgba(0, 255, 255, 0.3);
            border-radius: 10px;
            padding: 12px 20px;
            font-size: 0.9rem;
            font-weight: 500;
            color: #ffffff;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: linear-gradient(90deg, #00ffff, #ff00ff);
            transition: width 0.3s ease;
            z-index: -1;
        }
        
        .skill-item:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0, 255, 255, 0.4);
            color: #000000;
        }
        
        .skill-item:hover::before {
            width: 100%;
        }
        
        /* Social links */
        .social-section {
            text-align: center;
            margin-top: 50px;
        }
        
        .social-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.5rem;
            color: #00ffff;
            margin-bottom: 20px;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
        }
        
        .social-link {
            display: inline-block;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.2), rgba(138, 43, 226, 0.2));
            border-radius: 50%;
            border: 2px solid rgba(0, 255, 255, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #00ffff;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            border-radius: 50%;
            transform: scale(0);
            transition: transform 0.3s ease;
            z-index: -1;
        }
        
        .social-link:hover {
            transform: scale(1.2) rotate(360deg);
            color: #000000;
        }
        
        .social-link:hover::before {
            transform: scale(1);
        }
        
        /* Responsive design */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .title {
                font-size: 1.4rem;
            }
            
            .description {
                font-size: 1rem;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
            
            .social-links {
                gap: 20px;
            }
        }
        
        /* Loading animation */
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
        
        .fade-in {
            animation: fadeInUp 0.8s ease-out;
        }
        
        .fade-in-delay-1 {
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }
        
        .fade-in-delay-2 {
            animation: fadeInUp 0.8s ease-out 0.4s both;
        }
        
        .fade-in-delay-3 {
            animation: fadeInUp 0.8s ease-out 0.6s both;
        }
    </style>
</head>
<body>
    <div class="grid-bg"></div>
    <div class="particles"></div>
    
    <div class="container">
        <div class="header fade-in">
            <div class="header-content">
                <h1 class="name">Andry Ny Fitiavana</h1>
                <h2 class="title">Full-Stack Developer & Game Developer</h2>
                <p class="description">
                    A passionate full-stack developer with expertise in React ecosystem and Unreal Engine game development. 
                    I specialize in crafting visually stunning web applications and immersive gaming experiences. 
                    With three years of dedicated learning and adaptation, I deliver innovative solutions that push 
                    the boundaries of both web and game development.
                </p>
                <div class="location">🌍 Based in Antananarivo, Madagascar</div>
                <a href="mailto:andryfitia8@gmail.com" class="email">✉️ andryfitia8@gmail.com</a>
            </div>
        </div>
        
        <div class="skills-grid">
            <div class="skill-category fade-in-delay-1">
                <h3 class="skill-title">React Ecosystem</h3>
                <div class="skills-container">
                    <div class="skill-item">React</div>
                    <div class="skill-item">Next.js</div>
                    <div class="skill-item">JavaScript</div>
                    <div class="skill-item">TypeScript</div>
                    <div class="skill-item">HTML5</div>
                    <div class="skill-item">CSS3</div>
                    <div class="skill-item">Sass</div>
                    <div class="skill-item">Material-UI</div>
                    <div class="skill-item">Tailwind CSS</div>
                    <div class="skill-item">Redux</div>
                    <div class="skill-item">React Hooks</div>
                    <div class="skill-item">React Router</div>
                </div>
            </div>
            
            <div class="skill-category fade-in-delay-2">
                <h3 class="skill-title">Unreal Engine</h3>
                <div class="skills-container">
                    <div class="skill-item">Game Development</div>
                    <div class="skill-item">Level Design</div>
                    <div class="skill-item">Animation</div>
                    <div class="skill-item">Blueprint Visual Scripting</div>
                    <div class="skill-item">C++ Programming</div>
                    <div class="skill-item">3D Modeling</div>
                    <div class="skill-item">Lighting & Rendering</div>
                    <div class="skill-item">Physics Simulation</div>
                    <div class="skill-item">AI Behavior Trees</div>
                    <div class="skill-item">VR/AR Development</div>
                    <div class="skill-item">Niagara VFX</div>
                    <div class="skill-item">Sequencer</div>
                </div>
            </div>
            
            <div class="skill-category fade-in-delay-1">
                <h3 class="skill-title">Backend & Database</h3>
                <div class="skills-container">
                    <div class="skill-item">Node.js</div>
                    <div class="skill-item">Express.js</div>
                    <div class="skill-item">MongoDB</div>
                    <div class="skill-item">PostgreSQL</div>
                    <div class="skill-item">MySQL</div>
                    <div class="skill-item">REST APIs</div>
                    <div class="skill-item">GraphQL</div>
                    <div class="skill-item">JWT Authentication</div>
                </div>
            </div>
            
            <div class="skill-category fade-in-delay-2">
                <h3 class="skill-title">Tools & Technologies</h3>
                <div class="skills-container">
                    <div class="skill-item">Git & GitHub</div>
                    <div class="skill-item">Docker</div>
                    <div class="skill-item">VS Code</div>
                    <div class="skill-item">Linux</div>
                    <div class="skill-item">Google Cloud</div>
                    <div class="skill-item">Figma</div>
                    <div class="skill-item">Photoshop</div>
                    <div class="skill-item">Illustrator</div>
                    <div class="skill-item">Blender</div>
                    <div class="skill-item">Bash/Shell</div>
                </div>
            </div>
        </div>
        
        <div class="social-section fade-in-delay-3">
            <h3 class="social-title">Connect With Me</h3>
            <div class="social-links">
                <a href="https://www.github.com/Andryfitia" target="_blank" rel="noreferrer" class="social-link">
                    <span>⚡</span>
                </a>
                <a href="https://www.facebook.com/profile.php?id=100039060133896" target="_blank" rel="noreferrer" class="social-link">
                    <span>📱</span>
                </a>
                <a href="mailto:andryfitia8@gmail.com" class="social-link">
                    <span>✉️</span>
                </a>
            </div>
        </div>
    </div>
    
    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.querySelector('.particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }
        
        // Initialize particles
        createParticles();
        
        // Add hover effects to skill items
        document.querySelectorAll('.skill-item').forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.05) rotate(2deg)';
            });
            
            item.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotate(0deg)';
            });
        });
        
        // Smooth scrolling for better UX
        document.addEventListener('DOMContentLoaded', function() {
            // Add staggered animation to elements
            const elements = document.querySelectorAll('.fade-in, .fade-in-delay-1, .fade-in-delay-2, .fade-in-delay-3');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationPlayState = 'running';
                    }
                });
            });
            
            elements.forEach(element => {
                observer.observe(element);
            });
        });
        
        // Add dynamic glow effect to social links
        document.querySelectorAll('.social-link').forEach(link => {
            link.addEventListener('mouseenter', function() {
                this.style.boxShadow = '0 0 30px rgba(0, 255, 255, 0.8)';
            });
            
            link.addEventListener('mouseleave', function() {
                this.style.boxShadow = 'none';
            });
        });
    </script>
</body>
</html>
