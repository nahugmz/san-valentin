# dia de los enamorados 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>San Valentín 💖</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background: linear-gradient(to bottom, #ffe6f2, #ffb6c1);
            color: #d63384;
            padding: 40px 20px;
            overflow: hidden;
        }

        h1 {
            font-size: 26px;
        }

        #buttons {
            margin-top: 30px;
        }

        button {
            padding: 14px 24px;
            font-size: 18px;
            margin: 12px;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #yes {
            background-color: #ff69b4;
            color: white;
        }

        #no {
            background-color: #ddd;
            color: black;
        }

        #invitation {
            display: none;
            font-size: 22px;
            margin-top: 30px;
            background-color: white;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 0 15px rgba(0,0,0,0.15);
            animation: fadeIn 1s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        /* Corazones */
        .heart {
            position: fixed;
            bottom: -20px;
            font-size: 24px;
            animation: floatUp 6s linear infinite;
            opacity: 0.7;
        }

        @keyframes floatUp {
            from {
                transform: translateY(0);
                opacity: 1;
            }
            to {
                transform: translateY(-110vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1>¿Malena, quieres ser mi pareja este San Valentín? 💕</h1>

    <div id="buttons">
        <button id="yes">Sí 💖</button>
        <button id="no">No 🙈</button>
    </div>

    <div id="invitation">
        <p>🌹 Cita el 14 de febrero a las 22:00 🌹</p>
        <p>Vestirse elegante ✨</p>
        <p><strong>Te amo, Malena ❤️</strong></p>
    </div>

    <script>
        let yesSize = 1;
        let noClicks = 0;

        document.getElementById('no').addEventListener('click', () => {
            noClicks++;
            yesSize += 0.4;

            const yesBtn = document.getElementById('yes');
            yesBtn.style.transform = `scale(${yesSize})`;

            const noBtn = document.getElementById('no');
            const x = Math.random() * 200 - 100;
            const y = Math.random() * 200 - 100;
            noBtn.style.transform = `translate(${x}px, ${y}px)`;

            if (noClicks > 5) {
                noBtn.style.opacity = "0";
                noBtn.style.pointerEvents = "none";
            }
        });

        document.getElementById('yes').addEventListener('click', () => {
            document.getElementById('buttons').style.display = "none";
            document.getElementById('invitation').style.display = "block";
        });

        // Crear corazones flotando
        setInterval(() => {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.fontSize = (20 + Math.random() * 20) + "px";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 6000);
        }, 500);
    </script>

</body>
</html>