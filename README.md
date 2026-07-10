# simple-calculator
This  is a normal code for calculator 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #f4f4f4;
            font-family: Arial, sans-serif;
        }

        .calculator {
            background: #222;
            padding: 20px;
            border-radius: 10px;
            width: 260px;
        }

        .display {
            width: 100%;
            height: 50px;
            background: #000;
            color: #0f0;
            text-align: right;
            padding: 10px;
            font-size: 20px;
            margin-bottom: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        button {
            padding: 15px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .operator {
            background: orange;
            color: white;
        }

        .equal {
            background: green;
            color: white;
            grid-column: span 2;
        }

        .clear {
            background: red;
            color: white;
            grid-column: span 2;
        }

        button:hover {
            opacity: 0.8;
        }
    </style>
</head><body>

<div class="calculator">
    <div id="display" class="display">0</div>

    <div class="buttons">
        <button onclick="clearDisplay()" class="clear">C</button>
        <button onclick="appendValue('/')" class="operator">/</button>
        <button onclick="appendValue('*')" class="operator">*</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button onclick="appendValue('-')" class="operator">-</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="appendValue('+')" class="operator">+</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="calculate()" class="equal">=</button>

        <button onclick="appendValue('0')">0</button>
        <button onclick="appendValue('.')">.</button>
    </div>
</div>

<script>
    let display = document.getElementById("display");

    function appendValue(value) {
        if (display.innerText === "0") {
            display.innerText = value;
        } else {
            display.innerText += value;
        }
    }

    function clearDisplay() {
        display.innerText = "0";
    }

    function calculate() {
        try {
            display.innerText = eval(display.innerText);
        } catch {
            display.innerText = "Error";
        }
    }
</script>

</body>
</html>
