<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>VORTUNIX APPS</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&family=Montserrat:wght@400;600&display=swap" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box;}
    body {
      font-family: 'Montserrat', sans-serif;
      background: #0D0014;
      color: #E0E0E0;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 20px;
      position: relative; 
      overflow-x: hidden;
    }

    .app-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
        max-width: 420px;
        position: relative;
        z-index: 10;
    }

    h1.main-title {
      font-family: 'Orbitron', sans-serif;
      color: #BE60EE;
      font-size: 32px;
      margin-bottom: 30px;
      text-shadow: 0 0 10px rgba(190, 96, 238, 0.6);
      letter-spacing: 2px;
    }

    .container {
      background: #1A0526;
      border: 1px solid #3F0A5E;
      padding: 24px;
      border-radius: 20px;
      max-width: 420px;
      width: 100%;
      box-shadow: 0 0 25px rgba(190, 96, 238, 0.4);
      backdrop-filter: blur(5px);
      position: relative;
      margin-bottom: 20px;
    }

    .profile-card { text-align: center; margin-bottom: 30px; }
    .profile-logo {
      width: 100px; height: 100px; margin: 0 auto 15px; display: block;
      border-radius: 50%;
      box-shadow: 0 0 10px rgba(190, 96, 238, 0.8);
      border: 3px solid #BE60EE;
      object-fit: cover;
    }

    .section-title { 
      font-family: 'Orbitron', sans-serif; font-size: 18px; color: #BE60EE;
      margin-bottom: 15px; text-align: left; text-transform: uppercase; letter-spacing: 1px;
    }
    
    input[type="text"], input[type="password"] {
      width: 100%; padding: 14px 18px; border-radius: 10px;
      background: #2D0842; border: 1px solid #BE60EE; color: #E0E0E0;
      margin-bottom: 25px; font-size: 16px; outline: none;
      transition: border-color 0.3s ease, box-shadow 0.3s ease;
    }

    input::placeholder { color: #9A9A9A; }
    input:focus {
      border-color: #9a4ed1;
      box-shadow: 0 0 10px rgba(190, 96, 238, 0.5);
    }

    .execute-button {
      background: linear-gradient(90deg, #BE60EE, #7D26A6);
      color: #fff; padding: 18px; width: 100%;
      border-radius: 10px; font-weight: bold; border: none;
      margin-bottom: 12px; cursor: pointer; font-size: 18px; letter-spacing: 1px;
      transition: 0.3s ease, box-shadow 0.3s ease;
      box-shadow: 0 0 15px rgba(190, 96, 238, 0.4);
    }
    .execute-button:hover {
      background: linear-gradient(90deg, #7D26A6, #BE60EE);
      box-shadow: 0 0 25px rgba(190, 96, 238, 0.8);
    }

    .video-container {
      position: fixed; top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(13, 0, 20, 0.95);
      z-index: 1000; display: none;
      justify-content: center; align-items: center;
      backdrop-filter: blur(10px);
    }
    .video-container.active { display: flex; }
    .video-wrapper {
      width: 80%; max-width: 800px; position: relative;
      border-radius: 15px; overflow: hidden;
      box-shadow: 0 0 50px rgba(190, 96, 238, 0.4);
      border: 2px solid #BE60EE;
    }
    .video-player {
      width: 100%; height: auto; display: block; border-radius: 15px;
    }

    #smoke-background {
      position: fixed; top: 0; left: 0;
      width: 100%; height: 100%;
      z-index: 1; pointer-events: none; overflow: hidden;
    }
    .smoke-particle {
      position: absolute; bottom: 0; width: 5px; height: 5px;
      background-color: rgba(255, 50, 50, 0.6);
      border-radius: 50%; filter: blur(2px);
      animation: smoke-rise linear infinite;
    }
    @keyframes smoke-rise {
      0% { transform: translateY(0) translateX(0) scale(0.5); opacity: 0.8; }
      50% { transform: translateY(-50vh) translateX(10px) scale(1.5); opacity: 0.5; }
      100% { transform: translateY(-100vh) translateX(20px) scale(2); opacity: 0; }
    }
  </style>
</head>
<body>
  <div id="smoke-background"></div>

  <div class="video-container" id="videoContainer">
    <div class="video-wrapper">
      <video class="video-player" id="loginVideo">
        <source src="https://files.catbox.moe/mksc7a.mp4" type="video/mp4">
        Your browser does not support the video tag.
      </video>
    </div>
  </div>

  <div class="app-wrapper">
    <h1 class="main-title">VORTUNIX APPS</h1>

    <div class="container profile-card">
        <img src="https://files.catbox.moe/4tq0rq.jpg" alt="Logo" class="profile-logo" />
        <div class="profile-username" style="font-family: 'Orbitron', sans-serif; font-size: 24px; color: #E0E0E0; font-weight: bold; margin-bottom: 8px;">Login Account</div>
        <div class="profile-details" style="font-size: 14px; color: #9A9A9A;">
          Please enter your credentials to access the dashboard
        </div>
    </div>

    <div class="container">
        <form id="loginForm">
            <div class="section-title">Username</div>
            <input type="text" id="username" placeholder="Enter your username" required />

            <div class="section-title">Password</div>
            <input type="password" id="password" placeholder="Enter your password" required />

            <button type="submit" class="execute-button">
              <i class="fas fa-sign-in-alt"></i> LOGIN
            </button>
        </form>
    </div>
  </div>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const loginForm = document.getElementById('loginForm');
      const videoContainer = document.getElementById('videoContainer');
      const loginVideo = document.getElementById('loginVideo');

      loginForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const username = document.getElementById('username').value.trim();
        const password = document.getElementById('password').value.trim();

        if (username === 'vortunix' && password === 'vortunix') {
          showSuccessVideo();
          loginVideo.addEventListener('ended', function() {
            window.location.href = 'vortunix-infinity.html';
          }, { once: true });
        } else {
          alert('Username atau password salah!');
        }
      });

      function showSuccessVideo() {
        videoContainer.classList.add('active');
        loginVideo.play().catch(error => {
          console.error("Error playing video:", error);
          window.location.href = 'vortunix-infinity.html';
        });
      }

      function createSmokeParticles() {
        const smokeBackground = document.getElementById('smoke-background');
        for (let i = 0; i < 15; i++) {
          setTimeout(() => createSmokeParticle(smokeBackground), i * 200);
        }
        setInterval(() => createSmokeParticle(smokeBackground), 300);
      }

      function createSmokeParticle(container) {
        const particle = document.createElement('div');
        particle.classList.add('smoke-particle');
        const leftPosition = Math.random() * 100;
        particle.style.left = `${leftPosition}%`;
        const duration = 10 + Math.random() * 20;
        particle.style.animationDuration = `${duration}s`;
        const size = 3 + Math.random() * 7;
        particle.style.width = `${size}px`;
        particle.style.height = `${size}px`;
        const red = 200 + Math.floor(Math.random() * 55);
        const alpha = 0.3 + Math.random() * 0.4;
        particle.style.backgroundColor = `rgba(${red}, 50, 50, ${alpha})`;
        container.appendChild(particle);
        setTimeout(() => particle.remove(), duration * 1000);
      }

      createSmokeParticles();
      loginVideo.load();
    });
  </script>
