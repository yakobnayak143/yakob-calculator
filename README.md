# yakob-calculator
<!DOCTYPE html>
<html>
<head>
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    input {
      width: 50px;
      text-align: center;
    }
    button {
      margin: 5px;
      padding: 10px 20px;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <h2>Simple Calculator</h2>
  
  <input type="number" id="num1" placeholder="0">
  <input type="number" id="num2" placeholder="0"><br><br>
  
  <button onclick="calculate('+')">+</button>
  <button onclick="calculate('-')">-</button>
  <button onclick="calculate('*')">*</button>
  <button onclick="calculate('/')">/</button>
  
  <h3 id="result">Result: </h3>
  
  <script>
    function calculate(op) {
      let n1 = parseFloat(document.getElementById("num1").value);
      let n2 = parseFloat(document.getElementById("num2").value);
      let res;
      
      switch(op) {
        case '+': res = n1 + n2; break;
        case '-': res = n1 - n2; break;
        case '*': res = n1 * n2; break;
        case '/': res = n2 !== 0 ? n1 / n2 : "Error! Division by zero"; break;
      }
      
      document.getElementById("result").innerText = "Result: " + res;
    }
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Web Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f0f0f0;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #222;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }
    #display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 15px;
      padding: 10px;
      border: none;
      border-radius: 5px;
      background: #fff;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 70px);
      gap: 10px;
    }
    button {
      height: 60px;
      font-size: 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      background: #444;
      color: #fff;
      transition: background 0.2s;
    }
    button:hover {
      background: #666;
    }
    .equal {
      grid-column: span 2;
      background: #28a745;
    }
    .equal:hover {
      background: #218838;
    }
    .clear {
      background: #dc3545;
    }
    .clear:hover {
      background: #c82333;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('/')">÷</button>
      <button onclick="appendValue('*')">×</button>
      <button onclick="appendValue('-')">−</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('.')">.</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="calculate()" class="equal">=</button>

      <button onclick="appendValue('0')" style="grid-column: span 2;">0</button>
    </div>
  </div>

  <script>
    let display = document.getElementById("display");

    function appendValue(val) {
      display.value += val;
    }

    function clearDisplay() {
      display.value = "";
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>
</body>
</html>

