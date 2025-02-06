<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta de Amor</title>
    <style>
        body {
            background: url('https://th.bing.com/th/id/R.1044c3f11db6dd80d44974089ed53f0c?rik=aQLXrsZ8DcgR6A&pid=ImgRaw&r=0') no-repeat center center/cover;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Verdana', sans-serif;
            overflow: hidden;
            margin: 0;
            position: relative;
            background-color: #f8f7f5;
        }

        .flower {
            position: absolute;
            width: 40px;
            height: 40px;
            animation: floatFlowers 6s infinite;
            z-index: 1;
        }

        @keyframes floatFlowers {
            0% {
                transform: translateY(0) rotate(0deg);
            }
            50% {
                transform: translateY(-200px) rotate(180deg);
            }
            100% {
                transform: translateY(0) rotate(360deg);
            }
        }

        .carta {
            background: rgba(255, 255, 255, 0.8);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0px 15px 30px rgba(0, 0, 0, 0.2);
            position: relative;
            max-width: 600px;
            z-index: 2;
            display: none;
            opacity: 0;
            transform: scale(0.8);
            animation: aparecer 0.8s forwards;
        }

        @keyframes aparecer {
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .boton {
            padding: 12px 30px;
            border: none;
            background: linear-gradient(45deg, #ff4e50, #f9a8d4);
            color: white;
            font-size: 20px;
            border-radius: 12px;
            cursor: pointer;
            margin: 10px;
            transition: 0.3s;
            box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
        }

        .boton:hover {
            background: linear-gradient(45deg, #f9a8d4, #ff4e50);
            transform: translateY(-3px);
        }

        .corazon {
            color: red;
            font-size: 40px;
            animation: flotar 1.5s infinite alternate;
        }

        @keyframes flotar {
            from {
                transform: translateY(0);
            }

            to {
                transform: translateY(-15px);
            }
        }

        .corazon-flotante {
            position: absolute;
            color: red;
            font-size: 30px;
            animation: subir 3s linear forwards;
        }

        @keyframes subir {
            from {
                transform: translateY(100vh);
                opacity: 1;
            }

            to {
                transform: translateY(-10vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <audio id="musica" autoplay loop>
        <source src="tu_archivo_audio.mp3" type="audio/mp3">
    </audio>

    <!-- Corazones flotantes animados con la nueva imagen -->
    <img class="flower" src="https://emoji-terra.com/wp-content/uploads/2020/12/%F0%9F%92%99-%F0%9F%92%99-coraz%C3%B3n-negro.png" alt="Corazón negro" style="left: 10%; animation-duration: 6s;"/>
    <img class="flower" src="https://emoji-terra.com/wp-content/uploads/2020/12/%F0%9F%92%99-%F0%9F%92%99-coraz%C3%B3n-negro.png" alt="Corazón negro" style="left: 25%; animation-duration: 7s;"/>
    <img class="flower" src="https://emoji-terra.com/wp-content/uploads/2020/12/%F0%9F%92%99-%F0%9F%92%99-coraz%C3%B3n-negro.png" alt="Corazón negro" style="left: 50%; animation-duration: 8s;"/>
    <img class="flower" src="https://emoji-terra.com/wp-content/uploads/2020/12/%F0%9F%92%99-%F0%9F%92%99-coraz%C3%B3n-negro.png" alt="Corazón negro" style="left: 75%; animation-duration: 6.5s;"/>
    <img class="flower" src="https://emoji-terra.com/wp-content/uploads/2020/12/%F0%9F%92%99-%F0%9F%92%99-coraz%C3%B3n-negro.png" alt="Corazón negro" style="left: 90%; animation-duration: 7.5s;"/>

    <button class="boton" onclick="abrirCarta()">💌 Abrir Carta</button>
    <div class="carta" id="carta">
        <h2>Para el amor de mi vida ❤️</h2>
        <p id="mensaje">Desde el primer momento en que nuestras miradas se cruzaron, supe que mi vida cambiaría para siempre.</p>
        <p class="corazon">❤️</p>
        <button class="boton" onclick="siguienteMensaje()">💖 Siguiente Mensaje</button>
        <button class="boton" onclick="cerrarCarta()">❌ Cerrar Carta</button>
    </div>
    
    <script>
        const mensajes = [
            "Desde el primer momento en que nuestras miradas se cruzaron, supe que mi vida cambiaría para siempre.",
            "Cada día contigo es una nueva razón para sonreír, para amar más profundo y para ser feliz.",
            "Eres mi sol en los días nublados, mi refugio, mi paz, mi hogar. Todo lo que necesito lo encuentro en ti.",
            "Tu amor es el viento que hace que mis sueños vuelen alto, y tu sonrisa la razón por la que mi corazón late fuerte.",
            "A tu lado soy la mejor versión de mí mismo, porque me das fuerza, amor y razón para ser feliz.",
            "Quiero envejecer contigo, recorrer este viaje llamado vida, porque a tu lado todo tiene sentido.",
            "No te imaginas lo afortunado que me siento por haberte encontrado, por amarte y por ser amado por ti.",
            "Cada instante contigo es un regalo, y todo lo que quiero es que este amor sea eterno.",
            "¿Te casarías conmigo? 💍 Juntos por siempre, ¿te parece bien?"
        ];
        
        let index = 0;
        let musica = document.getElementById("musica");

        function abrirCarta() {
            const carta = document.getElementById("carta");
            carta.style.display = "block";
            carta.style.opacity = 1;
            carta.style.transform = "scale(1)";
            document.getElementById("mensaje").innerText = mensajes[index];
            musica.play();
        }

        function cerrarCarta() {
            const carta = document.getElementById("carta");
            carta.style.opacity = 0;
            carta.style.transform = "scale(0.8)";
            setTimeout(() => {
                carta.style.display = "none";
            }, 800);  // Tiempo de la animación de cierre
            musica.pause();
        }

        function siguienteMensaje() {
            index = (index + 1) % mensajes.length;
            document.getElementById("mensaje").innerText = mensajes[index];
        }

        setInterval(() => {
            let corazon = document.createElement("div");
            corazon.innerHTML = "❤️";
            corazon.classList.add("corazon-flotante");
            corazon.style.left = Math.random() * window.innerWidth + "px";
            corazon.style.top = "100vh";
            document.body.appendChild(corazon);

            setTimeout(() => {
                corazon.remove();
            }, 3000);
        }, 500);
    </script>
</body>
</html>
