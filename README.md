<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pragnesh Reddy - AI Enthusiast</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(120, 119, 198, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 40% 80%, rgba(120, 219, 255, 0.1) 0%, transparent 50%);
            animation: bgShift 20s ease-in-out infinite;
        }

        @keyframes bgShift {
            0%, 100% { transform: translateX(0) translateY(0); }
            25% { transform: translateX(-20px) translateY(-10px); }
            50% { transform: translateX(20px) translateY(10px); }
            75% { transform: translateX(-10px) translateY(20px); }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 80px 0;
            position: relative;
        }

        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 4px solid transparent;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            padding: 4px;
            margin: 0 auto 30px;
            animation: pulse 2s ease-in-out infinite;
        }

        .profile-img img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .main-title {
            font-size: 3.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            animation: slideInDown 1s ease-out;
        }

        .subtitle {
            font-size: 1.5rem;
            color: #a0aec0;
            margin-bottom: 40px;
            animation: slideInUp 1s ease-out 0.3s both;
        }

        @keyframes slideInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease-out;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: rgba(255, 255, 255, 0.2);
        }

        .stat-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            display: block;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: #4ecdc4;
            margin-bottom: 10px;
        }

        /* About Section */
        .about {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 30px;
            padding: 50px;
            margin: 60px 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
            animation: fadeIn 1s ease-out;
        }

        .about h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .about-item {
            display: flex;
            align-items: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            transition: transform 0.3s ease;
        }

        .about-item:hover {
            transform: translateX(10px);
        }

        .about-icon {
            font-size: 1.5rem;
            margin-right: 15px;
            color: #4ecdc4;
        }

        /* Skills Section */
        .skills {
            margin: 80px 0;
        }

        .skills h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 50px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 20px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px 15px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-card:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            border-color: #4ecdc4;
        }

        .skill-icon {
            width: 40px;
            height: 40px;
            margin: 0 auto 15px;
            display: block;
        }

        .skill-name {
            font-size: 0.9rem;
            font-weight: 600;
            color: #e2e8f0;
        }

        /* Social Links */
        .social {
            text-align: center;
            margin: 80px 0;
        }

        .social h2 {
            font-size: 2.5rem;
            margin-bottom: 40px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
        }

        .social-link {
            display: flex;
            align-items: center;
            padding: 15px 25px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 50px;
            text-decoration: none;
            color: #e2e8f0;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .social-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            border-color: #4ecdc4;
            color: #ffffff;
        }

        .social-icon {
            width: 24px;
            height: 24px;
            margin-right: 10px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .main-title {
                font-size: 2.5rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
            }
            
            .about {
                padding: 30px 20px;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
                gap: 15px;
            }
            
            .social-links {
                gap: 15px;
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-img">
                <img src="https://via.placeholder.com/120x120/4ecdc4/ffffff?text=PR" alt="Pragnesh Reddy">
            </div>
            <h1 class="main-title">Hi 👋, I'm Pragnesh Reddy</h1>
            <p class="subtitle">A passionate AI Enthusiast from India</p>
        </header>

        <!-- Stats Section -->
        <section class="stats">
            <div class="stat-card">
                <span class="stat-icon">👁️</span>
                <div class="stat-number">5.2K+</div>
                <div>Profile Views</div>
            </div>
            <div class="stat-card">
                <span class="stat-icon">🏆</span>
                <div class="stat-number">15+</div>
                <div>GitHub Trophies</div>
            </div>
            <div class="stat-card">
                <span class="stat-icon">🚀</span>
                <div class="stat-number">25+</div>
                <div>Projects Completed</div>
            </div>
        </section>

        <!-- About Section -->
        <section class="about">
            <h2>About Me</h2>
            <div class="about-grid">
                <div class="about-item">
                    <span class="about-icon">🌱</span>
                    <div>Currently learning <strong>Generative AI</strong></div>
                </div>
                <div class="about-item">
                    <span class="about-icon">👯</span>
                    <div>Looking to collaborate on <strong>AI-Based Projects</strong></div>
                </div>
                <div class="about-item">
                    <span class="about-icon">👨‍💻</span>
                    <div>All projects available at <strong>Portfolio</strong></div>
                </div>
                <div class="about-item">
                    <span class="about-icon">💬</span>
                    <div>Ask me about <strong>Machine Learning & Deep Learning</strong></div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section class="skills">
            <h2>Technologies & Tools</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <img class="skill-icon" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python">
                    <div class="skill-name">Python</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://www.vectorlogo.zone/logos/tensorflow/tensorflow-icon.svg" alt="TensorFlow">
                    <div class="skill-name">TensorFlow</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" alt="Scikit-learn">
                    <div class="skill-name">Scikit-learn</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="Pandas">
                    <div class="skill-name">Pandas</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" alt="Seaborn">
                    <div class="skill-name">Seaborn</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://www.vectorlogo.zone/logos/opencv/opencv-icon.svg" alt="OpenCV">
                    <div class="skill-name">OpenCV</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript">
                    <div class="skill-name">JavaScript</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js">
                    <div class="skill-name">Node.js</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://reactnative.dev/img/header_logo.svg" alt="React Native">
                    <div class="skill-name">React Native</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://cdn.worldvectorlogo.com/logos/django.svg" alt="Django">
                    <div class="skill-name">Django</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="MongoDB">
                    <div class="skill-name">MongoDB</div>
                </div>
                <div class="skill-card">
                    <img class="skill-icon" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt="AWS">
                    <div class="skill-name">AWS</div>
                </div>
            </div>
        </section>

        <!-- Social Links -->
        <section class="social">
            <h2>Connect with Me</h2>
            <div class="social-links">
                <a href="https://linkedin.com/in/pragnesh-reddy-gajjala-014242255" class="social-link" target="_blank">
                    <img class="social-icon" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn">
                    LinkedIn
                </a>
                <a href="https://pragneshportfolio.netlify.app/" class="social-link" target="_blank">
                    <span class="social-icon">🌐</span>
                    Portfolio
                </a>
                <a href="https://instagram.com/praxx.9" class="social-link" target="_blank">
                    <img class="social-icon" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="Instagram">
                    Instagram
                </a>
                <a href="https://www.hackerrank.com/pragneshreddyga1" class="social-link" target="_blank">
                    <img class="social-icon" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/hackerrank.svg" alt="HackerRank">
                    HackerRank
                </a>
                <a href="https://www.leetcode.com/praggy_reddy" class="social-link" target="_blank">
                    <img class="social-icon" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" alt="LeetCode">
                    LeetCode
                </a>
            </div>
        </section>
    </div>

    <script>
        // Add smooth scrolling and interaction effects
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill cards on scroll
            const skillCards = document.querySelectorAll('.skill-card');
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'fadeInUp 0.6s ease-out forwards';
                        entry.target.style.animationDelay = Math.random() * 0.3 + 's';
                    }
                });
            }, observerOptions);

            skillCards.forEach(card => {
                card.style.opacity = '0';
                observer.observe(card);
            });

            // Add hover effects to social links
            const socialLinks = document.querySelectorAll('.social-link');
            socialLinks.forEach(link => {
                link.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-3px) scale(1.05)';
                });
                
                link.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });

            // Add particle effect on click
            document.addEventListener('click', function(e) {
                createParticle(e.clientX, e.clientY);
            });

            function createParticle(x, y) {
                const particle = document.createElement('div');
                particle.style.position = 'fixed';
                particle.style.left = x + 'px';
                particle.style.top = y + 'px';
                particle.style.width = '6px';
                particle.style.height = '6px';
                particle.style.backgroundColor = '#4ecdc4';
                particle.style.borderRadius = '50%';
                particle.style.pointerEvents = 'none';
                particle.style.zIndex = '9999';
                particle.style.animation = 'particleFloat 1s ease-out forwards';
                
                document.body.appendChild(particle);
                
                setTimeout(() => {
                    particle.remove();
                }, 1000);
            }

            // Add CSS for particle animation
            const style = document.createElement('style');
            style.textContent = `
                @keyframes particleFloat {
                    0% {
                        transform: translateY(0) scale(1);
                        opacity: 1;
                    }
                    100% {
                        transform: translateY(-100px) scale(0);
                        opacity: 0;
                    }
                }
            `;
            document.head.appendChild(style);
        });
    </script>
</body>
</html>
