<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Counter</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #111;
      color: #fff;
      text-align: center;
      padding: 30px;
    }
    h1 {
      color: #00ffff;
    }
    input {
      padding: 10px;
      font-size: 16px;
      border-radius: 6px;
      border: none;
      margin-top: 15px;
    }
    #counter {
      font-size: 28px;
      margin-top: 20px;
      color: #0f0;
    }
  </style>
</head>
<body>

  <h1>Counter</h1>

  <label for="birthDate">Enter Your Birthday and Time:</label><br>
  <input type="datetime-local" id="birthDate"><br>

  <div id="counter">Seconds: 0</div>

  <script>
    const birthInput = document.getElementById("birthDate");
    const counter = document.getElementById("counter");
    let birthDate = null;

    birthInput.addEventListener("change", () => {
      birthDate = new Date(birthInput.value);
      updateSecondsAlive();
    });

    function updateSecondsAlive() {
      if (!birthDate) return;

      setInterval(() => {
        const now = new Date();
        const seconds = Math.floor((now - birthDate) / 1000);
        counter.textContent = `Seconds: ${seconds.toLocaleString()}`;
      }, 1000);
    }
  </script>

</body>
</html>