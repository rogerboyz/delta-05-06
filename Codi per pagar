<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>DELTA - Festa 05/06</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Montserrat', sans-serif;
      background: #f8f9fa;
      color: #333;
      margin: 0;
      padding: 0;
    }
    header {
      background: #000;
      color: white;
      text-align: center;
      padding: 2rem 1rem;
    }
    .container {
      max-width: 500px;
      margin: 2rem auto;
      background: white;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    label {
      display: block;
      margin-top: 1rem;
      font-weight: 600;
    }
    input, select, button {
      width: 100%;
      padding: 0.8rem;
      margin-top: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 1rem;
    }
    button {
      background: #000;
      color: white;
      margin-top: 1.5rem;
      cursor: pointer;
    }
    .payment-info {
      margin-top: 2rem;
      padding: 1rem;
      background: #e9ecef;
      border-radius: 5px;
    }
    .qr {
      margin-top: 1rem;
      text-align: center;
    }
  </style>
</head>
<body>
  <header>
    <h1>Festa DELTA - 05/06</h1>
    <p>Entrades: 25 € | Opció A: 3 copas | Opció B: 2 copas + sopar</p>
  </header>

  <div class="container">
    <form id="deltaForm">
      <label for="name">Nom complet</label>
      <input type="text" id="name" name="name" required>

      <label for="email">Correu electrónic</label>
      <input type="email" id="email" name="email" required>

      <label for="option">Selecciona la teva entrada</label>
      <select id="option" name="option" required>
        <option value="Opción 1 - 3 consumiciones">Opción A - 3 consumiciones</option>
        <option value="Opción 2 - 2 consumiciones + cena">Opción B - 2 consumiciones + cena</option>
      </select>

      <label for="drink">Quina beguda prefereixes?</label>
      <select id="drink" name="drink" required>
        <option value="Cerveza">Birra</option>
        <option value="Vino">Vi</option>
        <option value="Ron">Ron</option>
        <option value="Whiskey">Whiskey</option>
        <option value="Ginebra">Ginebra</option>
        <option value="Vodka">Vodka</option>
        
      </select>
      
       <label for="drink">Quina mezcla prefiereixes</label>
      <select id="drink" name="drink" required>
        <option value="Coca-Cola">Coca-Cola</option>
        <option value="Fanta Taronja">Fanta Taronja</option>
        <option value="Fanta Llimona">Fanta Llimona</option>
        <option value="RedBull">RedBull</option>
       
      </select>

      <button type="submit">Reservar i veure instruccions de pagament</button>
    </form>

    <div class="payment-info" id="paymentInfo" style="display:none;">
      <h3>Gràcias per la teva reserva!</h3>
      <p>Realiza un Bizum de <strong>25 €</strong> al número <strong>653 521 098</strong>.</p>
      <p><strong>Concepto:</strong> DELTA + Tu nombre</p>
      <div class="qr">
        <img src="https://chart.googleapis.com/chart?cht=qr&chs=200x200&chl=SMSTO:653521098:DELTA" alt="QR Bizum">
      </div>
      <p>T'arribara un correu de confirmació un cop completis aquest pas.</p>
    </div>
  </div>

  <!-- EmailJS -->
  <script src="https://cdn.jsdelivr.net/npm/emailjs-com@3/dist/email.min.js"></script>
  <script>
    (function(){ emailjs.init("YOUR_EMAILJS_USER_ID"); })();

    const form = document.getElementById('deltaForm');
    form.addEventListener('submit', function(e) {
      e.preventDefault();

      const data = {
        name: form.name.value,
        email: form.email.value,
        option: form.option.value,
        drink: form.drink.value
      };

      // Send confirmation email
      emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", data)
        .then(() => {
          document.getElementById('paymentInfo').style.display = 'block';
          form.reset();
        });

      // Send to Google Sheets (through Apps Script web app)
      fetch('YOUR_GOOGLE_SCRIPT_WEB_APP_URL', {
        method: 'POST',
        mode: 'no-cors',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(data)
      });
    });
  </script>
</body>
</html>
