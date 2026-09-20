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

        .main-wrapper {
            width: 100%;
            max-width: 500px;
            margin: 0 auto;
            text-align: center;
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

        /* Títulos y Textos */
        h1 {
            color: #d81b60;
            font-size: 2.2rem;
            margin-bottom: 20px;
            font-weight: 700;
        }

        h2 {
            color: #e91e63;
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        p {
            line-height: 1.6;
            color: #444;
            font-size: 1.05rem;
            margin-bottom: 20px;
            text-align: left;
        }

        /* Botones */
        .btn-pink {
            background: linear-gradient(45deg, #e91e63, #ff4081);
            color: white;
            border: none;
            padding: 16px 32px;
            font-size: 1.1rem;
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

        /* Multimedia */
        .media-container {
            width: 100%;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(233, 30, 99, 0.15);
            margin-bottom: 20px;
            border: 3px solid #fff;
        }

        .media-container img, .media-container video {
            width: 100%;
            height: 320px;
            object-fit: cover;
            display: block;
        }

        /* Regalitos en movimiento (Paso Juego) */
        .moving-area {
            position: relative;
            height: 380px;
            margin: 20px 0;
            overflow: hidden;
        }

        .floating-gift {
            position: absolute;
            background: #ffffff;
            border: 2px solid #f48fb1;
            border-radius: 20px;
            padding: 15px;
            width: 80%;
            left: 10%;
            cursor: pointer;
            box-shadow: 0 6px 15px rgba(233, 30, 99, 0.15);
            transition: all 0.3s;
            text-align: center;
        }

        .floating-gift.revealed {
            animation: none !important;
            background: #fff0f5;
            border-color: #e91e63;
        }

        /* Animaciones para flotar horizontalmente */
        @keyframes floatLeftRight1 {
            0%, 100% { transform: translateX(-20px); }
            50% { transform: translateX(20px); }
        }

        @keyframes floatLeftRight2 {
            0%, 100% { transform: translateX(25px); }
            50% { transform: translateX(-25px); }
        }

        .gift-1 { top: 10px; animation: floatLeftRight1 3.5s ease-in-out infinite; }
        .gift-2 { top: 100px; animation: floatLeftRight2 4s ease-in-out infinite; }
        .gift-3 { top: 190px; animation: floatLeftRight1 3.8s ease-in-out infinite; }
        .gift-4 { top: 280px; animation: floatLeftRight2 4.2s ease-in-out infinite; }

        .gift-title {
            font-weight: bold;
            color: #d81b60;
            font-size: 1rem;
        }

        .gift-text {
            display: none;
            color: #444;
            font-size: 0.95rem;
            margin-top: 8px;
        }
    </style>
</head>
<body>

    <div class="main-wrapper">

        <!-- PASO 1: Bienvenida -->
        <div id="step-1" class="step-page active">
            <div style="font-size: 80px; margin-bottom: 15px;">💖</div>
            <h1>¡Olaa Amor!</h1>
            <p style="text-align: center; margin-bottom: 30px;">
                Prepara un momento tranquilo y machuca el botón para continuar.
            </p>
            <button class="btn-pink" onclick="goToStep(2)">Sigue 💖</button>
        </div>

        <!-- PASO 2: Recuerdo 1 (Foto 1) -->
        <div id="step-2" class="step-page">
            <h2>Nuestros Momentos 💕</h2>
            <div class="media-container">
                <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?auto=format&fit=crop&w=600&q=80" alt="Foto 1">
            </div>
            <p><strong>Lo que sentí este día:</strong> [EDITA AQUÍ TU TEXTO DE LO QUE SENTISTE CON ESTA FOTO]</p>
            <button class="btn-pink" onclick="goToStep(3)">Siguiente recuerdo ➔</button>
        </div>

        <!-- PASO 3: Recuerdo 2 (Foto 2) -->
        <div id="step-3" class="step-page">
            <h2>Nuestros Momentos 💕</h2>
            <div class="media-container">
                <img src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?auto=format&fit=crop&w=600&q=80" alt="Foto 2">
            </div>
            <p><strong>Lo que sentí este día:</strong> [EDITA AQUÍ TU TEXTO DE LO QUE SENTISTE CON ESTA FOTO]</p>
            <button class="btn-pink" onclick="goToStep(4)">Siguiente recuerdo ➔</button>
        </div>

        <!-- PASO 4: Recuerdo 3 (Video 1) -->
        <div id="step-4" class="step-page">
            <h2>Nuestros Momentos 💕</h2>
            <div class="media-container">
                <video controls poster="https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=600&q=80">
                    <source src="TU_VIDEO_1.mp4" type="video/mp4">
                    Tu navegador no soporta videos.
                </video>
            </div>
            <p><strong>Lo que sentí este día:</strong> [EDITA AQUÍ TU TEXTO DE LO QUE SENTISTE CON ESTE VIDEO]</p>
            <button class="btn-pink" onclick="goToStep(5)">Siguiente recuerdo ➔</button>
        </div>

        <!-- PASO 5: Recuerdo 4 (Video 2) -->
        <div id="step-5" class="step-page">
            <h2>Nuestros Momentos 💕</h2>
            <div class="media-container">
                <video controls poster="https://images.unsplash.com/photo-1494774157365-9e04c6720e47?auto=format&fit=crop&w=600&q=80">
                    <source src="TU_VIDEO_2.mp4" type="video/mp4">
                    Tu navegador no soporta videos.
                </video>
            </div>
            <p><strong>Lo que sentí este día:</strong> [EDITA AQUÍ TU TEXTO DE LO QUE SENTISTE CON ESTE VIDEO]</p>
            <button class="btn-pink" onclick="goToStep(6)">Siguiente recuerdo ➔</button>
        </div>

        <!-- PASO 6: Recuerdo 5 (Video 3) -->
        <div id="step-6" class="step-page">
            <h2>Nuestros Momentos 💕</h2>
            <div class="media-container">
                <video controls poster="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=600&q=80">
                    <source src="TU_VIDEO_3.mp4" type="video/mp4">
                    Tu navegador no soporta videos.
                </video>
            </div>
            <p><strong>Lo que sentí este día:</strong> [EDITA AQUÍ TU TEXTO DE LO QUE SENTISTE CON ESTE VIDEO]</p>
            
            <!-- Botón especial después de los recuerdos -->
            <button class="btn-pink" onclick="goToStep(7)" style="margin-top: 25px; background: linear-gradient(45deg, #d81b60, #ff1744);">
                Si Amor sigue ✨
            </button>
        </div>

        <!-- PASO 7: Juego interactivo (Regalitos en movimiento) -->
        <div id="step-7" class="step-page">
            <h2>Toca un regalito 🎁</h2>
            <p style="text-align: center; font-size: 0.95rem; margin-bottom: 10px;">
                Toca los detalles en movimiento para detenerlos y leerlos:
            </p>

            <div class="moving-area">
                <div class="floating-gift gift-1" onclick="revealGift(this)">
                    <span class="gift-title">Un detalle para ti ✨</span>
                    <div class="gift-text">[EDITA AQUÍ EL MENSAJE DEL REGALO 1]</div>
                </div>

                <div class="floating-gift gift-2" onclick="revealGift(this)">
                    <span class="gift-title">Algo importante 💕</span>
                    <div class="gift-text">[EDITA AQUÍ EL MENSAJE DEL REGALO 2]</div>
                </div>

                <div class="floating-gift gift-3" onclick="revealGift(this)">
                    <span class="gift-title">Para que lo recuerdes 🌸</span>
                    <div class="gift-text">[EDITA AQUÍ EL MENSAJE DEL REGALO 3]</div>
                </div>

                <div class="floating-gift gift-4" onclick="revealGift(this)">
                    <span class="gift-title">Con todo mi corazón 💗</span>
                    <div class="gift-text">[EDITA AQUÍ EL MENSAJE DEL REGALO 4]</div>
                </div>
            </div>

            <button class="btn-pink" onclick="goToStep(8)">Continuar a la carta final 💌</button>
        </div>

        <!-- PASO 8: Carta Final -->
        <div id="step-8" class="step-page">
            <div style="font-size: 60px; margin-bottom: 15px;">💌</div>
            <h2>Para Ti</h2>
            
            <p>Hola,</p>
            <p>[EDITA AQUÍ TU PÁRRAFO 1: Expresa lo mucho que significa para ti y tus sentimientos sinceros].</p>
            <p>[EDITA AQUÍ TU PÁRRAFO 2: Recuérdale que para ti ella siempre ha sido más que suficiente].</p>
            <p>[EDITA AQUÍ TU PÁRRAFO 3: Déjale saber que cuenta contigo sin presiones y a su propio tiempo].</p>
            
            <p style="text-align: center; font-style: italic; color: #ad1457; margin-top: 30px; font-weight: 600;">
                [EDITA TU DESPEDIDA. Ej: Con mucho cariño, siempre.]
            </p>
        </div>

    </div>

    <script>
        // Cambiar entre páginas
        function goToStep(stepNumber) {
            document.querySelectorAll('.step-page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById('step-' + stepNumber).classList.add('active');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Detener animación y revelar regalo al tocar
        function revealGift(element) {
            if (!element.classList.contains('revealed')) {
                element.classList.add('revealed');
                const giftText = element.querySelector('.gift-text');
                giftText.style.display = 'block';
            }
        }
    </script>
</body>
</html>
