# -3.-Jewelry-Chain-Length-Guide-Tool
A visual interactive guide where customers choose body type + jewelry type, and the tool suggests ideal chain lengths.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jewelry Chain Length Guide Tool</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      max-width: 600px;
      margin: auto;
      background-color: #fdfdfd;
      color: #333;
    }
    h1 {
      font-size: 1.8rem;
      text-align: center;
    }
    .form-group {
      margin-bottom: 15px;
    }
    label {
      font-weight: bold;
      display: block;
      margin-bottom: 5px;
    }
    select, button {
      width: 100%;
      padding: 10px;
      font-size: 1rem;
      margin-top: 5px;
    }
    .result {
      margin-top: 20px;
      padding: 15px;
      border: 1px solid #ccc;
      background-color: #f8f8f8;
      display: none;
    }
    .cta {
      margin-top: 20px;
      text-align: center;
    }
    .cta a {
      text-decoration: none;
      background-color: #000;
      color: #fff;
      padding: 10px 20px;
      border-radius: 5px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Jewelry Chain Length Guide</h1>
  <div class="form-group">
    <label for="person">Who is this for?</label>
    <select id="person">
      <option value="woman">Woman</option>
      <option value="man">Man</option>
      <option value="child">Child</option>
    </select>
  </div>

  <div class="form-group">
    <label for="style">Select Necklace Style:</label>
    <select id="style">
      <option value="Choker">Choker (14–16")</option>
      <option value="Princess">Princess (18")</option>
      <option value="Matinee">Matinee (20–24")</option>
      <option value="Opera">Opera (28–36")</option>
      <option value="Rope">Rope (36+ inches)</option>
    </select>
  </div>

  <button onclick="getLength()">Show Recommended Length</button>

  <div class="result" id="output"></div>

  <div class="cta">
    <p>Need chain by the foot?</p>
    <a href="https://www.continentalbeadsuppliers.com/collections/chain">Shop Chains</a>
  </div>

  <script>
    function getLength() {
      const person = document.getElementById('person').value;
      const style = document.getElementById('style').value;
      let length = '';

      switch(style) {
        case 'Choker':
          length = '14 to 16 inches';
          break;
        case 'Princess':
          length = '18 inches';
          break;
        case 'Matinee':
          length = '20 to 24 inches';
          break;
        case 'Opera':
          length = '28 to 36 inches';
          break;
        case 'Rope':
          length = '36 inches or longer';
          break;
      }

      const message = `For a ${person} wearing a ${style.toLowerCase()}-style necklace, we recommend a chain length of <strong>${length}</strong>.`;
      const outputDiv = document.getElementById('output');
      outputDiv.innerHTML = message;
      outputDiv.style.display = 'block';
    }
  </script>
</body>
</html>
