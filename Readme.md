<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bima Adam Nugraha | Full Stack Developer</title>
    
    <!-- Fonts: Outfit for headings, JetBrains Mono for code -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Outfit:wght@300;400;600;800&display=swap" rel="stylesheet">
    
    <!-- Icons: FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --bg-color: #0d1117;
            --card-bg: #161b22;
            --text-main: #e6edf3;
            --text-muted: #8b949e;
            --primary: #8B5CF6; /* Purple */
            --primary-glow: rgba(139, 92, 246, 0.4);
            --secondary: #FF6B35; /* Orange */
            --border: #30363d;
            --font-main: 'Outfit', sans-serif;
            --font-code: 'JetBrains Mono', monospace;
            --glass: rgba(22, 27, 34, 0.7);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(139, 92, 246, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(255, 107, 53, 0.08) 0%, transparent 20%);
        }

        a { text-decoration: none; color: inherit; transition: 0.3s; }
        ul { list-style: none; }

        /* --- Utility Classes --- */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .gradient-text {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 800;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }

        section {
            padding: 60px 0;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        /* --- Header & Hero --- */
        header {
            text-align: center;
            padding-bottom: 40px;
        }

        .hero-wave {
            width: 100%;
            max-width: 800px;
            margin: 0 auto;
            display: block;
        }

        .typing-container {
            margin: 20px auto 40px;
            max-width: 600px;
            overflow: hidden;
            border-radius: 12px;
            box-shadow: 0 10px 30px -10px rgba(0,0,0,0.5);
        }

        /* --- About Me --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .profile-gif {
            width: 100%;
            border-radius: 20px;
            border: 2px solid var(--border);
            box-shadow: 0 0 20px rgba(139, 92, 246, 0.2);
            transition: transform 0.3s ease;
        }

        .profile-gif:hover {
            transform: scale(1.02);
        }

        .code-block {
            background: #1e1e1e;
            border-radius: 12px;
            padding: 20px;
            border: 1px solid var(--border);
            font-family: var(--font-code);
            font-size: 0.9rem;
            overflow-x: auto;
            position: relative;
        }
        
        /* Syntax highlighting simulation */
        .cb-key { color: #569cd6; }
        .cb-string { color: #ce9178; }
        .cb-num { color: #b5cea8; }
        .cb-bool { color: #569cd6; }
        .cb-comment { color: #6a9955; }

        /* --- Tech Stack --- */
        .stack-category {
            margin-bottom: 30px;
        }

        .stack-category h3 {
            margin-bottom: 15px;
            font-size: 1.1rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .stack-category h3 i { color: var(--primary); }

        .icons-wrapper {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            background: rgba(255,255,255,0.03);
            padding: 20px;
            border-radius: 16px;
            border: 1px solid var(--border);
        }

        .icons-wrapper img {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            filter: grayscale(100%);
            opacity: 0.7;
        }

        .icons-wrapper img:hover {
            filter: grayscale(0%);
            opacity: 1;
            transform: translateY(-5px);
        }

        /* --- Stats Grid --- */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border);
            transition: 0.3s;
        }
        
        .stat-card:hover {
            border-color: var(--primary);
            box-shadow: 0 0 15px var(--primary-glow);
        }

        .stat-card img {
            width: 100%;
            display: block;
        }

        /* --- Projects Table --- */
        .table-container {
            overflow-x: auto;
            border-radius: 12px;
            border: 1px solid var(--border);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background: var(--card-bg);
            min-width: 600px;
        }

        th, td {
            padding: 16px;
            text-align: left;
            border-bottom: 1px solid var(--border);
        }

        th {
            background: rgba(139, 92, 246, 0.1);
            color: var(--primary);
            font-weight: 600;
        }

        tr:last-child td { border-bottom: none; }
        tr:hover { background: rgba(255,255,255,0.02); }

        .status-badge {
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            background: rgba(255,255,255,0.1);
            color: var(--text-main);
        }

        .status-active { color: #3fb950; background: rgba(63, 185, 80, 0.15); }
        .status-progress { color: #d29922; background: rgba(210, 153, 34, 0.15); }

        /* --- CSS Only Mindmap / Skill Tree --- */
        /* This creates a visual tree structure without JS */
        .skill-tree {
            display: flex;
            justify-content: center;
            padding: 40px 0;
        }

        .tree-root {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .node {
            background: var(--card-bg);
            border: 1px solid var(--primary);
            padding: 10px 20px;
            border-radius: 30px;
            color: var(--primary);
            font-weight: bold;
            box-shadow: 0 0 15px var(--primary-glow);
            z-index: 2;
            margin-bottom: 40px;
            position: relative;
        }

        .branches {
            display: flex;
            justify-content: space-between;
            gap: 40px;
            position: relative;
        }

        /* Horizontal Connector */
        .branches::before {
            content: '';
            position: absolute;
            top: -20px;
            left: 50px;
            right: 50px;
            height: 2px;
            background: var(--border);
            z-index: 1;
        }

        /* Vertical Line from Root */
        .node::after {
            content: '';
            position: absolute;
            bottom: -40px;
            left: 50%;
            width: 2px;
            height: 40px;
            background: var(--border);
            transform: translateX(-50%);
        }

        .branch {
            display: flex;
            flex-direction: column;
            align-items: center;
            flex: 1;
            position: relative;
        }

        /* Branch Vertical Connector */
        .branch::before {
            content: '';
            position: absolute;
            top: -20px;
            left: 50%;
            width: 2px;
            height: 20px;
            background: var(--border);
        }

        .branch-title {
            background: rgba(255, 255, 255, 0.05);
            padding: 8px 16px;
            border-radius: 8px;
            margin-bottom: 15px;
            color: var(--text-main);
            font-weight: 600;
            border: 1px solid var(--border);
        }

        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            justify-content: center;
        }

        .tag {
            font-size: 0.8rem;
            padding: 4px 10px;
            background: rgba(0,0,0,0.3);
            border-radius: 4px;
            color: var(--text-muted);
            border: 1px solid transparent;
            transition: 0.2s;
        }

        .tag:hover {
            color: var(--secondary);
            border-color: var(--secondary);
        }

        /* --- Contact --- */
        .social-grid {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 30px;
        }

        .social-btn {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 24px;
            border-radius: 50px;
            background: rgba(255,255,255,0.05);
            border: 1px solid var(--border);
            font-weight: 600;
            transition: all 0.3s;
        }

        .social-btn:hover {
            background: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px var(--primary-glow);
            border-color: var(--primary);
        }

        .quote {
            text-align: center;
            font-style: italic;
            color: var(--text-muted);
            margin-bottom: 20px;
            font-size: 1.1rem;
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 40px;
            position: relative;
        }

        .footer-wave {
            width: 100%;
            max-width: 600px;
            margin: 0 auto;
            display: block;
        }

        .views-badge {
            margin-top: 20px;
            display: inline-block;
        }

        /* --- Responsive Design --- */
        @media (max-width: 768px) {
            .about-grid {
                grid-template-columns: 1fr;
            }
            
            .branches {
                flex-direction: column;
                align-items: center;
                gap: 30px;
            }

            .branches::before {
                display: none;
            }

            .node::after {
                display: none;
            }

            .branch::before {
                display: none;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="container">
            <!-- Capsule Render Header -->
            <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=150&section=header&text=Welcome%20to%20my%20digital%20space&fontSize=30&fontColor=fff&animation=fadeIn&fontAlignY=40" alt="Header Wave" class="hero-wave">
            
            <h1 class="gradient-text" style="font-size: 3rem; margin-top: 20px;">Hi there! I'm Bima Adam Nugraha</h1>

            <!-- Typing Animation -->
            <div class="typing-container">
                <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=1000&color=8B5CF6&center=true&vCenter=true&width=600&lines=Full+Stack+Developer;CO-Founder+at+Ignitron;Creative+Mechanic;Problem+Solver;Code+%26+Create" alt="Typing Animation">
            </div>
        </div>
    </header>

    <main class="container">

        <!-- About Section -->
        <section id="about">
            <h2 class="section-title">About Me</h2>
            <div class="about-grid">
                <div>
                    <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" alt="Coding GIF" class="profile-gif">
                </div>
                <div class="code-block">
<pre><code><span class="cb-key">const</span> <span class="cb-key">bima</span> = {
  <span class="cb-string">name</span>: <span class="cb-string">"Bima Adam Nugraha"</span>,
  <span class="cb-string">age</span>: <span class="cb-num">23</span>,
  <span class="cb-string">location</span>: <span class="cb-string">"Indonesia"</span>,
  <span class="cb-string">role</span>: <span class="cb-string">"CO-Founder @ Ignitron"</span>,
  <span class="cb-string">passion</span>: [<span class="cb-string">"Coding"</span>, <span class="cb-string">"Mechanics"</span>, <span class="cb-string">"Innovation"</span>],
  <span class="cb-string">workingOn</span>: <span class="cb-string">"Building scalable web apps"</span>,
  <span class="cb-string">learning</span>: <span class="cb-string">"Advanced system architecture"</span>,
  <span class="cb-string">funFact</span>: <span class="cb-string">"I can fix your car & build your web!"</span>
};</code></pre>
                </div>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section id="stack">
            <h2 class="section-title">Tech Stack</h2>
            
            <div class="stack-category">
                <h3><i class="fa-solid fa-code"></i> Languages</h3>
                <div class="icons-wrapper">
                    <img src="https://skillicons.dev/icons?i=cs,cpp,ts,js,dart,php,java&theme=dark" alt="Languages">
                </div>
            </div>

            <div class="stack-category">
                <h3><i class="fa-solid fa-laptop-code"></i> Frontend</h3>
                <div class="icons-wrapper">
                    <img src="https://skillicons.dev/icons?i=react,nextjs,flutter,tailwind,css,scss&theme=dark" alt="Frontend">
                </div>
            </div>

            <div class="stack-category">
                <h3><i class="fa-solid fa-server"></i> Backend</h3>
                <div class="icons-wrapper">
                    <img src="https://skillicons.dev/icons?i=nodejs,nestjs,laravel,express,fastapi,dotnet&theme=dark" alt="Backend">
                </div>
            </div>

            <div class="stack-category">
                <h3><i class="fa-solid fa-database"></i> Database & Tools</h3>
                <div class="icons-wrapper">
                    <img src="https://skillicons.dev/icons?i=prisma,mongodb,postgresql,redis,docker&theme=dark" alt="DB & Tools">
                </div>
            </div>

            <div class="stack-category">
                <h3><i class="fa-solid fa-terminal"></i> DevOps & Others</h3>
                <div class="icons-wrapper">
                    <img src="https://skillicons.dev/icons?i=git,github,vscode,figma,postman,notion&theme=dark" alt="DevOps">
                </div>
            </div>
        </section>

        <!-- Analytics Section -->
        <section id="stats">
            <h2 class="section-title">GitHub Analytics</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=bimaadam&show_icons=true&count_private=true&hide_border=true&title_color=8B5CF6&icon_color=8B5CF6&text_color=c9d1d9&bg_color=161b22" alt="GitHub Stats">
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=bimaadam&layout=compact&hide_border=true&title_color=8B5CF6&text_color=c9d1d9&bg_color=161b22&hide=php,html,scss,css" alt="Top Languages">
                </div>
            </div>
            
            <div style="display: flex; justify-content: center; margin-bottom: 30px;">
                <img src="https://streak-stats.demolab.com?user=bimaadam&theme=dark&hide_border=true&background=161B22&stroke=8B5CF6&ring=8B5CF6&fire=FF6B35&currStreakNum=C9D1D9&sideNums=C9D1D9&currStreakLabel=8B5CF6&sideLabels=C9D1D9&dates=C9D1D9" alt="GitHub Streak" style="width: 100%; max-width: 600px; border-radius: 12px; border: 1px solid var(--border);">
            </div>

            <div style="display: flex; justify-content: center; margin-bottom: 30px;">
                <img src="https://github-profile-trophy.vercel.app/?username=bimaadam&theme=darkhub&no-frame=true&no-bg=true&margin-w=4&row=2&column=6" alt="GitHub Achievements" style="width: 100%; max-width: 800px;">
            </div>

            <div style="display: flex; justify-content: center;">
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=bimaadam&bg_color=161b22&color=8b5cf6&line=8b5cf6&point=ff6b35&area=true&hide_border=true&custom_title=My%20Code%20Journey" alt="Activity Graph" style="width: 100%; border-radius: 12px; border: 1px solid var(--border);">
            </div>
        </section>

        <!-- Current Focus -->
        <section id="focus">
            <h2 class="section-title">What I'm Working On</h2>
            <div class="table-container">
                <table>
                    <thead>
                        <tr>
                            <th width="30%">Focus Area</th>
                            <th width="50%">Description</th>
                            <th width="20%">Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong style="color:var(--primary)">Ignitron</strong></td>
                            <td>Building innovative solutions</td>
                            <td><span class="status-badge status-progress">In Progress</span></td>
                        </tr>
                        <tr>
                            <td><strong>Full-Stack Projects</strong></td>
                            <td>Modern web applications</td>
                            <td><span class="status-badge status-active">Active</span></td>
                        </tr>
                        <tr>
                            <td><strong>Open Source</strong></td>
                            <td>Contributing to community</td>
                            <td><span class="status-badge">Contributing</span></td>
                        </tr>
                        <tr>
                            <td><strong>Learning</strong></td>
                            <td>System architecture & AI</td>
                            <td><span class="status-badge">Exploring</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- Skills Tree (Visual CSS Representation of Mindmap) -->
        <section id="skills">
            <h2 class="section-title">Skills & Interests</h2>
            
            <div class="skill-tree">
                <div class="tree-root">
                    <div class="node">Bima</div>
                    <div class="branches">
                        <!-- Branch 1: Programming -->
                        <div class="branch">
                            <div class="branch-title"><i class="fa-solid fa-code"></i> Programming</div>
                            <div class="tags">
                                <span class="tag">React</span>
                                <span class="tag">Next.js</span>
                                <span class="tag">Flutter</span>
                                <span class="tag">Node.js</span>
                                <span class="tag">NestJS</span>
                                <span class="tag">Laravel</span>
                            </div>
                        </div>
                        
                        <!-- Branch 2: Creative -->
                        <div class="branch">
                            <div class="branch-title"><i class="fa-solid fa-lightbulb"></i> Creative</div>
                            <div class="tags">
                                <span class="tag">Problem Solving</span>
                                <span class="tag">System Design</span>
                                <span class="tag">Innovation</span>
                            </div>
                        </div>

                        <!-- Branch 3: Hobbies -->
                        <div class="branch">
                            <div class="branch-title"><i class="fa-solid fa-wrench"></i> Hobbies</div>
                            <div class="tags">
                                <span class="tag">Mechanics</span>
                                <span class="tag">Technology</span>
                                <span class="tag">Photography</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section id="connect">
            <h2 class="section-title">Connect With Me</h2>
            <div class="social-grid">
                <a href="https://bimaadam.fun/" class="social-btn">
                    <i class="fa-solid fa-globe"></i> Website
                </a>
                <a href="https://github.com/bimaadam" class="social-btn">
                    <i class="fa-brands fa-github"></i> GitHub
                </a>
                <a href="mailto:contact@bimaadamrin.my.id" class="social-btn">
                    <i class="fa-solid fa-envelope"></i> Email
                </a>
                <a href="https://linkedin.com/in/bimaadam" class="social-btn">
                    <i class="fa-brands fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://instagram.com/bimaadam" class="social-btn">
                    <i class="fa-brands fa-instagram"></i> Instagram
                </a>
            </div>
        </section>

    </main>

    <footer>
        <div class="quote">
            "Innovation happens at the intersection of curiosity and capability"
        </div>
        
        <img src="https://komarev.com/ghpvc/?username=bimaadam&label=Profile%20Views&color=8B5CF6&style=for-the-badge" alt="Profile Views" class="views-badge">
        
        <div style="margin-top: 30px;">
            <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=100&section=footer&animation=fadeIn" alt="Footer Wave" class="footer-wave">
        </div>
        
        <p style="color: var(--text-muted); font-size: 0.9rem;">
            Thanks for visiting! Let's build something amazing together.
        </p>
    </footer>

</body>
</html>
