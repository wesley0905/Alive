#<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Seconds Alive Counter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #121212;
      color: #ffffff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    h1 {
      color: #00bfff;
    }
    input {
      padding: 10px;
      font-size: 16px;
      margin: 10px 0;
      border-radius: 5px;
      border: none;
    }
    #counter {
      font-size: 24px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Seconds You've Been Alive</h1>
  <label for="dob">Enter Your Birthday:</label>
  <input type="datetime-local" id="dob" />
  <div id="counter">Seconds: 0</div>

  <script>
    const input = document.getElementById('dob');
    const counter = document.getElementById('counter');
    let birthDate;

    input.addEventListener('change', () => {
      birthDate = new Date(input.value);
      updateCounter();
    });

    function updateCounter() {
      if (!birthDate) return;
      setInterval(() => {
        const now = new Date();
        const secondsAlive = Math.floor((now - birthDate) / 1000);
        counter.textContent = `Seconds: ${secondsAlive.toLocaleString()}`;
      }, 1000);
    }
  </script>
</body>
</html>