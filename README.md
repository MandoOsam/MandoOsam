
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mando Osama - Full Stack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #333;
        }

        .container {
            max-width: 800px;
            margin: 20px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            backdrop-filter: blur(10px);
            animation: slideUp 1s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            background: linear-gradient(135deg, #2c3e50, #3498db);
            padding: 40px 30px;
            text-align: center;
            color: white;
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
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(255, 255, 255, 0.1) 10px,
                rgba(255, 255, 255, 0.1) 20px
            );
            animation: move 20s linear infinite;
        }

        @keyframes move {
            0% {
                transform: translate(-50%, -50%) rotate(0deg);
            }
            100% {
                transform: translate(-50%, -50%) rotate(360deg);
            }
        }

        .profile-image {
            width: 120px;
            height: 120px;
            margin: 0 auto 20px;
            position: relative;
            z-index: 2;
        }

        .profile-image img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 4px solid rgba(255, 255, 255, 0.3);
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .profile-image img:hover {
            transform: scale(1.1);
        }

        .name {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .title {
            font-size: 1.2rem;
            opacity: 0.9;
            position: relative;
            z-index: 2;
        }

        .content {
            padding: 40px 30px;
        }

        .info-card {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            border-left: 5px solid #3498db;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .info-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .info-item {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            font-size: 1.1rem;
            direction: rtl;
        }

        .info-item:last-child {
            margin-bottom: 0;
        }

        .info-item i {
            font-size: 1.5rem;
            color: #3498db;
            margin-left: 15px;
            width: 30px;
            text-align: center;
        }

        .skills {
            margin-top: 30px;
        }

        .skills h3 {
            text-align: center;
            margin-bottom: 20px;
            color: #2c3e50;
            font-size: 1.5rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .skill-tag {
            background: linear-gradient(135deg, #3498db, #2c3e50);
            color: white;
            padding: 12px 20px;
            border-radius: 25px;
            text-align: center;
            font-weight: 500;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }

        .skill-tag:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(52, 152, 219, 0.3);
        }

        .social-links {
            text-align: center;
            margin-top: 30px;
            padding-top: 30px;
            border-top: 2px solid #eee;
        }

        .social-link {
            display: inline-block;
            margin: 0 15px;
            padding: 15px;
            background: #3498db;
            color: white;
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.5rem;
        }

        .social-link:hover {
            background: #2c3e50;
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .github-link {
            background: #333;
        }

        .linkedin-link {
            background: #0077b5;
        }

        .email-link {
            background: #e74c3c;
        }

        @media (max-width: 768px) {
            .container {
                margin: 10px;
            }

            .header {
                padding: 30px 20px;
            }

            .name {
                font-size: 2rem;
            }

            .content {
                padding: 30px 20px;
            }

            .info-item {
                font-size: 1rem;
            }

            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
                gap: 10px;
            }
        }

        @media (max-width: 480px) {
            .name {
                font-size: 1.8rem;
            }

            .title {
                font-size: 1rem;
            }

            .social-link {
                margin: 0 10px;
                padding: 12px;
                font-size: 1.3rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="profile-image">
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/828c432b-e8b2-4d02-90ad-09d3252054d8.png" alt="Professional headshot of Mando Osama, a young software developer with a friendly smile wearing a modern casual shirt" />
            </div>
            <h1 class="name">Mando Osama</h1>
            <p class="title">Full Stack Web Developer</p>
        </div>

        <div class="content">
            <div class="info-card">
                <div class="info-item">
                    <i class="fas fa-user"></i>
                    <span>اسمي مندو أسامة</span>
                </div>
                
                <div class="info-item">
                    <i class="fas fa-graduation-cap"></i>
                    <span>طالب في كلية الحاسبات والمعلومات - جامعة طنطا</span>
                </div>
                
                <div class="info-item">
                    <i class="fas fa-laptop-code"></i>
                    <span>أدرس تطوير الويب الشامل (Full Stack Web Development)</span>
                </div>
                
                <div class="info-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <span>طنطا، مصر</span>
                </div>
            </div>

            <div class="skills">
                <h3>التقنيات التي أتعلمها</h3>
                <div class="skills-grid">
                    <div class="skill-tag">HTML5</div>
                    <div class="skill-tag">CSS3</div>
                    <div class="skill-tag">JavaScript</div>
                    <div class="skill-tag">React</div>
                    <div class="skill-tag">Node.js</div>
                    <div class="skill-tag">MongoDB</div>
                    <div class="skill-tag">Express.js</div>
                    <div class="skill-tag">Git & GitHub</div>
                </div>
            </div>

            <div class="social-links">
                <a href="#" class="social-link github-link" title="GitHub Profile">
                    <i class="fab fa-github"></i>
                </a>
                <a href="#" class="social-link linkedin-link" title="LinkedIn Profile">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="#" class="social-link email-link" title="Email">
                    <i class="fas fa-envelope"></i>
                </a>
            </div>
        </div>
    </div>

    <script>
        // Add smooth scrolling and interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill tags on scroll
            const skillTags = document.querySelectorAll('.skill-tag');
            
            skillTags.forEach((tag, index) => {
                tag.style.opacity = '0';
                tag.style.transform = 'translateY(20px)';
                
                setTimeout(() => {
                    tag.style.transition = 'all 0.5s ease';
                    tag.style.opacity = '1';
                    tag.style.transform = 'translateY(0)';
                }, index * 100);
            });

            // Add click animation to skill tags
            skillTags.forEach(tag => {
                tag.addEventListener('click', function() {
                    this.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        this.style.transform = 'scale(1)';
                    }, 150);
                });
            });

            // Add hover effect to info cards
            const infoCards = document.querySelectorAll('.info-card');
            infoCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.background = 'linear-gradient(135deg, #f8f9fa, #e9ecef)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.background = '#f8f9fa';
                });
            });

            // Add typing effect to name
            const nameElement = document.querySelector('.name');
            const originalText = nameElement.textContent;
            nameElement.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < originalText.length) {
                    nameElement.textContent += originalText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 100);
                }
            }
            
            setTimeout(typeWriter, 500);

            // Add floating animation to profile image
            const profileImage = document.querySelector('.profile-image img');
            setInterval(() => {
                profileImage.style.transform = 'translateY(-5px)';
                setTimeout(() => {
                    profileImage.style.transform = 'translateY(0)';
                }, 1000);
            }, 2000);
        });

        // Add particles background effect
        function createParticle() {
            const particle = document.createElement('div');
            particle.style.cssText = `
                position: fixed;
                width: 4px;
                height: 4px;
                background: rgba(255, 255, 255, 0.6);
                border-radius: 50%;
                pointer-events: none;
                z-index: -1;
                animation: float 6s linear infinite;
            `;
            
            particle.style.left = Math.random() * 100 + 'vw';
            particle.style.animationDelay = Math.random() * 6 + 's';
            
            document.body.appendChild(particle);
            
            setTimeout(() => {
                particle.remove();
            }, 6000);
        }

        // Add CSS for particle animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes float {
                0% {
                    transform: translateY(100vh) rotate(0deg);
                    opacity: 0;
                }
                10% {
                    opacity: 1;
                }
                90% {
                    opacity: 1;
                }
                100% {
                    transform: translateY(-100vh) rotate(360deg);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);

        // Create particles every 300ms
        setInterval(createParticle, 300);
    </script>
</body>
</html>

