<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minecraft Hardcore - O Desafio Definitivo</title>
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1a1a2e, #16213e, #0f3460);
            color: #ffffff;
            overflow-x: hidden;
        }

        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23654321" width="1200" height="300"/><rect fill="%23228B22" y="300" width="1200" height="300"/><rect fill="%2387CEEB" y="0" width="1200" height="200"/></svg>');
            background-size: cover;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(255,0,0,0.1) 10px,
                rgba(255,0,0,0.1) 20px
            );
            animation: danger-pulse 3s ease-in-out infinite;
        }

        @keyframes danger-pulse {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.7; }
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.8);
            color: #ff4444;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 3px 3px 6px rgba(0,0,0,0.8), 0 0 20px rgba(255,68,68,0.5); }
            to { text-shadow: 3px 3px 6px rgba(0,0,0,0.8), 0 0 30px rgba(255,68,68,0.8); }
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            max-width: 800px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
        }

        .cta-button {
            background: linear-gradient(45deg, #ff4444, #cc0000);
            color: white;
            padding: 1rem 2rem;
            font-size: 1.2rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255,68,68,0.4);
            animation: pulse-button 2s infinite;
        }

        @keyframes pulse-button {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255,68,68,0.6);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section {
            padding: 4rem 0;
            margin: 2rem 0;
        }

        .forbidden-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .forbidden-card {
            background: linear-gradient(135deg, #2d1b69, #11998e);
            padding: 2rem;
            border-radius: 15px;
            border: 2px solid #ff4444;
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease;
        }

        .forbidden-card:hover {
            transform: translateY(-5px);
        }

        .forbidden-card::before {
            content: '❌';
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 2rem;
            animation: shake 1s infinite;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }

        .forbidden-card h3 {
            color: #ff4444;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat-card {
            background: rgba(255,255,255,0.1);
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #ff4444;
            display: block;
        }

        .challenge-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 4rem 2rem;
            border-radius: 20px;
            margin: 3rem 0;
            text-align: center;
            position: relative;
        }

        .challenge-section::before {
            content: '⚠️';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 3rem;
            background: #ff4444;
            padding: 10px;
            border-radius: 50%;
        }

        .testimonial {
            background: rgba(0,0,0,0.3);
            padding: 2rem;
            border-radius: 10px;
            margin: 2rem 0;
            border-left: 4px solid #ff4444;
            font-style: italic;
        }

        .final-cta {
            background: linear-gradient(135deg, #ff4444, #cc0000);
            padding: 4rem 2rem;
            border-radius: 20px;
            text-align: center;
            margin: 3rem 0;
            position: relative;
            overflow: hidden;
        }

        .final-cta::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-conic-gradient(
                from 0deg,
                transparent 0deg,
                rgba(255,255,255,0.1) 1deg,
                transparent 2deg,
                transparent 10deg
            );
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .final-cta-content {
            position: relative;
            z-index: 1;
        }

        .heart-icon {
            color: #ff4444;
            font-size: 1.5rem;
            animation: heartbeat 1.5s ease-in-out infinite;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            14% { transform: scale(1.3); }
            28% { transform: scale(1); }
            42% { transform: scale(1.3); }
            70% { transform: scale(1); }
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .hero p { font-size: 1.2rem; }
            .forbidden-grid { grid-template-columns: 1fr; }
            .stats-container { grid-template-columns: repeat(2, 1fr); }
        }
    </style>
</head>
<body>
    <div class="hero">
        <h1>MINECRAFT HARDCORE</h1>
        <p>Uma vida. Uma chance. Sem volta. Você tem coragem?</p>
        <a href="#challenge" class="cta-button">ACEITAR O DESAFIO</a>
    </div>

    <div class="container">
        <div class="section">
            <h2 style="text-align: center; font-size: 2.5rem; margin-bottom: 2rem;">O Que Você NUNCA Mais Poderá Fazer</h2>
            
            <div class="forbidden-grid">
                <div class="forbidden-card">
                    <h3>Respawn Após a Morte</h3>
                    <p>Morreu? Game over. Não existe "tentar novamente". Seu mundo será deletado ou ficará permanentemente em modo espectador. Cada decisão importa quando não há segunda chance.</p>
                </div>
                
                <div class="forbidden-card">
                    <h3>Comandos de Trapaça</h3>
                    <p>Nada de /gamemode creative, /give ou /heal. Você está completamente por conta própria. Sem atalhos, sem facilidades, apenas sua habilidade pura.</p>
                </div>
                
                <div class="forbidden-card">
                    <h3>Pausar Durante Combate</h3>
                    <p>O jogo não pausa no menu. Se você abrir o inventário durante uma luta, os mobs continuam atacando. Cada segundo de hesitação pode ser fatal.</p>
                </div>
                
                <div class="forbidden-card">
                    <h3>Relaxar e Ser Descuidado</h3>
                    <p>Não existe "só mais um bloco" ou "vou dar uma olhadinha rápida". Cada movimento deve ser calculado. A complacência é sua maior inimiga.</p>
                </div>
                
                <div class="forbidden-card">
                    <h3>Ignorar a Fome</h3>
                    <p>Sua barra de fome pode te matar. Sem regeneração natural quando está baixa, você precisa sempre ter comida. Morrer de fome é real e definitivo.</p>
                </div>
                
                <div class="forbidden-card">
                    <h3>Explorar Sem Preparação</h3>
                    <p>Nada de "vou só dar uma olhada". Cada expedição precisa de planejamento: armadura, armas, comida, tochas. Um creeper pode acabar com horas de progresso.</p>
                </div>
            </div>
        </div>

        <div class="section">
            <h2 style="text-align: center; font-size: 2.5rem; margin-bottom: 2rem;">A Realidade Brutal</h2>
            
            <div class="stats-container">
                <div class="stat-card">
                    <span class="stat-number">73%</span>
                    <p>dos jogadores morrem nas primeiras 24 horas</p>
                </div>
                <div class="stat-card">
                    <span class="stat-number">1</span>
                    <p><span class="heart-icon">❤️</span> vida restante sempre</p>
                </div>
                <div class="stat-card">
                    <span class="stat-number">0</span>
                    <p>chances de recuperar seus itens após a morte</p>
                </div>
                <div class="stat-card">
                    <span class="stat-number">∞</span>
                    <p>adrenalina a cada som suspeito</p>
                </div>
            </div>
        </div>

        <div class="challenge-section" id="challenge">
            <div style="position: relative; z-index: 1;">
                <h2 style="font-size: 2.5rem; margin-bottom: 2rem;">Por Que Você PRECISA Tentar</h2>
                <p style="font-size: 1.3rem; margin-bottom: 2rem;">
                    Imagine a sensação de cada vitória sendo REAL. Cada estrutura construída, cada mob derrotado, cada noite sobrevivida tem um peso que você nunca sentiu antes no Minecraft.
                </p>
                <p style="font-size: 1.2rem;">
                    Quando você finalmente derrotar o Ender Dragon no Hardcore, você não será apenas mais um jogador... você será um SOBREVIVENTE.
                </p>
            </div>
        </div>

        <div class="testimonial">
            <p>"Joguei Minecraft por anos, mas só no Hardcore descobri o que é realmente JOGAR. Cada creeper me faz suar frio, cada caverna é uma aventura épica. Nunca mais consegui voltar ao modo normal." - Player veterano</p>
        </div>

        <div class="testimonial">
            <p>"Morri depois de 47 dias no meu primeiro mundo Hardcore. Chorei de verdade. Mas já criei outro mundo. O vício é real." - Streamer popular</p>
        </div>

        <div class="final-cta">
            <div class="final-cta-content">
                <h2 style="font-size: 3rem; margin-bottom: 2rem;">VOCÊ TEM CORAGEM?</h2>
                <p style="font-size: 1.4rem; margin-bottom: 2rem;">
                    Milhões de jogadores já experimentaram. Alguns se tornaram lendas. Outros... bem, outros aprenderam que não eram tão bons quanto pensavam.
                </p>
                <p style="font-size: 1.6rem; font-weight: bold; margin-bottom: 2rem;">
                    A pergunta é: Você vai ficar se perguntando "e se..." ou vai descobrir do que é capaz?
                </p>
                <button class="cta-button" onclick="startChallenge()" style="font-size: 1.4rem; padding: 1.5rem 3rem;">
                    CRIAR MUNDO HARDCORE AGORA
                </button>
                <p style="margin-top: 1rem; font-size: 0.9rem; opacity: 0.8;">
                    ⚠️ Aviso: Pode causar dependência, suor nas mãos e gritos involuntários
                </p>
            </div>
        </div>
    </div>

    <script>
        function startChallenge() {
            const messages = [
                "🔥 DESAFIO ACEITO! Abra o Minecraft e clique em 'Criar Novo Mundo'",
                "⚡ Selecione 'Hardcore' no modo de jogo",
                "💀 Lembre-se: UMA vida, UMA chance!",
                "🎯 Sua jornada épica começa AGORA!"
            ];
            
            let index = 0;
            const button = event.target;
            const originalText = button.textContent;
            
            const showMessage = () => {
                if (index < messages.length) {
                    button.textContent = messages[index];
                    button.style.background = `hsl(${Math.random() * 360}, 70%, 50%)`;
                    index++;
                    setTimeout(showMessage, 2000);
                } else {
                    button.textContent = "BOA SORTE, SOBREVIVENTE! 🏆";
                    button.style.background = "linear-gradient(45deg, #00ff00, #008800)";
                    
                    // Efeito de confete
                    createConfetti();
                }
            };
            
            showMessage();
        }
        
        function createConfetti() {
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.style.position = 'fixed';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-10px';
                confetti.style.width = '10px';
                confetti.style.height = '10px';
                confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 70%, 50%)`;
                confetti.style.pointerEvents = 'none';
                confetti.style.zIndex = '9999';
                confetti.textContent = ['🎉', '🔥', '⚡', '💀', '🏆'][Math.floor(Math.random() * 5)];
                confetti.style.fontSize = '20px';
                
                document.body.appendChild(confetti);
                
                const animation = confetti.animate([
                    { transform: 'translateY(-10px) rotate(0deg)', opacity: 1 },
                    { transform: `translateY(100vh) rotate(${Math.random() * 360}deg)`, opacity: 0 }
                ], {
                    duration: 3000 + Math.random() * 2000,
                    easing: 'cubic-bezier(0.25, 0.46, 0.45, 0.94)'
                });
                
                animation.onfinish = () => confetti.remove();
            }
        }
        
        // Efeito de scroll suave
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
        
        // Efeito de paralaxe no hero
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            hero.style.transform = `translateY(${scrolled * 0.5}px)`;
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'98a5b68966b0c20f',t:'MTc1OTc1OTUyMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