</body>
</html>      </video>
    </div>
  </div>

  <div class="app-wrapper">
    <h1 class="main-title">VORTUNIX APPS</h1>

    <div class="container profile-card">
        <img src="https://files.catbox.moe/4tq0rq.jpg" alt="Logo" class="profile-logo" />
        <div class="profile-username" style="font-family: 'Orbitron', sans-serif; font-size: 24px; color: #E0E0E0; font-weight: bold; margin-bottom: 8px;">Login Account</div>
        <div class="profile-details" style="font-size: 14px; color: #9A9A9A;">
          Please enter your credentials to access the dashboard
        </div>
    </div>

    <div class="container">
        <form id="loginForm">
            <div class="section-title">Username</div>
            <input type="text" id="username" placeholder="Enter your username" required />

            <div class="section-title">Password</div>
            <input type="password" id="password" placeholder="Enter your password" required />

            <button type="submit" class="execute-button">
              <i class="fas fa-sign-in-alt"></i> LOGIN
            </button>
        </form>
    </div>
  </div>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const loginForm = document.getElementById('loginForm');
      const videoContainer = document.getElementById('videoContainer');
      const loginVideo = document.getElementById('loginVideo');

      loginForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const username = document.getElementById('username').value.trim();
        const password = document.getElementById('password').value.trim();

        if (username === 'vortunix' && password === 'vortunix') {
          showSuccessVideo();
          loginVideo.addEventListener('ended', function() {
            window.location.href = 'VORTUNIX INFINITY.html';
          }, { once: true });
        } else {
          alert('Username atau password salah!');
        }
      });

      function showSuccessVideo() {
        videoContainer.classList.add('active');
        loginVideo.play().catch(error => {
          console.error("Error playing video:", error);
          window.location.href = 'FORTUNIX INFINITY.html';
        });
      }

      function createSmokeParticles() {
        const smokeBackground = document.getElementById('smoke-background');
        for (let i = 0; i < 15; i++) {
          setTimeout(() => createSmokeParticle(smokeBackground), i * 200);
        }
        setInterval(() => createSmokeParticle(smokeBackground), 300);
      }

      function createSmokeParticle(container) {
        const particle = document.createElement('div');
        particle.classList.add('smoke-particle');
        const leftPosition = Math.random() * 100;
        particle.style.left = `${leftPosition}%`;
        const duration = 10 + Math.random() * 20;
        particle.style.animationDuration = `${duration}s`;
        const size = 3 + Math.random() * 7;
        particle.style.width = `${size}px`;
        particle.style.height = `${size}px`;
        const red = 200 + Math.floor(Math.random() * 55);
        const alpha = 0.3 + Math.random() * 0.4;
        particle.style.backgroundColor = `rgba(${red}, 50, 50, ${alpha})`;
        container.appendChild(particle);
        setTimeout(() => particle.remove(), duration * 1000);
      }

      createSmokeParticles();
      loginVideo.load();
    });
  </script>
</body>
</html>
