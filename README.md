<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rescate Matemático - Sitio Oficial</title>
    <style>
        /* ESTILOS GENERALES */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial Rounded MT Bold', 'Arial', sans-serif;
        }

        :root {
            --primary: #3498db;
            --secondary: #e74c3c;
            --accent: #f1c40f;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --success: #27ae60;
            --math-purple: #9b59b6;
        }

        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: white;
            line-height: 1.6;
            min-height: 100vh;
        }

        /* HEADER Y LOGO */
        header {
            background: rgba(26, 26, 46, 0.95);
            backdrop-filter: blur(10px);
            padding: 1.5rem 0;
            border-bottom: 3px solid var(--accent);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, var(--accent), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            font-weight: bold;
            color: var(--dark);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        .logo-text {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(to right, var(--accent), var(--primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        /* HERO SECTION */
        .hero {
            text-align: center;
            padding: 6rem 2rem 4rem;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="1" fill="%23f1c40f" opacity="0.3"/></svg>') repeat;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            background: linear-gradient(to right, var(--accent), var(--math-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .game-preview {
            max-width: 800px;
            height: 350px;
            margin: 2rem auto;
            background: linear-gradient(45deg, var(--primary), var(--math-purple));
            border-radius: 20px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 1rem;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            padding: 2rem;
        }

        .preview-title {
            font-size: 2.5rem;
            color: white;
        }

        .preview-subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        .play-button {
            display: inline-block;
            background: linear-gradient(to right, var(--secondary), var(--accent));
            color: white;
            padding: 1rem 3rem;
            font-size: 1.3rem;
            font-weight: bold;
            text-decoration: none;
            border-radius: 50px;
            margin-top: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 10px 20px rgba(231, 76, 60, 0.3);
        }

        .play-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 30px rgba(231, 76, 60, 0.5);
        }

        /* SECTIONS */
        .section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--accent);
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }

        /* GAMEPLAY SECTION */
        .gameplay-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .gameplay-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .gameplay-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-align: center;
        }

        /* CHARACTERS SECTION */
        .characters-section {
            background: rgba(0, 0, 0, 0.2);
        }

        .characters-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .character-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
        }

        .character-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.15);
        }

        .character-avatar {
            width: 100px;
            height: 100px;
            background: linear-gradient(45deg, var(--accent), var(--secondary));
            border-radius: 50%;
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            font-weight: bold;
        }

        /* DEMO SECTION */
        .demo-section {
            text-align: center;
            background: rgba(0, 0, 0, 0.3);
            padding: 4rem 2rem;
        }

        .demo-container {
            max-width: 800px;
            margin: 0 auto;
            padding: 3rem;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            border: 2px solid var(--primary);
        }

        .demo-button {
            display: inline-block;
            background: var(--success);
            color: white;
            padding: 1rem 2.5rem;
            font-size: 1.3rem;
            text-decoration: none;
            border-radius: 50px;
            margin: 2rem 0;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        .demo-button:hover {
            background: #229954;
            transform: scale(1.1);
        }

        /* CREDITS SECTION */
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .team-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 1.5rem;
            border-radius: 15px;
            text-align: center;
        }

        /* FOOTER */
        footer {
            background: rgba(0, 0, 0, 0.9);
            padding: 3rem 2rem;
            text-align: center;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .copyright {
            color: #aaa;
            margin-top: 2rem;
            font-size: 0.9rem;
        }

        /* RESPONSIVE */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 1rem;
                text-align: center;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .game-preview {
                height: 300px;
                padding: 1rem;
            }

            .section {
                padding: 3rem 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- HEADER CON LOGO -->
    <header>
        <div class="header-container">
            <div class="logo-container">
                <div class="logo-icon">🧮</div>
                <div class="logo-text">RESCATE MATEMÁTICO</div>
            </div>
        </div>
    </header>

    <!-- HERO SECTION -->
    <section class="hero">
        <h1>¡LA AVENTURA MATEMÁTICA COMIENZA!</h1>
        <p style="font-size: 1.3rem; max-width: 800px; margin: 0 auto 2rem; opacity: 0.9;">
            Un videojuego educativo donde cada problema matemático es un paso hacia la victoria. 
            Rescata a la Princesa de los Números y derrota a la Reina de la Ignorancia.
        </p>
        
        <div class="game-preview">
            <div class="preview-title">🎮 RESCATE MATEMÁTICO 🧮</div>
            <div class="preview-subtitle">¡Juego educativo 100% funcional!</div>
            <a href="file:///C:/Users/IK/Desktop/Aventura%20matematica.html%20da.html" class="play-button">
                ▶ JUGAR AHORA
            </a>
        </div>
    </section>

    <!-- GAMEPLAY SECTION -->
    <section id="gameplay" class="section">
        <h2 class="section-title">MECÁNICAS DEL JUEGO</h2>
        <div class="gameplay-grid">
            <div class="gameplay-card">
                <div class="gameplay-icon">🎯</div>
                <h3>CONTROLES INTUITIVOS</h3>
                <p>Mueve al héroe con flechas o WASD, salta con ESPACIO o ↑, agáchate con ↓ o S, y corre con SHIFT.</p>
            </div>
            <div class="gameplay-card">
                <div class="gameplay-icon">⚔️</div>
                <h3>COMBATE MATEMÁTICO</h3>
                <p>Los enemigos te desafían con problemas de suma, resta y multiplicación. ¡Resuelve en 60 segundos!</p>
            </div>
            <div class="gameplay-card">
                <div class="gameplay-icon">🌟</div>
                <h3>8 MUNDOS ÚNICOS</h3>
                <p>Desde el Bosque de las Sumas hasta el Castillo Final, cada mundo aumenta la dificultad.</p>
            </div>
            <div class="gameplay-card">
                <div class="gameplay-icon">🏆</div>
                <h3>SISTEMA DE PUNTUACIÓN</h3>
                <p>Monedas: +100 pts | Enemigos: +200 pts | Mundos: +1000 pts | ¡Persigue el récord!</p>
            </div>
        </div>
    </section>

    <!-- CHARACTERS SECTION -->
    <section id="personajes" class="section characters-section">
        <h2 class="section-title">PERSONAJES Y UNIVERSO</h2>
        <div class="characters-grid">
            <div class="character-card">
                <div class="character-avatar">👑</div>
                <h3>EL HÉROE MATEMÁTICO</h3>
                <p>Valiente guardián que usa las matemáticas como arma para rescatar a la princesa y salvar el reino.</p>
            </div>
            <div class="character-card">
                <div class="character-avatar">👸</div>
                <h3>PRINCESA DE LOS NÚMEROS</h3>
                <p>Guardián de las ecuaciones sagradas. Su secuestro amenaza el equilibrio matemático del reino.</p>
            </div>
            <div class="character-card">
                <div class="character-avatar">👿</div>
                <h3>REINA DE LA IGNORANCIA</h3>
                <p>Villana que odia el conocimiento y busca eliminar las matemáticas para gobernar con confusión.</p>
            </div>
            <div class="character-card">
                <div class="character-avatar">🐉</div>
                <h3>EJÉRCITO MATEMÁTICO</h3>
                <p>Bichos Calculadores, Tortugas de Ecuaciones y Plantas de Multiplicación protegen cada mundo.</p>
            </div>
        </div>
        
        <div style="margin-top: 3rem; padding: 2rem; background: rgba(255,255,255,0.1); border-radius: 15px;">
            <h3 style="color: var(--accent); margin-bottom: 1rem;">LA HISTORIA DEL UNIVERSO MATEMÁTICO</h3>
            <p>En un reino donde los números gobiernan la realidad, las ecuaciones mantienen el balance del universo. 
            La Princesa de los Números era la guardiana de este equilibrio, pero su secuestro por la Reina de la 
            Ignorancia ha desatado el caos. Ahora, monstruos matemáticos campan por el reino, y solo un verdadero 
            héroe, armado con su ingenio matemático, puede restaurar el orden resolviendo los problemas que 
            mantienen la realidad en pie.</p>
            <p style="margin-top: 1rem; font-style: italic; color: var(--accent);">
                "Aquí, cada problema resuelto es un paso más hacia la salvación del reino."
            </p>
        </div>
    </section>

    <!-- DEMO SECTION -->
    <section id="demo" class="section demo-section">
        <h2 class="section-title">¡JUGAR DEMO!</h2>
        <div class="demo-container">
            <h3 style="color: var(--accent); margin-bottom: 1rem;">DEMO COMPLETA DISPONIBLE</h3>
            <p style="font-size: 1.2rem; margin-bottom: 1.5rem;">
                El juego completo "Rescate Matemático" está listo para jugar. 
                Haz clic en el botón para abrir el juego directamente desde tu computadora.
            </p>
            
            <div style="background: rgba(0,0,0,0.3); padding: 1.5rem; border-radius: 10px; margin: 2rem 0;">
                <h4 style="color: var(--accent); margin-bottom: 0.5rem;">🎮 CONTROLES DEL JUEGO:</h4>
                <p>• ← → o A D: Moverse izquierda/derecha</p>
                <p>• ↑ o ESPACIO: Saltar</p>
                <p>• ↓ o S: Agacharse</p>
                <p>• SHIFT: Correr rápido</p>
                <p>• Los enemigos inician combates automáticamente al tocarlos</p>
                <p>• ¡Tienes 60 segundos para resolver cada problema!</p>
            </div>
            
            <a href="file:///C:/Users/IK/Desktop/Aventura%20matematica.html%20da.html" class="demo-button">
                ▶ ABRIR JUEGO COMPLETO
            </a>
            
            <p style="color: var(--accent); margin-top: 1rem; font-size: 0.9rem;">
                ⚠️ El juego se abrirá directamente desde tu computadora
            </p>
        </div>
    </section>

    <!-- CREDITS SECTION -->
    <section id="creditos" class="section">
        <h2 class="section-title">EQUIPO DE DESARROLLO</h2>
        <div class="team-grid">
            <div class="team-card">
                <h4>DESARROLLADOR PRINCIPAL</h4>
                <p>Programación del juego completo</p>
                <div style="color: var(--accent); font-weight: bold; margin-top: 0.5rem;">Programador</div>
            </div>
            <div class="team-card">
                <h4>DISEÑADOR DE NIVELES</h4>
                <p>Diseño de mundos y desafíos</p>
                <div style="color: var(--accent); font-weight: bold; margin-top: 0.5rem;">Game Designer</div>
            </div>
            <div class="team-card">
                <h4>ARTISTA CONCEPTUAL</h4>
                <p>Diseño visual y personajes</p>
                <div style="color: var(--accent); font-weight: bold; margin-top: 0.5rem;">Artista Digital</div>
            </div>
            <div class="team-card">
                <h4>ASESOR EDUCATIVO</h4>
                <p>Diseño de problemas matemáticos</p>
                <div style="color: var(--accent); font-weight: bold; margin-top: 0.5rem;">Consultor Pedagógico</div>
            </div>
        </div>
        
        <div style="margin-top: 3rem; padding: 2rem; background: rgba(255,255,255,0.1); border-radius: 15px;">
            <h3 style="color: var(--accent); margin-bottom: 1rem;">PROCESO DE DESARROLLO</h3>
            <p><strong>Duración:</strong> 3 semanas de desarrollo intensivo</p>
            <p><strong>Tecnologías utilizadas:</strong> HTML5, CSS3, JavaScript, Phaser.js</p>
            <p><strong>Metodología:</strong> Desarrollo iterativo con pruebas constantes</p>
            <p><strong>Objetivo educativo:</strong> Transformar el aprendizaje de matemáticas en una aventura emocionante</p>
            
            <div style="margin-top: 1.5rem; padding: 1rem; background: rgba(120, 224, 143, 0.1); border-radius: 10px;">
                <h4 style="color: var(--accent); margin-bottom: 0.5rem;">📈 FASES DEL PROYECTO:</h4>
                <p>• Semana 1: Prototipo básico con física y controles</p>
                <p>• Semana 2: Sistema de combate matemático y enemigos</p>
                <p>• Semana 3: Pulido, sonidos y sitio web vitrina</p>
            </div>
            
            <p style="margin-top: 1.5rem; font-style: italic; color: #d1d8e0;">
                "Cada error de código fue una lección, cada problema resuelto una victoria. 
                Este proyecto demostró que aprender puede ser la aventura más épica de todas."
            </p>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <div class="footer-content">
            <div style="font-size: 2rem; margin-bottom: 1rem; color: var(--accent);">🧮 RESCATE MATEMÁTICO</div>
            <p style="max-width: 600px; margin: 0 auto 1rem; font-size: 1.1rem;">
                Videojuego educativo desarrollado para hacer las matemáticas divertidas y accesibles.
            </p>
            
            <div style="margin: 2rem 0;">
                <a href="#gameplay" style="color: var(--accent); margin: 0 15px; text-decoration: none;">Gameplay</a> •
                <a href="#personajes" style="color: var(--accent); margin: 0 15px; text-decoration: none;">Personajes</a> •
                <a href="#demo" style="color: var(--accent); margin: 0 15px; text-decoration: none;">Demo</a> •
                <a href="#creditos" style="color: var(--accent); margin: 0 15px; text-decoration: none;">Créditos</a>
            </div>
            
            <div class="copyright">
                © 2024 RESCATE MATEMÁTICO - Proyecto Educativo<br>
                Desarrollado con ❤️ para transformar el aprendizaje<br>
                Contacto: equipo@rescatematematico.com<br>
                Todos los derechos reservados
            </div>
        </div>
    </footer>

    <script>
        // NAVEGACIÓN SUAVE
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const target = document.querySelector(targetId);
                if(target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // ANIMACIÓN PARA TARJETAS
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if(entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // OBSERVAR ELEMENTOS
        document.querySelectorAll('.gameplay-card, .character-card, .team-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
            observer.observe(card);
        });

        // EFECTO HEADER AL SCROLL
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if(window.scrollY > 100) {
                header.style.background = 'rgba(26, 26, 46, 0.98)';
                header.style.boxShadow = '0 5px 20px rgba(0,0,0,0.5)';
            } else {
                header.style.background = 'rgba(26, 26, 46, 0.95)';
                header.style.boxShadow = 'none';
            }
        });

        // MENSAJE AL ABRIR EL JUEGO
        document.querySelectorAll('a[href*="Aventura"]').forEach(link => {
            link.addEventListener('click', function(e) {
                if(!confirm('¿Estás seguro de que quieres abrir el juego? Se abrirá en una nueva ventana/pestaña.')) {
                    e.preventDefault();
                }
            });
        });
    </script>
</body>
</html>
