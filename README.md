<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>VORTUNIX LOGIN</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&family=Montserrat:wght@400;600&display=swap" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
  <style>
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
    }
    .container {
      background: #1A0526;
      border: 1px solid #3F0A5E;
      padding: 25px;
      border-radius: 20px;
      box-shadow: 0 0 25px rgba(190, 96, 238, 0.4);
      width: 100%;
      max-width: 400px;
    }
    h1 {
      font-family: 'Orbitron', sans-serif;
      color: #BE60EE;
      text-align: center;
      margin-bottom: 25px;
    }
    input {
      width: 100%;
      padding: 14px;
      margin-bottom: 20px;
      border-radius: 10px;
      border: 1px solid #BE60EE;
      background: #2D0842;
      color: #fff;
      outline: none;
      font-size: 16px;
    }
    input:focus {
      border-color: #9a4ed1;
      box-shadow: 0 0 10px rgba(190,96,238,0.5);
    }
    button {
      width: 100%;
      padding: 16px;
      border: none;
      border-radius: 10px;
      font-size: 18px;
      font-weight: 600;
      cursor: pointer;
      background: linear-gradient(90deg, #BE60EE, #7D26A6);
      color: #fff;
      box-shadow: 0 0 15px rgba(190, 96, 238, 0.4);
      transition: 0.3s;
    }
    button:hover {
      background: linear-gradient(90deg, #7D26A6, #BE60EE);
      box-shadow: 0 0 25px rgba(190,96,238,0.8);
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>VORTUNIX LOGIN</h1>
    <form id="loginForm">
      <input type="text" id="username" placeholder="Username" required>
      <input type="password" id="password" placeholder="Password" required>
      <button type="submit"><i class="fas fa-sign-in-alt"></i> LOGIN</button>
    </form>
  </div>

  <script>
    document.getElementById('loginForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const user = document.getElementById('username').value.trim();
      const pass = document.getElementById('password').value.trim();

      // ubah sesuai kebutuhanmu
      if (user === 'vortunix' && pass === 'vortunix') {
        // ✅ langsung pindah ke halaman utama
        window.location.href = 'vortunix-infinity.html';
      } else {
        alert('❌ Username atau password salah!');
      }
    });
  </script>
</body>
</html>
