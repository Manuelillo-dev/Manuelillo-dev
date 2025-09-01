
# 👋 ¡Hola! Soy Manuel Ramírez

[![Gmail Badge](https://img.shields.io/badge/Gmail-EA4335.svg?style=for-the-badge&logo=Gmail&logoColor=white)](mailto:manuel.raamirez03@gmail.com)
[![Business Badge](https://img.shields.io/badge/Business-0078D4.svg?style=for-the-badge&logo=Microsoft&logoColor=white)](mailto:manuel.ramirez@compucloud.com.mx)
[![LinkedIn Badge](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/manuelramírez-mich)

Soy estudiante de Ingeniería en Sistemas con conocimientos en desarrollo de software. Me apasiona crear soluciones que tengan un impacto real y siempre busco proyectos desafiantes que me permitan seguir aprendiendo y creciendo.

- 🎓 Educación y Formación: práctica y académica en desarrollo web y móvil 
- 🔧 Experiencia con **React, Firebase, FastAPI**  
- 📱 Construyendo aplicaciones con arquitectura **MVVM**  
- 🚀 Explorando DevOps y despliegue de aplicaciones  

---

## 🛠️ Tecnologías y Herramientas

<div align="center">
  <img src="https://skillicons.dev/icons?i=python,java,html,css,js,react,sqlite,firebase,mongodb,fastapi,windows,linux" height="50" alt="Tecnologías" />
</div>

<h4> Other Tools and Technologies </h4>
<span>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white">
  <a href="https://github.com/ELanza-48" target="_blank">
    <img src="https://img.shields.io/badge/github-181717.svg?style=for-the-badge&logo=github&logoColor=white" alt="github" />
  </a>
  <img src="https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white">
  <img src="https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white">
  <img src="https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white">
  <img src="https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white">

---

## 📈 GitHub Stats

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Manuelillo-dev&layout=compact&theme=tokyonight" width="38%" />

---
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bug Eater Snake Game</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Courier New', monospace;
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            color: #00ff88;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        .game-container {
            background: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 10px;
            border: 2px solid #00ff88;
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.3);
        }

        .game-header {
            text-align: center;
            margin-bottom: 20px;
        }

        .game-title {
            font-size: 24px;
            color: #ff6b6b;
            text-shadow: 0 0 10px rgba(255, 107, 107, 0.5);
            margin-bottom: 5px;
        }

        .game-subtitle {
            font-size: 14px;
            color: #00ff88;
            opacity: 0.8;
        }

        .game-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 14px;
        }

        .score {
            color: #4ecdc4;
        }

        .high-score {
            color: #ffe66d;
        }

        #gameCanvas {
            border: 2px solid #00ff88;
            background: #0a0a0a;
            display: block;
            box-shadow: 0 0 15px rgba(0, 255, 136, 0.2);
        }

        .controls {
            text-align: center;
            margin-top: 15px;
            font-size: 12px;
            color: #888;
        }

        .game-over {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(0, 0, 0, 0.9);
            color: #ff6b6b;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            border: 2px solid #ff6b6b;
            display: none;
        }

        .restart-btn {
            background: #00ff88;
            color: #000;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-family: 'Courier New', monospace;
            font-weight: bold;
            margin-top: 10px;
            transition: all 0.3s;
        }

        .restart-btn:hover {
            background: #4ecdc4;
            transform: scale(1.05);
        }

        /* Confetti Animation */
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background: #ff6b6b;
            pointer-events: none;
            animation: confetti-fall 3s linear forwards;
        }

        .confetti:nth-child(odd) {
            background: #00ff88;
            animation-delay: 0.5s;
        }

        .confetti:nth-child(3n) {
            background: #4ecdc4;
            animation-delay: 1s;
        }

        .confetti:nth-child(4n) {
            background: #ffe66d;
            animation-delay: 1.5s;
        }

        @keyframes confetti-fall {
            0% {
                transform: translateY(-100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }

        .achievement {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(0, 255, 136, 0.9);
            color: #000;
            padding: 10px 15px;
            border-radius: 5px;
            font-weight: bold;
            transform: translateX(300px);
            transition: transform 0.5s;
        }

        .achievement.show {
            transform: translateX(0);
        }
    </style>
</head>
<body>
    <div class="game-container">
        <div class="game-header">
            <div class="game-title">🐍 BUG EATER 🐛</div>
            <div class="game-subtitle">¡Ayuda al desarrollador a comer todos los bugs!</div>
        </div>
        
        <div class="game-stats">
            <div class="score">Bugs comidos: <span id="score">0</span></div>
            <div class="high-score">Récord: <span id="highScore">0</span></div>
        </div>
        
        <canvas id="gameCanvas" width="400" height="300"></canvas>
        
        <div class="controls">
            Usa las flechas ⬅️ ➡️ ⬆️ ⬇️ para moverte | ESPACIO para pausar
        </div>
    </div>

    <div class="game-over" id="gameOver">
        <h2>¡GAME OVER! 💀</h2>
        <p>¡Has comido <span id="finalScore">0</span> bugs!</p>
        <button class="restart-btn" onclick="restartGame()">🔄 Reintentar</button>
    </div>

    <div class="achievement" id="achievement"></div>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const scoreElement = document.getElementById('score');
        const highScoreElement = document.getElementById('highScore');
        const gameOverElement = document.getElementById('gameOver');
        const finalScoreElement = document.getElementById('finalScore');
        const achievementElement = document.getElementById('achievement');

        const gridSize = 20;
        const tileCount = canvas.width / gridSize;

        let snake = [
            {x: 10, y: 10}
        ];
        let food = {};
        let dx = 0;
        let dy = 0;
        let score = 0;
        let highScore = localStorage.getItem('snakeHighScore') || 0;
        let gameRunning = true;
        let isPaused = false;

        highScoreElement.textContent = highScore;

        // Generar comida (bug)
        function generateFood() {
            food = {
                x: Math.floor(Math.random() * tileCount),
                y: Math.floor(Math.random() * tileCount)
            };
            
            // Asegurar que la comida no aparezca sobre la serpiente
            for (let segment of snake) {
                if (segment.x === food.x && segment.y === food.y) {
                    generateFood();
                    return;
                }
            }
        }

        function drawGame() {
            // Limpiar canvas
            ctx.fillStyle = 'black';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // Dibujar serpiente (desarrollador)
            ctx.fillStyle = '#00ff88';
            for (let segment of snake) {
                ctx.fillRect(segment.x * gridSize, segment.y * gridSize, gridSize - 2, gridSize - 2);
            }

            // Dibujar cabeza con emoji
            ctx.fillStyle = '#4ecdc4';
            ctx.fillRect(snake[0].x * gridSize, snake[0].y * gridSize, gridSize - 2, gridSize - 2);
            
            // Dibujar comida (bug)
            ctx.fillStyle = '#ff6b6b';
            ctx.fillRect(food.x * gridSize, food.y * gridSize, gridSize - 2, gridSize - 2);
            
            // Dibujar emoji de bug
            ctx.fillStyle = '#fff';
            ctx.font = '12px Arial';
            ctx.textAlign = 'center';
            ctx.fillText('🐛', food.x * gridSize + gridSize/2, food.y * gridSize + gridSize/2 + 4);
        }

        function moveSnake() {
            if (isPaused || !gameRunning) return;

            const head = {x: snake[0].x + dx, y: snake[0].y + dy};

            // Verificar colisiones con paredes
            if (head.x < 0 || head.x >= tileCount || head.y < 0 || head.y >= tileCount) {
                gameOver();
                return;
            }

            // Verificar colisiones con el cuerpo
            for (let segment of snake) {
                if (head.x === segment.x && head.y === segment.y) {
                    gameOver();
                    return;
                }
            }

            snake.unshift(head);

            // Verificar si comió la comida
            if (head.x === food.x && head.y === food.y) {
                score++;
                scoreElement.textContent = score;
                generateFood();
                
                // Mostrar logros
                showAchievement(score);
                
                // Confetti en puntuaciones especiales
                if (score % 5 === 0) {
                    createConfetti();
                }
            } else {
                snake.pop();
            }
        }

        function gameOver() {
            gameRunning = false;
            finalScoreElement.textContent = score;
            
            if (score > highScore) {
                highScore = score;
                localStorage.setItem('snakeHighScore', highScore);
                highScoreElement.textContent = highScore;
                createConfetti();
                showAchievement(score, true);
            }
            
            gameOverElement.style.display = 'block';
        }

        function restartGame() {
            snake = [{x: 10, y: 10}];
            dx = 0;
            dy = 0;
            score = 0;
            scoreElement.textContent = score;
            gameRunning = true;
            isPaused = false;
            gameOverElement.style.display = 'none';
            generateFood();
        }

        function createConfetti() {
            for (let i = 0; i < 50; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.className = 'confetti';
                    confetti.style.left = Math.random() * window.innerWidth + 'px';
                    confetti.style.background = ['#ff6b6b', '#00ff88', '#4ecdc4', '#ffe66d'][Math.floor(Math.random() * 4)];
                    document.body.appendChild(confetti);
                    
                    setTimeout(() => confetti.remove(), 3000);
                }, i * 50);
            }
        }

        function showAchievement(currentScore, isHighScore = false) {
            let message = '';
            
            if (isHighScore) {
                message = '🎉 ¡NUEVO RÉCORD!';
            } else if (currentScore === 1) {
                message = '🎯 ¡Primer bug eliminado!';
            } else if (currentScore === 5) {
                message = '⚡ ¡Desarrollador junior!';
            } else if (currentScore === 10) {
                message = '🚀 ¡Desarrollador senior!';
            } else if (currentScore === 20) {
                message = '👑 ¡Bug Hunter Master!';
            }

            if (message) {
                achievementElement.textContent = message;
                achievementElement.classList.add('show');
                setTimeout(() => achievementElement.classList.remove('show'), 3000);
            }
        }

        function gameLoop() {
            moveSnake();
            drawGame();
            setTimeout(gameLoop, 120);
        }

        // Controles del teclado
        document.addEventListener('keydown', (e) => {
            if (!gameRunning && e.code !== 'Space') return;
            
            switch(e.code) {
                case 'ArrowUp':
                    if (dy !== 1) { dx = 0; dy = -1; }
                    break;
                case 'ArrowDown':
                    if (dy !== -1) { dx = 0; dy = 1; }
                    break;
                case 'ArrowLeft':
                    if (dx !== 1) { dx = -1; dy = 0; }
                    break;
                case 'ArrowRight':
                    if (dx !== -1) { dx = 1; dy = 0; }
                    break;
                case 'Space':
                    e.preventDefault();
                    if (gameRunning) isPaused = !isPaused;
                    break;
            }
        });

        // Inicializar juego
        generateFood();
        gameLoop();
    </script>
