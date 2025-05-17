# Ff-16-player-solo-tournament-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hamro Topup FF Tournament</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #121212;
      color: #ffffff;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #00ff99;
    }
    form {
      background: #1e1e1e;
      padding: 20px;
      border-radius: 10px;
      display: inline-block;
    }
    input {
      padding: 10px;
      margin: 10px;
      border: none;
      border-radius: 5px;
      width: 80%;
    }
    button {
      padding: 10px 20px;
      background: #00ff99;
      border: none;
      color: black;
      font-weight: bold;
      border-radius: 5px;
      cursor: pointer;
    }
    .slot-info {
      margin: 20px 0;
      font-size: 18px;
    }
  </style>
</head>
<body>

  <h1>16 Player Solo Level Tournament</h1>
  <p>Hosted by <strong>Hamro Topup Centre</strong></p>
  <p>Registration Fee: Rs. 100</p>
  <div class="slot-info" id="slotInfo">Slots Filled: 0 / 16</div>

  <form id="registerForm">
    <input type="text" id="name" placeholder="Your Name" required><br>
    <input type="text" id="uid" placeholder="Free Fire UID" required><br>
    <button type="submit">Register</button>
  </form>

  <div id="message" style="margin-top: 20px;"></div>

  <script>
    let slotsFilled = 0;
    const maxSlots = 16;
    const form = document.getElementById('registerForm');
    const slotInfo = document.getElementById('slotInfo');
    const message = document.getElementById('message');

    form.addEventListener('submit', function(e) {
      e.preventDefault();
      if (slotsFilled < maxSlots) {
        const name = document.getElementById('name').value;
        const uid = document.getElementById('uid').value;
        slotsFilled++;
        slotInfo.textContent = `Slots Filled: ${slotsFilled} / 16`;
        message.innerHTML = `<p style="color: lightgreen;">${name} registered successfully with UID: ${uid}!</p>`;
        form.reset();
      } else {
        message.innerHTML = `<p style="color: red;">Tournament is full! No more registrations allowed.</p>`;
      }
    });
  </script>

</body>
</html>
