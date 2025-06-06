<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
      width: 300px;
    }
    #display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      padding: 10px;
      margin-bottom: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      padding: 20px;
      font-size: 18px;
      border: none;
      background-color: #e0e0e0;
      border-radius: 5px;
      cursor: pointer;
    }
    button.operator {
      background-color: #f9a825;
      color: white;
    }
    button.equal {
      background-color: #43a047;
      color: white;
      grid-column: span 2;
    }
    button.clear {
      background-color: #e53935;
      color: white;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button class="operator" onclick="appendValue('/')">/</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button class="operator" onclick="appendValue('*')">*</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button class="operator" onclick="appendValue('-')">-</button>
      <button onclick="appendValue('0')">+/-</button>

      <button onclick="appendValue('0')">0</button>
      
      <button onclick="appendValue('.')">.</button>
      <button onclick="appendValue('0')">()</button>
      <button class="equal" onclick="calculate()">=</button>
      <button class="operator" onclick="appendValue('+')">+</button>

      <button class="clear" onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');

    function appendValue(value) {
      display.value += value;
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch (e) {
        display.value = 'Error';
      }
    }

    function clearDisplay() {
      display.value = '';
    }
  </script>
</body>
</html>
