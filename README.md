<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
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
      <button onclick="calculate()">=</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  background: #f3f4f6;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  font-family: sans-serif;
}

.calculator {
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 8px 16px rgba(0,0,0,0.2);
  padding: 20px;
  width: 240px;
}

#display {
  width: 100%;
  height: 50px;
  font-size: 24px;
  text-align: right;
  margin-bottom: 10px;
  padding: 5px 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  height: 50px;
  font-size: 18px;
  border: none;
  border-radius: 5px;
  background-color: #e5e7eb;
  cursor: pointer;
  transition: 0.2s;
}

button:hover {
  background-color: #d1d5db;
}
function appendValue(val) {
  document.getElementById("display").value += val;
}

function clearDisplay() {
  document.getElementById("display").value = "";
}

function calculate() {
  try {
    const result = eval(document.getElementById("display").value);
    document.getElementById("display").value = result;
  } catch {
    alert("Invalid input!");
  }
}