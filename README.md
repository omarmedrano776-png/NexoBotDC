# NexoBotDC<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Discord Bot - Tu Bot Multifuncional</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            padding: 20px 0;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #a78bfa;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 100px 20px;
            animation: fadeIn 1s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero h1 {
            font-size: 56px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 10px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 24px;
            margin-bottom: 40px;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: #fff;
            text-decoration: none;
            border-radius: 50px;
            font-size: 18px;
            font-weight: bold;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.4);
        }

        .btn-secondary {
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(10px);
            margin-left: 20px;
        }

        /* Features Section */
        .features {
            padding: 80px 20px;
            background: rgba(0,0,0,0.2);
        }

        .features h2 {
            text-align: center;
            font-size: 42px;
            margin-bottom: 60px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            padding: 30px;
            border-radius: 20px;
            transition: transform 0.3s, background 0.3s;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            background: rgba(255,255,255,0.15);
        }

        .feature-icon {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
        }

        .feature-card p {
            opacity: 0.8;
            line-height: 1.6;
        }

        /* Commands Section */
        .commands {
            padding: 80px 20px;
        }

        .commands h2 {
            text-align: center;
            font-size: 42px;
            margin-bottom: 60px;
        }

        .command-category {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            padding: 30px;
            border-radius: 20px;
            margin-bottom: 30px;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .command-category h3 {
            font-size: 28px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .command-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }

        .command-item {
            background: rgba(255,255,255,0.05);
            padding: 15px;
            border-radius: 10px;
            border-left: 4px solid #a78bfa;
        }

        .command-item code {
            color: #a78bfa;
            font-weight: bold;
            font-size: 16px;
        }

        .command-item p {
            margin-top: 8px;
            font-size: 14px;
            opacity: 0.8;
        }

        /* Stats Section */
        .stats {
            padding: 80px 20px;
            background: rgba(0,0,0,0.2);
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            max-width: 800px;
            margin: 0 auto;
        }

        .stat-item {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            padding: 40px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .stat-number {
            font-size: 48px;
            font-weight: bold;
            color: #a78bfa;
            margin-bottom: 10px;
        }

        .stat-label {
            font-size: 18px;
            opacity: 0.8;
        }

        /* Footer */
        footer {
            padding: 40px 20px;
            text-align: center;
            background: rgba(0,0,0,0.3);
            backdrop-filter: blur(10px);
        }

        .social-links {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .social-links a {
            color: #fff;
            font-size: 24px;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: #a78bfa;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 18px;
            }

            nav ul {
                flex-direction: column;
                gap: 10px;
            }

            .btn-secondary {
                margin-left: 0;
                margin-top: 10px;
            }
        }

        /* Scroll Animation */
        .fade-in {
            opacity: 0;
            animation: fadeIn 1s ease-in forwards;
        }

        .fade-in.visible {
            opacity: 1;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">
                <div class="logo-icon">🤖</div>
                <span>Discord Bot</span>
            </div>
            <ul>
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#caracteristicas">Características</a></li>
                <li><a href="#comandos">Comandos</a></li>
                <li><a href="#estadisticas">Estadísticas</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="inicio" class="hero">
        <div class="container">
            <h1>🤖 Bot Multifuncional</h1>
            <p>El bot todo-en-uno para tu servidor de Discord</p>
            <a href="#" class="btn" onclick="alert('Reemplaza este enlace con tu URL de invitación del bot')">Añadir a Discord</a>
            <a href="#comandos" class="btn btn-secondary">Ver Comandos</a>
        </div>
    </section>

    <!-- Features Section -->
    <section id="caracteristicas" class="features">
        <div class="container">
            <h2>✨ Características Principales</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">ℹ️</div>
                    <h3>Información</h3>
                    <p>Obtén información detallada de usuarios, servidor, avatares y más con comandos simples.</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">🛡️</div>
                    <h3>Moderación</h3>
                    <p>Herramientas completas de moderación: kick, ban, mute, clear y sistema de advertencias.</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">🎮</div>
                    <h3>Diversión</h3>
                    <p>Juegos, memes, dados, bola 8 mágica y mucho más para entretener a tu comunidad.</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">🎨</div>
                    <h3>Utilidades</h3>
                    <p>Encuestas, recordatorios, calculadora y herramientas útiles para tu servidor.</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <h3>Rápido y Eficiente</h3>
                    <p>Respuestas instantáneas con baja latencia. Optimizado para el mejor rendimiento.</p>
                </div>

                <div class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <h3>Seguro</h3>
                    <p>Sistema de permisos robusto y protección contra uso indebido de comandos.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Commands Section -->
    <section id="comandos" class="commands">
        <div class="container">
            <h2>📚 Lista de Comandos</h2>

            <div class="command-category">
                <h3>ℹ️ Información</h3>
                <div class="command-list">
                    <div class="command-item">
                        <code>!ayuda</code>
                        <p>Muestra todos los comandos disponibles</p>
                    </div>
                    <div class="command-item">
                        <code>!info [@usuario]</code>
                        <p>Información detallada de un usuario</p>
                    </div>
                    <div class="command-item">
                        <code>!servidor</code>
                        <p>Estadísticas del servidor</p>
                    </div>
                    <div class="command-item">
                        <code>!avatar [@usuario]</code>
                        <p>Muestra el avatar de un usuario</p>
                    </div>
                    <div class="command-item">
                        <code>!ping</code>
                        <p>Verifica la latencia del bot</p>
                    </div>
                    <div class="command-item">
                        <code>!bot</code>
                        <p>Información del bot</p>
                    </div>
                </div>
            </div>

            <div class="command-category">
                <h3>🎮 Diversión</h3>
                <div class="command-list">
                    <div class="command-item">
                        <code>!dado [XdY]</code>
                        <p>Lanza dados (ej: 2d6)</p>
                    </div>
                    <div class="command-item">
                        <code>!8ball [pregunta]</code>
                        <p>Bola mágica 8</p>
                    </div>
                    <div class="command-item">
                        <code>!meme</code>
                        <p>Obtiene un meme aleatorio</p>
                    </div>
                    <div class="command-item">
                        <code>!chiste</code>
                        <p>Cuenta un chiste</p>
                    </div>
                    <div class="command-item">
                        <code>!flip</code>
                        <p>Lanza una moneda</p>
                    </div>
                    <div class="command-item">
                        <code>!elegir [opciones]</code>
                        <p>Elige entre opciones</p>
                    </div>
                </div>
            </div>

            <div class="command-category">
                <h3>🛡️ Moderación</h3>
                <div class="command-list">
                    <div class="command-item">
                        <code>!kick @usuario [razón]</code>
                        <p>Expulsa a un usuario</p>
                    </div>
                    <div class="command-item">
                        <code>!ban @usuario [razón]</code>
                        <p>Banea a un usuario</p>
                    </div>
                    <div class="command-item">
                        <code>!unban [ID]</code>
                        <p>Desbanea a un usuario</p>
                    </div>
                    <div class="command-item">
                        <code>!clear [cantidad]</code>
                        <p>Borra mensajes</p>
                    </div>
                    <div class="command-item">
                        <code>!mute @usuario [min]</code>
                        <p>Silencia a un usuario</p>
                    </div>
                    <div class="command-item">
                        <code>!unmute @usuario</code>
                        <p>Quita el silencio</p>
                    </div>
                </div>
            </div>

            <div class="command-category">
                <h3>🎨 Utilidades</h3>
                <div class="command-list">
                    <div class="command-item">
                        <code>!encuesta "?" op1 op2</code>
                        <p>Crea una encuesta</p>
                    </div>
                    <div class="command-item">
                        <code>!recordatorio [min] [msg]</code>
                        <p>Programa un recordatorio</p>
                    </div>
                    <div class="command-item">
                        <code>!calc [expresión]</code>
                        <p>Calculadora matemática</p>
                    </div>
                    <div class="command-item">
                        <code>!reverse [texto]</code>
                        <p>Invierte un texto</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section id="estadisticas" class="stats">
        <div class="container">
            <h2>📊 Estadísticas</h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number" id="servers">1000+</div>
                    <div class="stat-label">Servidores</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="users">50K+</div>
                    <div class="stat-label">Usuarios</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="commands">40+</div>
                    <div class="stat-label">Comandos</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2024 Discord Bot. Todos los derechos reservados.</p>
            <p style="margin-top: 10px; opacity: 0.7;">Hecho con ❤️ usando discord.py</p>
            <div class="social-links">
                <a href="#" title="Discord">💬</a>
                <a href="#" title="GitHub">⚙️</a>
                <a href="#" title="Documentación">📚</a>
            </div>
        </div>
    </footer>

    <script>
        // Animación de números en estadísticas
        function animateNumber(id, start, end, duration) {
            const element = document.getElementById(id);
            const range = end - start;
            const increment = range / (duration / 16);
            let current = start;

            const timer = setInterval(() => {
                current += increment;
                if (current >= end) {
                    current = end;
                    clearInterval(timer);
                }
                element.textContent = Math.floor(current).toLocaleString() + '+';
            }, 16);
        }

        // Observer para animar cuando sea visible
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateNumber('servers', 0, 1000, 2000);
                    animateNumber('users', 0, 50000, 2000);
                    animateNumber('commands', 0, 40, 2000);
                    observer.unobserve(entry.target);
                }
            });
        });

        observer.observe(document.querySelector('.stats'));

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
                  </html>
