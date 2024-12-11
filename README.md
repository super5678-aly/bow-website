<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title> Waste ur time with me! 🎀</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: hotpink; /* Hot pink background */
      color: darkred; /* Text color */
      text-align: center;
      border: 5px solid darkred; /* Dark red border around the whole page */
      box-sizing: border-box; /* Ensures the border doesn't affect the layout */
    }

    header {
      background-color: darkred; /* Dark red background */
      padding: 20px;
      color: black; /* Black text */
    }

    h1 {
      margin: 0;
    }

    main {
      padding: 20px;
    }

    select, label, input {
      font-size: 16px;
      margin-top: 10px;
    }

    select {
      border: 2px solid darkred;
      color: black;
      background-color: #ffe6e6;
    }

    select:focus {
      outline: none;
      border-color: darkred;
      box-shadow: 0 0 5px darkred;
    }

    .output, .motivation-output {
      margin-top: 20px;
    }

    .highlight {
      font-size: 20px;
      color: darkred;
      background-color: #ffe6e6;
      padding: 10px;
      border-radius: 10px;
      display: inline-block;
      border: 2px solid darkred;
    }

    .motivation-box {
      margin-top: 50px;
      background-color: #ffe6e6;
      padding: 15px;
      border-radius: 10px;
      border: 2px solid darkred;
      display: inline-block;
    }

    #motivationSection {
      margin-top: 100px;
    }

    #studySection {
      margin-top: 50px;
    }

    #studySection h2 {
      color: darkred;
    }

    .study-option label {
      display: inline-block;
      margin: 10px;
      color: black;
    }
  </style>
</head>
<body>
  <header>
    <h1> Super Fatima 🎀</h1>
  </header>

  <main>
    <h2>Idhar kidhar?</h2>
    <p>HONEY SHINE BRIGHT, LET THEM BURNNNNNN</p>

    <h2>🎀 Choose an option 🎀</h2>
    <form>
      <label for="options">Select your mood:</label>
      <select id="options" name="options">
        <option value="">-- Select an Option --</option>
        <option value="option1">Lowkey Anxious</option>
        <option value="option2">Certified Loner</option>
        <option value="option3">Vibing</option>
        <option value="option4">IDK and IDC</option>
      </select>
    </form>

    <div id="output" class="output"></div>

    <div id="motivationSection">
      <h2>Listen to me</h2>
      <input type="text" id="nameInput" placeholder="Enter your name">
      <button id="motivateButton">Get Motivation</button>
      <div id="motivationOutput" class="motivation-output"></div>
    </div>

    <!-- New Section for 'Parha Nahi Ja Raha?' -->
    <div id="studySection">
      <h2>Parha Nahi Ja Raha?</h2>
      <form class="study-option">
        <label>
          <input type="radio" name="studyStatus" value="yes1"> YES
        </label>
        <label>
          <input type="radio" name="studyStatus" value="yes2"> YES
        </label>
      </form>
      <div id="studyOutput" class="output"></div>
    </div>
  </main>

  <script>
    const dropdown = document.getElementById('options');
    const output = document.getElementById('output');
    const nameInput = document.getElementById('nameInput');
    const motivateButton = document.getElementById('motivateButton');
    const motivationOutput = document.getElementById('motivationOutput');
    const studyRadios = document.getElementsByName('studyStatus');
    const studyOutput = document.getElementById('studyOutput');

    // Mood dropdown functionality
    dropdown.addEventListener('change', function () {
      const selectedValue = this.value;
      let displayText = '';

      if (selectedValue === 'option1') {
        displayText = 'Its a harsh world .Just do not give a fuck!';
      } else if (selectedValue === 'option2') {
        displayText = 'Bro u are not alone they just dont deserve uh!';
      } else if (selectedValue === 'option3') {
        displayText = 'Just keep vibing cuz Masti nahi rukni chaiye!';
      } else if (selectedValue === 'option4') {
        displayText = 'Sometimes saying "I Don’t Know and I Don’t Care" is self-care. Just say "Jatt don’t care, Baby Jatt don’t care" and move on!';
      } else {
        displayText = ''; 
      }

      if (displayText) {
        output.innerHTML = `<div class="highlight">${displayText}</div>`;
      } else {
        output.innerHTML = '';
      }
    });

    // Motivation button functionality
    motivateButton.addEventListener('click', function () {
      const name = nameInput.value.trim();

      if (name === '') {
        motivationOutput.innerHTML = `<div class="motivation-box">Please enter your name to receive motivation!</div>`;
        return;
      }

      const messages = [
        `Oye dukh apni jaga lakin, ${name}! Juice pila do musami kaaa`,
        `Eating is better than crying, ${name}! `,
        `${name}, Beta parh lo ! 🚀`
      ];

      const randomMessage = messages[Math.floor(Math.random() * messages.length)];
      motivationOutput.innerHTML = `<div class="motivation-box">${randomMessage}</div>`;

      nameInput.value = '';
    });

    // Radio button functionality
    studyRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        if (radio.checked) {
          const selectedValue = radio.value;
          studyOutput.innerHTML = `<div class="highlight"> ${selectedValue === 'yes1' ? 'Us bro us!   ' : 'Beta parh loooooo'}</div>`;
      });
    });
  </script>
</body>
</html>
