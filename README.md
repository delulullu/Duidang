<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For You</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: linear-gradient(to right, #fdfbfb, #ebedee);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Poppins', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    h1 {
      color: #333;
      margin-bottom: 40px;
      padding: 0 20px;
      font-size: 5vw;
      max-width: 90%;
    }

    .buttons {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
    }

    button {
      font-size: 5vw;
      padding: 12px 24px;
      min-width: 150px;
      max-width: 250px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s ease;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
      z-index: 10; /* Ensures buttons are on top */
    }

    #yes {
      background-color: #7ed6df;
      color: #fff;
    }

    #no {
      background-color: #dff9fb;
      color: #130f40;
    }
  </style>
</head>
<body>

  <h1>Will you promise me to do your best and not be sad no matter what happens?</h1>

  <div class="buttons">
    <button id="yes">Yes</button>
    <button id="no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const yesBtn = document.getElementById('yes');

    let yesBtnSize = 5; // Initial size factor for the "Yes" button
    let noBtnClicked = 0; // Count how many times the "No" button has been clicked

    // Function to grow the "Yes" button
    function growYesButton() {
      yesBtnSize += 2; // Increase size factor
      yesBtn.style.fontSize = `${yesBtnSize}vw`; // Increase font size
      yesBtn.style.padding = `${12 + yesBtnSize}px ${24 + yesBtnSize}px`; // Increase padding

      if (yesBtnSize >= 15) { // When "Yes" reaches a large enough size
        noBtn.style.display = 'none'; // Hide "No" button
      }
    }

    noBtn.addEventListener('click', () => {
      noBtnClicked++; // Increment the "No" button click count
      growYesButton(); // Call the function to grow the "Yes" button
    });

    yesBtn.addEventListener('click', () => {
      document.body.innerHTML = `
        <h1 style="color:#6D214F; padding: 20px; font-size: 6vw;">
          I knew you'd say yes.<br><br>
          I believe in you so much.<br><br>
          I love you.
        </h1>
      `;
    });
  </script>

</body>
</html>
