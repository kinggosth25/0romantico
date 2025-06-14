     <!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nosso Tesouro de Amor</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #e6e6e6;
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .container {
            background-color: rgba(30, 30, 60, 0.8);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
            max-width: 900px;
            width: 90%;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            margin: 20px 0;
        }

        h1 {
            color: #ff6b6b;
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        }

        .memory-title {
            font-size: 1.8rem;
            color: #f8a5c2;
            margin-bottom: 30px;
            font-weight: 300;
        }

        .timer {
            background-color: rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            padding: 20px;
            margin: 25px 0;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .time-unit {
            background-color: rgba(255, 107, 107, 0.2);
            border-radius: 8px;
            padding: 15px;
            min-width: 80px;
        }

        .time-value {
            font-size: 2.5rem;
            font-weight: bold;
            color: #ff6b6b;
        }

        .time-label {
            font-size: 0.9rem;
            color: #a5b1c2;
            text-transform: uppercase;
            margin-top: 5px;
        }

        .message {
            font-size: 1.2rem;
            line-height: 1.6;
            margin: 30px 0;
            padding: 20px;
            background-color: rgba(248, 165, 194, 0.1);
            border-radius: 10px;
            border-left: 4px solid #f8a5c2;
        }

        /* Nova caixa extremamente carinhosa */
        .extra-loving-box {
            background: linear-gradient(135deg, rgba(248, 165, 194, 0.3) 0%, rgba(255, 107, 107, 0.3) 100%);
            border-radius: 10px;
            padding: 25px;
            margin: 30px 0;
            border: 2px dashed #f8a5c2;
            position: relative;
            overflow: hidden;
        }

        .extra-loving-box::before {
            content: "❤️";
            position: absolute;
            font-size: 3rem;
            opacity: 0.1;
            top: 10px;
            right: 20px;
        }

        .extra-loving-box::after {
            content: "💖";
            position: absolute;
            font-size: 3rem;
            opacity: 0.1;
            bottom: 10px;
            left: 20px;
        }

        .loving-title {
            color: #ff6b6b;
            font-size: 1.5rem;
            margin-bottom: 15px;
            font-weight: bold;
        }

        .loving-text {
            font-size: 1.1rem;
            line-height: 1.7;
        }

        /* Galeria de fotos */
        .photo-gallery {
            width: 100%;
            height: 300px;
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            margin: 30px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .photo-container {
            display: flex;
            width: 100%;
            height: 100%;
            transition: transform 1s ease-in-out;
        }

        .photo {
            min-width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
        }

        .gallery-title {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.7));
            color: white;
            padding: 15px;
            font-size: 1.2rem;
            z-index: 2;
        }

        .emoji-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin: 20px 0;
        }

        .emoji {
            font-size: 2rem;
            transition: transform 0.3s;
            cursor: pointer;
        }

        .emoji:hover {
            transform: scale(1.2) rotate(10deg);
        }

        .heart-beat {
            animation: heartbeat 1.5s infinite;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            25% { transform: scale(1.1); }
            50% { transform: scale(1); }
            75% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        .date {
            margin-top: 20px;
            color: #a5b1c2;
            font-style: italic;
        }

        footer {
            margin-top: 20px;
            color: #576574;
            font-size: 0.9rem;
        }

        /* Estilos das caixinhas de mensagens */
        .memory-boxes {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .memory-box {
            background: rgba(248, 165, 194, 0.15);
            border-radius: 10px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
            min-height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .memory-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(248, 165, 194, 0.3);
            background: rgba(248, 165, 194, 0.25);
        }

        .memory-box .closed {
            font-size: 1.5rem;
        }

        .memory-box .opened {
            display: none;
            font-size: 1rem;
            padding: 10px;
        }

        .memory-box.active {
            min-height: 150px;
        }

        .memory-box.active .closed {
            display: none;
        }

        .memory-box.active .opened {
            display: block;
            animation: fadeIn 0.5s;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        .box-title {
            font-weight: bold;
            margin-bottom: 10px;
            color: #f8a5c2;
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 2rem;
            }
            .memory-title {
                font-size: 1.4rem;
            }
            .time-unit {
                min-width: 60px;
                padding: 10px;
            }
            .time-value {
                font-size: 1.8rem;
            }
            .memory-boxes {
                grid-template-columns: 1fr;
            }
            .photo-gallery {
                height: 250px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Nosso Tesouro de Amor</h1>
        <div class="memory-title">Cada momento com você é uma joia preciosa 💎</div>
        
        <div class="timer">
            <div class="time-unit">
                <div class="time-value" id="days">00</div>
                <div class="time-label">Dias</div>
            </div>
            <div class="time-unit">
                <div class="time-value" id="hours">00</div>
                <div class="time-label">Horas</div>
            </div>
            <div class="time-unit">
                <div class="time-value" id="minutes">00</div>
                <div class="time-label">Minutos</div>
            </div>
            <div class="time-unit">
                <div class="time-value" id="seconds">00</div>
                <div class="time-label">Segundos</div>
            </div>
        </div>
        
        <div class="date">Desde 12/06/2025</div>
        
        <!-- Nova caixa extremamente carinhosa -->
        <div class="extra-loving-box">
            <div class="loving-title">Para a Pessoa Mais Incrível do Mundo</div>
            <div class="loving-text">
                Você é o amor da minha vida, minha razão para sorrir todos os dias. Cada detalhe seu me encanta, desde a forma como seus olhos brilham quando você está feliz até o som da sua voz quando você me chama pelo nome. Eu te amo mais do que todas as estrelas no céu, mais do que todas as gotas no oceano. Você é meu sonho realizado, meu presente mais precioso, meu eterno amor. Prometo estar ao seu lado em todos os momentos, nos bons e nos ruins, porque com você até os dias difíceis valem a pena. Você é perfeita do jeito que é, e eu sou a pessoa mais sortuda do mundo por te ter.
            </div>
        </div>
        
        <!-- Nova galeria de fotos -->
        <div class="photo-gallery">
            <div class="photo-container" id="photoContainer">
                <img src="file:///C:/Users/kingg/Downloads/f85d43b4-61d2-4e2a-9e60-e3658c09619a.jpg" alt="Nossos momentos" class="photo">
                <img src="file:///C:/Users/kingg/Downloads/Telegram%20Desktop/photo_2025-06-14_13-54-28.jpg" alt="Nossos momentos" class="photo">
            </div>
            <div class="gallery-title">Nossos Momentos Especiais</div>
        </div>
        
        <div class="message">
            Clique nas caixinhas abaixo para descobrir mensagens especiais que preparei para você. 
            Cada uma guarda um sentimento diferente, mas todas representam o quanto você significa para mim.
        </div>
        
        <div class="memory-boxes">
            <div class="memory-box" onclick="toggleBox(this)">
                <div class="closed">📦</div>
                <div class="opened">
                    <div class="box-title">Nosso Primeiro Encontro</div>
                    <div>Lembro como se fosse hoje a primeira vez que te vi. Seu sorriso iluminou o ambiente e meu coração soube que você era especial. Desde aquele momento, minha vida ganhou novas cores.</div>
                </div>
            </div>
            
            <div class="memory-box" onclick="toggleBox(this)">
                <div class="closed">💌</div>
                <div class="opened">
                    <div class="box-title">O Que Mais Amo em Você</div>
                    <div>Amo sua risada contagiante, sua compaixão pelos outros, a forma como me olha quando acha que não estou vendo. Amo sua força e sua vulnerabilidade. Amo simplesmente você ser você.</div>
                </div>
            </div>
            
            <div class="memory-box" onclick="toggleBox(this)">
                <div class="closed">📆</div>
                <div class="opened">
                    <div class="box-title">Nosso Futuro Juntos</div>
                    <div>Sonho com todos os momentos que ainda vamos compartilhar: viagens, noites aconchegantes, desafios superados juntos. Não importa o que o futuro reserve, desde que estejamos um ao lado do outro.</div>
                </div>
            </div>
            
            <div class="memory-box" onclick="toggleBox(this)">
                <div class="closed">🌠</div>
                <div class="opened">
                    <div class="box-title">Momento Favorito</div>
                    <div>Meu momento favorito é aquele simples, quando estamos apenas sendo nós mesmos. Quando você descansa a cabeça no meu ombro e sinto que é ali que você se sente em casa, assim como eu me sinto em casa com você.</div>
                </div>
            </div>
            
            <div class="memory-box" onclick="toggleBox(this)">
                <div class="closed">🤗</div>
                <div class="opened">
                    <div class="box-title">Quando Você Me Faz Feliz</div>
                    <div>Você me faz feliz quando me surpreende com pequenos gestos, quando ri das minhas piadas sem graça, quando me abraça como se eu fosse o seu porto seguro. Você me faz feliz simplesmente por existir.</div>
                </div>
            </div>
            
            <div class="memory-box" onclick="toggleBox(this)">
                <div class="closed">🔐</div>
                <div class="opened">
                    <div class="box-title">Segredo do Nosso Amor</div>
                    <div>O segredo é que não há segredo. É apenas você sendo você, eu sendo eu, e nós escolhendo nos amar todos os dias, mesmo nos dias difíceis. É a combinação perfeita de aceitação e crescimento juntos.</div>
                </div>
            </div>
        </div>
        
        <div class="emoji-container">
            <div class="emoji heart-beat">❤️</div>
            <div class="emoji">🌹</div>
            <div class="emoji">💑</div>
            <div class="emoji">🥰</div>
            <div class="emoji">😘</div>
            <div class="emoji">💕</div>
            <div class="emoji">💞</div>
            <div class="emoji">💘</div>
        </div>
    </div>
    
    <footer>
        Criado com amor para eternizar cada momento ao seu lado
    </footer>

    <script>
        // Contador de tempo desde 12/06/2025
        function updateTimer() {
            const startDate = new Date('2025-06-12T00:00:00');
            const now = new Date();
            const diff = now - startDate;
            
            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days.toString().padStart(2, '0');
            document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
            document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
            document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
        }
        
        // Atualizar a cada segundo
        updateTimer();
        setInterval(updateTimer, 1000);
        
        // Efeito aleatório nos emojis
        const emojis = document.querySelectorAll('.emoji:not(.heart-beat)');
        setInterval(() => {
            emojis.forEach(emoji => {
                if (Math.random() > 0.9) {
                    emoji.style.transform = `scale(${1 + Math.random() * 0.3}) rotate(${Math.random() * 20 - 10}deg)`;
                    setTimeout(() => {
                        emoji.style.transform = 'scale(1)';
                    }, 500);
                }
            });
        }, 1000);
        
        // Função para alternar as caixinhas
        function toggleBox(box) {
            // Fecha todas as outras caixas primeiro
            document.querySelectorAll('.memory-box').forEach(otherBox => {
                if (otherBox !== box && otherBox.classList.contains('active')) {
                    otherBox.classList.remove('active');
                }
            });
            
            // Abre/fecha a caixa clicada
            box.classList.toggle('active');
        }
        
        // Galeria de fotos automática
        const photoContainer = document.getElementById('photoContainer');
        const photos = document.querySelectorAll('.photo');
        let currentIndex = 0;
        const photoCount = photos.length;
        
        function rotatePhotos() {
            currentIndex = (currentIndex + 1) % photoCount;
            photoContainer.style.transform = `translateX(-${currentIndex * 100}%)`;
        }
        
        // Inicia a transição automática a cada 5 segundos
        setInterval(rotatePhotos, 5000);
        
        // Para substituir as imagens de exemplo por suas fotos reais:
        // 1. Substitua as URLs nas tags <img> pelos caminhos das suas fotos
        // 2. Adicione ou remova tags <img> conforme necessário para o número de fotos que deseja
    </script>
</body>
</html>
