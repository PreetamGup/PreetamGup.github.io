<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Preetam Kumar - MERN Stack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary: #00ff88;
            --secondary: #0a192f;
            --text: #8892b0;
            --highlight: #64ffda;
            --bg: #0a192f;
            --nav: rgba(10, 25, 47, 0.85);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Consolas', monospace;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
        }

        /* Navbar */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem;
            background: var(--nav);
            backdrop-filter: blur(10px);
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            color: var(--primary);
            font-weight: bold;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text);
            text-decoration: none;
            position: relative;
            padding: 0.5rem;
        }

        .nav-links a::before {
            content: '>';
            color: var(--primary);
            opacity: 0;
            margin-right: 5px;
            transition: all 0.3s;
        }

        .nav-links a:hover::before {
            opacity: 1;
            transform: translateX(5px);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 4rem 2rem;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(0,255,136,0.1) 0%, rgba(10,25,47,0.9) 100%);
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
        }

        .typing-effect {
            border-right: 2px solid var(--primary);
            white-space: nowrap;
            overflow: hidden;
            font-size: 1.5rem;
            animation: typing 3.5s steps(30, end), blink 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink {
            from, to { border-color: transparent }
            50% { border-color: var(--primary) }
        }

        .code-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.1;
            font-family: 'Consolas', monospace;
            color: var(--primary);
            overflow: hidden;
            pointer-events: none;
        }

        .code-line {
            font-size: 1rem;
            margin: 5px 0;
            animation: codescroll 20s linear infinite;
        }

        @keyframes codescroll {
            from { transform: translateY(0); }
            to { transform: translateY(-50%); }
        }

        /* Project Cards */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            padding: 2rem;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 2rem;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(100, 255, 218, 0.1);
            transition: all 0.3s;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(0, 255, 136, 0.1));
            opacity: 0;
            transition: all 0.3s;
        }

        .project-card:hover::before {
            opacity: 1;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
        }

        .project-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .project-links a {
            color: var(--primary);
            text-decoration: none;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .project-links a:hover {
            transform: translateY(-3px);
        }

        /* Skills Section */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            padding: 2rem;
        }

        .skill-tag {
            background: rgba(0, 255, 136, 0.1);
            color: var(--primary);
            padding: 0.8rem 1.5rem;
            border-radius: 5px;
            border: 1px solid var(--primary);
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .skill-tag::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: var(--primary);
            transition: all 0.5s;
            border-radius: 50%;
            transform: translate(-50%, -50%);
            opacity: 0.2;
        }

        .skill-tag:hover::before {
            width: 200%;
            height: 200%;
        }

        /* Terminal Section */
        .terminal {
            background: #1d2433;
            border-radius: 10px;
            padding: 2rem;
            margin: 2rem;
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.1);
        }

        .terminal-header {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .terminal-button {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #ff5f56;
        }

        .terminal-button:nth-child(2) {
            background: #ffbd2e;
        }

        .terminal-button:nth-child(3) {
            background: #27c93f;
        }

        .terminal-content {
            font-family: 'Consolas', monospace;
            color: var(--primary);
        }

        .command-line {
            display: flex;
            gap: 0.5rem;
            margin: 0.5rem 0;
        }

        .prompt {
            color: var(--primary);
        }

        .command {
            color: white;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav {
                padding: 1rem;
            }

            .nav-links {
                display: none;
            }

            .hero {
                padding: 2rem 1rem;
            }

            .typing-effect {
                font-size: 1.2rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .terminal {
                margin: 1rem;
                padding: 1rem;
            }
        }

        /* Animations */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }

        .float-animation {
            animation: float 6s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">{'PG'}</div>
        <div class="nav-links">
            <a href="#about">About</a>
            <a href="#projects">Projects</a>
            <a href="#skills">Skills</a>
            <a href="#experience">Experience</a>
        </div>
    </nav>

    <div class="hero">
        <div class="code-background">
            <!-- Simulated code background -->
            <div class="code-line">const developer = {</div>
            <div class="code-line">  name: 'Preetam Kumar',</div>
            <div class="code-line">  role: 'MERN Stack Developer',</div>
            <div class="code-line">  skills: ['React', 'Node.js', 'MongoDB'],</div>
            <div class="code-line">  passion: 'Building awesome web apps'</div>
            <div class="code-line">};</div>
        </div>
        
        <div class="hero-content">
            <h1 class="typing-effect">Hi 👋, I'm Preetam Kumar Gupta</h1>
            <p style="font-size: 2.5rem; color: var(--primary); margin: 1rem 0;">MERN Stack Developer</p>
            <p style="max-width: 600px; margin: 1rem 0;">
                Transforming ideas into reality through code. Specialized in building 
                exceptional digital experiences with modern web technologies.
            </p>
            <div style="margin-top: 2rem;">
                <a href="mailto:guptapritam285@gmail.com" style="background: transparent; border: 1px solid var(--primary); color: var(--primary); padding: 1rem 2rem; text-decoration: none; border-radius: 5px; transition: all 0.3s;">
                    Get In Touch
                </a>
            </div>
        </div>
    </div>

    <section id="about">
        <h2 class="section-title" style="color: var(--primary); margin: 2rem; text-align: center; text-shadow: 0px 0px 10px var(--highlight);">About Me</h2>
        <div class="terminal">
            <div class="terminal-header">
                <div class="terminal-button"></div>
                <div class="terminal-button"></div>
                <div class="terminal-button"></div>
            </div>
            <div class="terminal-content">
                <div class="command-line">
                    <span class="prompt">$</span>
                    <span class="command">cat about.txt</span>
                </div>
                <p style="margin: 1rem 0;">
                    Highly motivated professional with a strong passion for web development and a background in Mechanical Engineering.
                    Currently focused on MERN stack development and building scalable web applications.
                </p>
                <div class="command-line">
                    <span class="prompt">$</span>
                    <span class="command">ls skills/</span>
                </div>
                <p style="margin: 1rem 0; color: #ffbd2e;">
                    React.js  Node.js  MongoDB  Express.js  JavaScript  TypeScript
                </p>
            </div>
        </div>
    </section>

    <section id="projects">
        <h2 class="section-title" style="color: var(--primary); margin: 2rem; text-align: center; text-shadow: 0px 0px 10px var(--highlight);">Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <img src="/api/placeholder/800/400" alt="Web Tools Project" style="width: 100%; border-radius: 5px; margin-bottom: 1rem;">
                <h3 style="color: var(--primary);">Web Tools</h3>
                <p>Next.js-powered web tool with SEO optimization and analytics integration.</p>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i></a>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>

            <div class="project-card">
                <img src="/api/placeholder/800/400" alt="Cybersecurity Course Platform" style="width: 100%; border-radius: 5px; margin-bottom: 1rem;">
                <h3 style="color: var(--primary);">Cybersecurity Course Platform</h3>
                <p>Full-stack course platform with secure authentication and admin capabilities.</p>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i></a>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>

            <div class="project-card">
                <img src="/api/placeholder/800/400" alt="Doctor Appointment App" style="width: 100%; border-radius: 5px; margin-bottom: 1rem;">
                <h3 style="color: var(--primary);">Doctor Appointment App</h3>
                <p>MERN stack appointment booking system with full CRUD functionality.</p>
                <div class="project-links">
                    <a href="#"><i class="fab fa-github"></i></a>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title" style="color: var(--primary); margin: 2rem; text-align: center; text-shadow: 0px 0px 10px var(--highlight);">Tech Stack</h2>
        <div class="skills-container">
            <span class="skill-tag">TypeScript</span>
            <span class="skill-tag">React.js</span>
            <span class="skill-tag">Node.js</span>
            <span class="skill-tag">Express.js</span>
            <span class="skill-tag">MongoDB</span>
            <span class="skill-tag">Redux</span>
            <span class="skill-tag">Next.js</span>
            <span class="skill-tag">Tailwind CSS</span>
            <span class="skill-tag">Git</span>
            <span class="skill-tag">REST APIs</span>
            <span class="skill-tag">JavaScript</span>
            <span class="skill-tag">HTML5</span>
            <span class="skill-tag">CSS3</span>
            <span class="skill-tag">MySQL</span>
        </div>
    </section>

    <section id="experience">
    <h2 class="section-title" style="color: var(--primary); margin: 2rem; text-align: center; text-shadow: 0px 0px 10px var(--highlight);">
        Experience
    </h2>
    <div class="terminal">
        <div class="terminal-header">
            <div class="terminal-button"></div>
            <div class="terminal-button"></div>
            <div class="terminal-button"></div>
        </div>
        <div class="terminal-content">
            <div class="command-line">
                <span class="prompt">$</span>
                <span class="command">cat experience.txt</span>
            </div>
            <p style="padding: 1rem; border-left: 3px solid var(--primary); margin-bottom: 1rem;">
                <strong style="color: var(--highlight);">Ultratech Cement (Manikgarh Cement Works)</strong> | Maintenance Engineering (March 2021 - March 2022)
                <br><span style="color: var(--text);">- Planned and undertook scheduled maintenance.</span>
                <br><span style="color: var(--text);">- Maintained spreadsheets for every work and material issued.</span>
                <br><span style="color: var(--text);">- Created permits as per Ultratech Standards.</span>
                <br><span style="color: var(--text);">- Worked with SAP MM and SAP PP.</span>
            </p>
        </div>
    </div>
</section>

<section id="education">
    <h2 class="section-title" style="color: var(--primary); margin: 2rem; text-align: center; text-shadow: 0px 0px 10px var(--highlight);">
        Education
    </h2>
    <div class="terminal">
        <div class="terminal-header">
            <div class="terminal-button"></div>
            <div class="terminal-button"></div>
            <div class="terminal-button"></div>
        </div>
        <div class="terminal-content">
            <div class="command-line">
                <span class="prompt">$</span>
                <span class="command">cat education.txt</span>
            </div>
            <div style="padding: 1rem; border-left: 3px solid var(--highlight);">
                <p><strong style="color: var(--highlight);">Bachelor of Engineering (Mechanical Engineering)</strong></p>
                <p style="margin-left: 1rem;">Rajiv Gandhi College of Engineering, Research & Technology, Chandrapur (2019) - <span style="color: var(--primary);">67.1%</span></p>

                <p><strong style="color: var(--highlight);">Intermediate (Class XII)</strong></p>
                <p style="margin-left: 1rem;">Manikgarh Cement English School, Gadchandur (2015) - <span style="color: var(--primary);">75.0%</span></p>

                <p><strong style="color: var(--highlight);">Matriculation (Class X)</strong></p>
                <p style="margin-left: 1rem;">Manikgarh Cement English School (2013) - <span style="color: var(--primary);">80.0%</span></p>
            </div>
        </div>
    </div>
</section>

<section id="achievements">
    <h2 class="section-title" style="color: var(--primary); margin: 2rem; text-align: center; text-shadow: 0px 0px 10px var(--highlight);">
        Achievements
    </h2>
    <div class="terminal">
        <div class="terminal-header">
            <div class="terminal-button"></div>
            <div class="terminal-button"></div>
            <div class="terminal-button"></div>
        </div>
        <div class="terminal-content">
            <div class="command-line">
                <span class="prompt">$</span>
                <span class="command">cat achievements.txt</span>
            </div>
            <ul style="margin: 1rem; padding: 1rem; border-left: 3px solid var(--primary); list-style: none;">
                <li style="margin-bottom: 0.5rem; color: var(--text);">🏆 <span style="color: var(--highlight);">Played Basketball and Table Tennis</span> at District and University levels.</li>
                <li style="margin-bottom: 0.5rem; color: var(--text);">🏆 <span style="color: var(--highlight);">Won the Best Camper Award</span> organized by the school.</li>
                <li style="margin-bottom: 0.5rem; color: var(--text);">🏆 <span style="color: var(--highlight);">Served as House Captain</span> and Project Leader in college.</li>
                <li style="margin-bottom: 0.5rem; color: var(--text);">🏆 <span style="color: var(--highlight);">Hosted 30+ online game tournaments</span> and streamed on YouTube.</li>
            </ul>
        </div>
    </div>
</section>

        
        
        
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.1 });

            sections.forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