</body>
</html>

---

## 🚧 Proyectos destacados

- 🍩 **[SGP2 - Mini Donas Arenita](https://github.com/AngelMariscal01/MDA)** (En colaboración con [Ángel D. Mariscal](https://github.com/AngelMariscal01))  
  Sistema web integral para digitalizar la gestión de pedidos e inventario de la repostería "Mini Donas Arenita".  
  **Rol:** COO/CTO - Frontend Developer, liderando arquitectura y decisiones técnicas.  
  **Stack:** React + FastAPI + PostgreSQL + Vercel + Aiven  
  **Metodología:** DevATHENA (metodología ágil propia)

- 📊 **AsistenciasREST** (En colaboración con [Carlos H. García Lira](https://github.com/CHGL17), [Leonardo B. Garibay](https://github.com/LeonardoBG2003),[Carlos E. López Quesada](https://github.com/manyquesada))  
  API REST robusta para gestionar actividades extraescolares en el ITESZ, resolviendo la problemática de acreditación estudiantil.  
  **Arquitectura:** 3 microservicios por dominio (Asistencias, Usuarios, Grupos)  
  **Stack:** FastAPI + MongoDB Atlas + Swagger  
  **Impacto:** Optimización del proceso de liberación de créditos académicos

- 🌱 **[ControlAgro25](https://github.com/SaidPR/ControlAgro25)** (En colaboración con [Said Piñones](https://github.com/SaidPR))  
  App móvil para gestión agrícola integral: control de asistencia, producción y trabajadores.  
  **Stack:** React Native + Firebase + Expo Notifications  
  **Arquitectura:** MVVM con Firestore y notificaciones push en tiempo real

- 📱 **[Calls Linking](https://github.com/Manuelillo-dev/Calls_Linking-API_REACT-NATIVE)**  
  App móvil para gestión de trabajadores con funcionalidades avanzadas de comunicación.  
  Incluye llamadas directas, edición de perfiles con cámara/galería y navegación dinámica.  
  **Stack:** React Native + Expo + React Navigation

---

## 🙌 ¡Gracias por visitar mi perfil!

_"El conocimiento se construye paso a paso, un desafío a la vez."_
