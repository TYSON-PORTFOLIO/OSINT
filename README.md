<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tyson OSINT Telegram Bot</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a2a6c, #2c3e50);
            color: #fff;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 20px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            animation: fadeIn 1s ease-in-out;
        }

        .logo {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }

        .logo-icon {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, #3498db, #8e44ad);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 50px;
            box-shadow: 0 0 20px rgba(52, 152, 219, 0.7);
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff9966, #ff5e62);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
        }

        .tagline {
            font-size: 1.4rem;
            color: #bdc3c7;
            max-width: 700px;
            margin: 0 auto 25px;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #3498db, #8e44ad);
            color: white;
            padding: 15px 40px;
            font-size: 1.2rem;
            font-weight: bold;
            text-decoration: none;
            border-radius: 50px;
            margin-top: 20px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
            background: linear-gradient(45deg, #2980b9, #9b59b6);
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }

        .card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 30px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.12);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        .card i {
            font-size: 2.5rem;
            color: #3498db;
            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 1.6rem;
            margin-bottom: 15px;
            color: #3498db;
        }

        .card p {
            color: #ecf0f1;
            line-height: 1.6;
        }

        .commands {
            background: rgba(0, 0, 0, 0.3);
            border-radius: 15px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .commands h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: #3498db;
        }

        .command-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .command-card {
            background: rgba(52, 152, 219, 0.15);
            border-radius: 10px;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .command-card:hover {
            background: rgba(52, 152, 219, 0.25);
            transform: scale(1.03);
        }

        .command-card h4 {
            color: #3498db;
            font-size: 1.3rem;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }

        .command-card h4 i {
            margin-right: 10px;
        }

        .command-card p {
            color: #ecf0f1;
            line-height: 1.5;
        }

        footer {
            text-align: center;
            padding: 30px;
            margin-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }

        .social-icons a {
            color: #3498db;
            font-size: 1.8rem;
            transition: transform 0.3s ease;
        }

        .social-icons a:hover {
            transform: translateY(-5px);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1.1rem;
            }
            
            .cta-button {
                padding: 12px 30px;
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-robot"></i>
                </div>
            </div>
            <h1>Tyson OSINT Telegram Bot</h1>
            <p class="tagline">Advanced Open Source Intelligence gathering tool directly in your Telegram messenger. Gather information, analyze data, and conduct investigations with ease.</p>
            <a href="https://t.me/Nobita_hack_2_bot" class="cta-button">
                <i class="fab fa-telegram"></i> Start Using Bot
            </a>
        </header>

        <section class="features">
            <div class="card">
                <i class="fas fa-search"></i>
                <h3>Comprehensive Data Collection</h3>
                <p>Tyson OSINT Bot scans multiple sources including social media, public databases, and websites to gather comprehensive information on your target.</p>
            </div>
            
            <div class="card">
                <i class="fas fa-shield-alt"></i>
                <h3>Privacy Focused</h3>
                <p>All investigations are conducted ethically and legally. We don't store your query data and respect privacy regulations.</p>
            </div>
            
            <div class="card">
                <i class="fas fa-bolt"></i>
                <h3>Lightning Fast Results</h3>
                <p>Get detailed OSINT reports in seconds. Our powerful infrastructure processes requests quickly and efficiently.</p>
            </div>
        </section>

        <section class="commands">
            <h2>Bot Commands</h2>
            <div class="command-grid">
                <div class="command-card">
                    <h4><i class="fas fa-user"></i> /whois</h4>
                    <p>Perform WHOIS lookup for domain names to get registration information.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-network-wired"></i> /ip</h4>
                    <p>Get detailed information about an IP address including geolocation and ISP.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-envelope"></i> /email</h4>
                    <p>Verify email addresses and check for data breaches.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-phone"></i> /phone</h4>
                    <p>Lookup phone number information including carrier and location.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-hashtag"></i> /username</h4>
                    <p>Search for a username across multiple social media platforms.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-image"></i> /image</h4>
                    <p>Reverse image search to find similar images across the web.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-file"></i> /doc</h4>
                    <p>Analyze documents and extract metadata information.</p>
                </div>
                
                <div class="command-card">
                    <h4><i class="fas fa-question-circle"></i> /help</h4>
                    <p>Get assistance and see all available commands with examples.</p>
                </div>
            </div>
        </section>

        <section class="features">
            <div class="card">
                <i class="fas fa-lock"></i>
                <h3>Secure Communication</h3>
                <p>All interactions with Tyson OSINT Bot are encrypted using Telegram's secure protocol, ensuring your investigations remain confidential.</p>
            </div>
            
            <div class="card">
                <i class="fas fa-sync-alt"></i>
                <h3>Regular Updates</h3>
                <p>Our development team constantly updates the bot with new features and data sources to keep you ahead in your OSINT investigations.</p>
            </div>
            
            <div class="card">
                <i class="fas fa-users"></i>
                <h3>Community Support</h3>
                <p>Join our community of cybersecurity professionals and OSINT researchers to share tips and techniques.</p>
            </div>
        </section>

        <footer>
            <p>© 2023 Tyson OSINT Bot. All rights reserved.</p>
            <div class="social-icons">
                <a href="#"><i class="fab fa-telegram"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-discord"></i></a>
            </div>
            <p>Disclaimer: This bot is intended for ethical security research and authorized investigations only.</p>
        </footer>
    </div>

    <script>
        // Simple animation on scroll
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.card, .command-card');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'fadeIn 0.8s forwards';
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.1 });
            
            cards.forEach(card => {
                card.style.opacity = '0';
                observer.observe(card);
            });
            
            // Button hover effect
            const ctaButton = document.querySelector('.cta-button');
            ctaButton.addEventListener('mouseover', function() {
                this.style.transform = 'translateY(-3px)';
            });
            
            ctaButton.addEventListener('mouseout', function() {
                this.style.transform = 'translateY(0)';
            });
        });
    </script>
</body>
</html>
