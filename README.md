# task3
DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f9;
        }

        .calculator {
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            width: 300px;
        }

        .display {
            width: 100%;
            height: 50px;
            margin-bottom: 20px;
            padding: 10px;
            font-size: 1.2rem;
            text-align: right;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .button {
            padding: 15px;
            font-size: 1rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #007bff;
            color: white;
            transition: background 0.3s;
        }

        .button:hover {
            background-color: #0056b3;
        }

        .button.clear {
            background-color: #dc3545;
        }

        .button.clear:hover {
            background-color: #a71d2a;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="result" class="display" disabled>
        <div class="buttons">
            <button class="button" onclick="appendValue('7')">7</button>
            <button class="button" onclick="appendValue('8')">8</button>
            <button class="button" onclick="appendValue('9')">9</button>
            <button class="button" onclick="appendValue('/')">/</button>

            <button class="button" onclick="appendValue('4')">4</button>
            <button class="button" onclick="appendValue('5')">5</button>
            <button class="button" onclick="appendValue('6')">6</button>
            <button class="button" onclick="appendValue('*')">*</button>

            <button class="button" onclick="appendValue('1')">1</button>
            <button class="button" onclick="appendValue('2')">2</button>
            <button class="button" onclick="appendValue('3')">3</button>
            <button class="button" onclick="appendValue('-')">-</button>

            <button class="button" onclick="appendValue('0')">0</button>
            <button class="button" onclick="appendValue('.')">.</button>
            <button class="button" onclick="calculateResult()">=</button>
            <button class="button" onclick="appendValue('+')">+</button>

            <button class="button clear" onclick="clearResult()">C</button>
        </div>
    </div>

    <script>
        function appendValue(value) {
            const result = document.getElementById('result');
            result.value += value;
        }

        function clearResult() {
            const result = document.getElementById('result');
            result.value = '';
        }

        function calculateResult() {
            const result = document.getElementById('result');
            try {
                result.value = eval(result.value);
            } catch (error) {
                result.value = 'Error';
            }
        }
    </script>
</body>
</html>
