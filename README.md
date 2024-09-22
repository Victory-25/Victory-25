- 👋 Hi, I’m @Victory-25
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Victory-25/Victory-25 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contagem Regressiva</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }
        .countdown {
            text-align: center;
        }
        .countdown h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        .countdown p {
            font-size: 36px;
        }
    </style>
</head>
<body>

    <div class="countdown">
        <h1>Contagem até o dia 27!</h1>
        <p id="timer"></p>
    </div>

    <script>
        // Define a data de destino (dia 27 do mês atual)
        let targetDate = new Date();
        targetDate.setDate(27);
        targetDate.setHours(0, 0, 0, 0);

        function updateCountdown() {
            const now = new Date();
            const timeDiff = targetDate - now;

            // Calcula os dias, horas, minutos e segundos restantes
            const days = Math.floor(timeDiff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeDiff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeDiff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeDiff % (1000 * 60)) / 1000);

            // Exibe o resultado
            document.getElementById("timer").innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;

            // Para a contagem regressiva quando atingir zero
            if (timeDiff < 0) {
                clearInterval(countdownInterval);
                document.getElementById("timer").innerHTML = "Chegou o dia!";
            }
        }

        // Atualiza a contagem a cada segundo
        const countdownInterval = setInterval(updateCountdown, 1000);
    </script>

</body>
</html>
