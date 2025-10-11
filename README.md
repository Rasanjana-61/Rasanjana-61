<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rasanjana - Frontend Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #6c63ff;
            --secondary: #4a44b5;
            --dark: #2a2a3c;
            --light: #f8f9fa;
            --accent: #ff6584;
            --text: #333;
            --text-light: #777;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--text);
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            border-radius: 15px;
            margin-bottom: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid white;
            margin: 0 auto 20px;
            background-color: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: var(--primary);
            background: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .tagline {
            font-size: 1.3rem;
            margin-bottom: 20px;
            opacity: 0.9;
        }

        .location {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 1.1rem;
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 20px;
            border-radius: 30px;
            margin-top: 10px;
        }

        section {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }

        section:hover {
            transform: translateY(-5px);
        }

        h2 {
            color: var(--primary);
            margin-bottom: 25px;
            font-size: 1.8rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        h2 i {
            background: var(--primary);
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 20px;
        }

        .skill-card {
            background: var(--light);
            border-radius: 10px;
            padding: 20px 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid #eee;
        }

        .skill-card:hover {
            background: var(--primary);
            color: white;
            transform: scale(1.05);
        }

        .skill-card i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .skill-card:hover i {
            color: white;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .stat-card {
            background: var(--light);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            border-left: 4px solid var(--primary);
        }

        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .stat-label {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .trophy-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 15px;
        }

        .trophy {
            text-align: center;
            padding: 15px 10px;
            background: var(--light);
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .trophy:hover {
            background: var(--primary);
            color: white;
        }

        .trophy i {
            font-size: 1.8rem;
            margin-bottom: 8px;
            color: gold;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--primary);
            color: white;
            font-size: 1.3rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: var(--secondary);
            transform: translateY(-5px);
        }

        footer {
            text-align: center;
            padding: 20px;
            color: var(--text-light);
            font-size: 0.9rem;
            margin-top: 40px;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .tagline {
                font-size: 1.1rem;
            }
            
            .skills-container {
                grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            }
            
            .stats-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="profile-img">
                <i class="fas fa-code"></i>
            </div>
            <h1>Hi 👋, I'm Rasanjana</h1>
            <p class="tagline">A passionate frontend developer</p>
            <div class="location">
                <i class="fas fa-map-marker-alt"></i>
                <span>Sri Lanka</span>
            </div>
        </header>

        <section>
            <h2><i class="fas fa-rocket"></i> Languages and Tools I Use</h2>
            <div class="skills-container">
                <div class="skill-card">
                    <i class="fab fa-cuttlefish"></i>
                    <p>C</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-java"></i>
                    <p>Java</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-php"></i>
                    <p>PHP</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-js-square"></i>
                    <p>JavaScript</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-python"></i>
                    <p>Python</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-html5"></i>
                    <p>HTML5</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-css3-alt"></i>
                    <p>CSS3</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-bootstrap"></i>
                    <p>Bootstrap</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-flutter"></i>
                    <p>Flutter</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-database"></i>
                    <p>MySQL</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-ship"></i>
                    <p>Kubernetes</p>
                </div>
            </div>
        </section>

        <section>
            <h2><i class="fas fa-chart-line"></i> GitHub Statistics</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <div class="stat-value">48</div>
                    <div class="stat-label">Repositories</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">127</div>
                    <div class="stat-label">Contributions</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">19</div>
                    <div class="stat-label">Followers</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">6</div>
                    <div class="stat-label">Languages</div>
                </div>
            </div>
        </section>

        <section>
            <h2><i class="fas fa-trophy"></i> GitHub Achievements</h2>
            <div class="trophy-container">
                <div class="trophy">
                    <i class="fas fa-medal"></i>
                    <p>Gold</p>
                </div>
                <div class="trophy">
                    <i class="fas fa-medal"></i>
                    <p>Silver</p>
                </div>
                <div class="trophy">
                    <i class="fas fa-medal"></i>
                    <p>Bronze</p>
                </div>
                <div class="trophy">
                    <i class="fas fa-star"></i>
                    <p>Star</p>
                </div>
                <div class="trophy">
                    <i class="fas fa-code-branch"></i>
                    <p>Fork</p>
                </div>
                <div class="trophy">
                    <i class="fas fa-heart"></i>
                    <p>Heart</p>
                </div>
            </div>
        </section>

        <div class="social-links">
            <a href="#" class="social-link">
                <i class="fab fa-github"></i>
            </a>
            <a href="#" class="social-link">
                <i class="fab fa-linkedin-in"></i>
            </a>
            <a href="#" class="social-link">
                <i class="fab fa-twitter"></i>
            </a>
            <a href="#" class="social-link">
                <i class="fab fa-dev"></i>
            </a>
        </div>

        <footer>
            <p>© 2023 Rasanjana. All rights reserved.</p>
        </footer>
    </div>

    <script>
        // Simple animation on scroll
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            sections.forEach(section => {
                section.style.opacity = 0;
                section.style.transform = 'translateY(20px)';
                section.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
