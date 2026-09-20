<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Ti ❤️</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #ffeef8 0%, #ffd6e7 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            color: #4a4a4a;
        }

        .card-container {
            background: #ffffff;
            border-radius: 24px;
            padding: 30px 24px;
            max-width: 480px;
            width: 100%;
            box-shadow: 0 12px 30px rgba(233, 30, 99, 0.12);
            border: 2px solid #ffb6c1;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .step-page {
            display: none;
            animation: fadeIn 0.4s ease-in-out;
        }

        .step-page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Títulos y textos */
        h1 {
            color: #d81b60;
            font-size: 1.8rem;
            margin-bottom: 15px;
            font-weight: 700;
        }

        h2 {
            color: #e91e63;
            font-size: 1.3rem;
            margin-bottom: 12px;
        }

        p {
            line-height: 1.6;
            color: #555;
            font-size: 1rem;
            margin-bottom: 16px;
            text-align: left;
        }

        /* Botones */
        .btn-pink {
            background: linear-gradient(45deg, #e91e63, #ff4081);
            color: white;
            border: none;
            padding: 14px 28px;
            font-size: 1.05rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(233, 30, 99, 0.3);
            transition: all 0.3s ease;
            display: inline-block;
            margin-top: 15px;
            width: 100%;
        }

        .btn-pink:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(233, 30, 99, 0.4);
        }

        .btn-secondary {
            background: #f8bbd0;
            color: #880e4f;
            border: none;
            padding: 10px 20px;
            font-size: 0.95rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.2s;
        }

        /* Recuerdos (Paso 2) */
        .memory-media {
            width: 100%;
            height: 240px;
            border-radius: 16px;
            object-fit: cover;
            margin-bottom: 15px;
            border: 2px solid #f8bbd0;
        }

        .nav-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
            gap: 10px;
        }

        .counter {
            font-size: 0.85rem;
            color: #ad1457;
            font-weight: 600;
        }

        /* Juego (Paso 3) */
        .game-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin: 20px 0;
        }

        .game-card {
            background: #ffe4e8;
            border: 2px dashed #f48fb1;
            border-radius: 16px;
            padding: 20px 10px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: bold;
            color: #c2185b;
            min-height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .game-card.revealed {
            background: #fff;
            border-style: solid;
            border-color: #e91e63;
            color: #444;
            font-weight: normal;
            font-size: 0.9rem;
        }

        /* Corazones flotantes */
        .floating-heart {
            position: absolute;
            font-size: 20px;
            animation: floatUp 2s ease-out forwards;
            pointer-events: none;
        }

        @keyframes floatUp {
            0% { opacity: 1; transform: translateY(0) scale(1); }
            100% { opacity: 0; transform: translateY(-100px) scale(1.5); }
        }
    </style>
</head>
<body>

    <div class="card-container">

        <!-- PASO 1: Bienvenida -->
        <div id="step-1" class="step-page active">
            <div style="font-size: 60px; margin-bottom: 10px;">💖</div>
            <h1>¡Olaa Amor!</h1>
            <p style="text-align: center; margin-bottom: 25px;">
                Prepara un momento tranquilo y presiona el botón para continuar.
            </p>
            <button class="btn-pink" onclick="goToStep(2)">Sigue 💖</button>
        </div>

        <!-- PASO 2: Recuerdos (1 por página) -->
        <div id="step-2" class="step-page">
            <h2>Nuestros Momentos 💕</h2>
            
            <!-- Recuerdo 1 -->
            <div id="memory-1" class="memory-item">
                <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?auto=format&fit=crop&w=600&q=80" class="memory-media" alt="Foto 1">
                <p><strong>Recuerdo 1:</strong> [EDITA AQUÍ TU TEXTO PARA LA FOTO 1]</p>
            </div>

            <!-- Recuerdo 2 -->
            <div id="memory-2" class="memory-item" style="display: none;">
                <img src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?auto=format&fit=crop&w=600&q=80" class="memory-media" alt="Foto 2">
                <p><strong>Recuerdo 2:</strong> [EDITA AQUÍ TU TEXTO PARA LA FOTO 2]</p>
            </div>

            <!-- Recuerdo 3 -->
            <div id="memory-3" class="memory-item" style="display: none;">
                <img src="https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=600&q=80" class="memory-media" alt="Foto 3">
                <p><strong>Recuerdo 3:</strong> [EDITA AQUÍ TU TEXTO PARA LA FOTO 3]</p>
            </div>

            <!-- Recuerdo 4 -->
            <div id="memory-4" class="memory-item" style="display: none;">
                <img src="https://images.unsplash.com/photo-1494774157365-9e04c6720e47?auto=format&fit=crop&w=600&q=80" class="memory-media" alt="Foto 4">
                <p><strong>Recuerdo 4:</strong> [EDITA AQUÍ TU TEXTO PARA LA FOTO 4]</p>
            </div>

            <!-- Recuerdo 5 -->
            <div id="memory-5" class="memory-item" style="display: none;">
                <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=600&q=80" class="memory-media" alt="Foto 5">
                <p><strong>Recuerdo 5:</strong> [EDITA AQUÍ TU TEXTO PARA LA FOTO 5]</p>
            </div>

            <!-- Recuerdo 6 -->
            <div id="memory-6" class="memory-item" style="display: none;">
                <img src="https://images.unsplash.com/photo-1529156069898-49953e39b3ac?auto=format&fit=crop&w=600&q=80" class="memory-media" alt="Foto 6">
                <p><strong>Recuerdo 6:</strong> [EDITA AQUÍ TU TEXTO PARA LA FOTO 6]</p>
            </div>

            <!-- Controles de navegación de recuerdos -->
            <div class="nav-controls">
                <button class="btn-secondary" onclick="changeMemory(-1)">Anterior</button>
                <span class="counter" id="memory-counter">1 / 6</span>
                <button class="btn-secondary" onclick="changeMemory(1)">Siguiente</button>
            </div>

            <button class="btn-pink" onclick="goToStep(3)" style="margin-top: 20px;">Sí, sigue ✨</button>
        </div>

        <!-- PASO 3: Juego interactivo -->
        <div id="step-3" class="step-page">
            <h2>Descubre los mensajes 🎁</h2>
            <p style="text-align: center; font-size: 0.9rem;">Haz clic en cada tarjeta para descubrir la sorpresa:</p>
            
            <div class="game-grid">
                <div class="game-card" onclick="revealCard(this, '[EDITA TEXTO TARJETA 1]')">
                    <span>Haz clic aquí ✨</span>
                </div>
                <div class="game-card" onclick="revealCard(this, '[EDITA TEXTO TARJETA 2]')">
                    <span>Haz clic aquí 💕</span>
                </div>
                <div class="game-card" onclick="revealCard(this, '[EDITA TEXTO TARJETA 3]')">
                    <span>Haz clic aquí 🌸</span>
                </div>
                <div class="game-card" onclick="revealCard(this, '[EDITA TEXTO TARJETA 4]')">
                    <span>Haz clic aquí 💗</span>
                </div>
            </div>

            <button class="btn-pink" onclick="goToStep(4)">Continuar a la carta final 💌</button>
        </div>

        <!-- PASO 4: Carta Final -->
        <div id="step-4" class="step-page">
            <div style="font-size: 50px; margin-bottom: 10px;">💌</div>
            <h2>Para Ti</h2>
            
            <p>Hola,</p>
            <p>[EDITA AQUÍ TU PARRAFO 1: Dile lo mucho que la aprecias y que no quieres que se sienta presionada].</p>
            <p>[EDITA AQUÍ TU PARRAFO 2: Recuérdale que para ti siempre ha sido más que suficiente].</p>
            <p>[EDITA AQUÍ TU PARRAFO 3: Déjale saber que cuenta contigo y que le das su espacio].</p>
            
            <p style="text-align: center; font-style: italic; color: #ad1457; margin-top: 20px;">
                [EDITA TU DESPEDIDA. Ej: Con mucho cariño, siempre.]
            </p>
        </div>

    </div>

    <script>
        // Navegación entre pasos
        function goToStep(stepNumber) {
            document.querySelectorAll('.step-page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById('step-' + stepNumber).classList.add('active');
            window.scrollTo(0, 0);
        }

        // Navegación entre recuerdos
        let currentMemory = 1;
        const totalMemories = 6;

        function changeMemory(direction) {
            document.getElementById('memory-' + currentMemory).style.display = 'none';
            currentMemory += direction;

            if (currentMemory < 1) currentMemory = totalMemories;
            if (currentMemory > totalMemories) currentMemory = 1;

            document.getElementById('memory-' + currentMemory).style.display = 'block';
            document.getElementById('memory-counter').innerText = `${currentMemory} / ${totalMemories}`;
        }

        // Revelar tarjeta del juego
        function revealCard(element, text) {
            if (!element.classList.contains('revealed')) {
                element.classList.add('revealed');
                element.innerHTML = text;
                createHearts(element);
            }
        }

        // Animación de corazones al hacer clic
        function createHearts(target) {
            for (let i = 0; i < 5; i++) {
                const heart = document.createElement('div');
                heart.classList.add('floating-heart');
                heart.innerText = '💖';
                heart.style.left = (target.offsetLeft + Math.random() * target.offsetWidth) + 'px';
                heart.style.top = target.offsetTop + 'px';
                document.querySelector('.card-container').appendChild(heart);

                setTimeout(() => heart.remove(), 2000);
            }
        }
    </script>
</body>
</html>
