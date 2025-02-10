<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi San Valentín?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            overflow: hidden;
            position: relative;
        }
        h1 {
            color: #fff;
            font-size: 32px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        .button {
            padding: 15px 30px;
            font-size: 18px;
            margin: 10px;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            color: white;
            transition: transform 0.2s ease;
        }
        #si {
            background-color: #5cb85c;
        }
        #no {
            background-color: #d9534f;
            position: relative;
        }
        .heart {
            position: absolute;
            bottom: 20px; /* Posición en la parte inferior */
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 90px;
            animation: heartbeat 1.5s infinite;
        }
        .heart::before,
        .heart::after {
            content: '';
            position: absolute;
            top: 0;
            width: 52px;
            height: 80px;
            background: #ff4d4d;
            border-radius: 50px 50px 0 0;
        }
        .heart::before {
            left: 50px;
            transform: rotate(-45deg);
            transform-origin: 0 100%;
        }
        .heart::after {
            left: 0;
            transform: rotate(45deg);
            transform-origin: 100% 100%;
        }
        @keyframes heartbeat {
            0%, 100% {
                transform: translateX(-50%) scale(1);
            }
            50% {
                transform: translateX(-50%) scale(1.1);
            }
        }
    </style>
</head>
<body>

    <div>
        <h1>¿Sarita Quieres ser mi San Valentín?</h1>
        <button id="si" class="button">Sí</button>
        <button id="no" class="button">No</button>
    </div>

    <!-- Corazón animado en la parte inferior -->
    <div class="heart"></div>

    <script>
        const noButton = document.getElementById('no');

        // Función para mover el botón "No"
        const moveButton = () => {
            const x = Math.random() * (window.innerWidth - noButton.offsetWidth);
            const y = Math.random() * (window.innerHeight - noButton.offsetHeight);
            noButton.style.position = 'absolute';
            noButton.style.left = `${x}px`;
            noButton.style.top = `${y}px`;
        };

        // Evento para PC (mousedown)
        noButton.addEventListener('mousedown', (event) => {
            event.preventDefault(); // Evita que el botón se seleccione
            moveButton();
        });

        // Evento para móviles (touchstart)
        noButton.addEventListener('touchstart', (event) => {
            event.preventDefault(); // Evita el comportamiento por defecto del touch
            moveButton();
        });

        // Evento para el botón "Sí"
        document.getElementById('si').addEventListener('click', () => {
            alert('¡Yay! Gracias mi amor lindo 💖');
        });
    </script>

</body>
</html>
