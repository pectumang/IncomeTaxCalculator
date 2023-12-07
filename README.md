<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Income Tax Calculator</title>

    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #3498db;
            text-align: center;
            color: white;
            margin: 50px;
        }

        h2, h3 {
            color: #fff;
        }

        label {
            font-size: 16px;
            margin-right: 10px;
            color: #fff;
            text-align: right; /* Align label text to the right */
        }

        input, button {
            padding: 10px;
            font-size: 16px;
            border: 1px solid #fff;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        input {
            text-align: left; /* Align input text to the left */
        }

        button {
            cursor: pointer;
        }

        button:hover {
            background-color: #2980b9;
        }

        #resultBox {
            padding: 10px;
            font-size: 18px;
            color: #3498db; /* Blue text */
            border: 1px solid #fff;
            border-radius: 5px;
            background-color: #fff; /* White background */
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h2>Income Tax Calculator</h2>

    <label for="incomeInput">Enter Taxable Income:</label>
    <br>
    <input type="number" id="incomeInput" min="0" step="1">
    <br>
    <button onclick="calculateIncomeTax()">Calculate</button>

    <div id="resultBox"></div>

    <script>
        function calculateIncomeTax() {
            const taxableIncome = parseFloat(document.getElementById('incomeInput').value);
            let incomeTax = 0;

            // Income tax calculation logic
            if (taxableIncome <= 250000) {
                incomeTax = 0;
            } else if (taxableIncome <= 400000) {
                incomeTax = 0.2 * (taxableIncome - 250000);
            } else if (taxableIncome <= 800000) {
                incomeTax = 30000 + 0.25 * (taxableIncome - 400000);
            } else if (taxableIncome <= 2000000) {
                incomeTax = 130000 + 0.3 * (taxableIncome - 800000);
            } else if (taxableIncome <= 8000000) {
                incomeTax = 490000 + 0.32 * (taxableIncome - 2000000);
            } else {
                incomeTax = 2410000 + 0.35 * (taxableIncome - 8000000);
            }

            // Display result in the result box with blue text
            const resultBox = document.getElementById('resultBox');
            resultBox.textContent = `Income Tax: P${incomeTax.toFixed(2)}`;
            resultBox.style.color = '#3498db'; // Blue text color
        }
    </script>

</body>
</html>



































































































































