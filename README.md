# Number-System-Conversion


To create a webpage for number system conversions, you can use HTML, CSS, and JavaScript. Below is an example of a simple webpage that allows users to convert numbers between binary, octal, decimal, and hexadecimal systems.

### HTML Code for Number System Conversion Webpage

1. **Create an HTML file (e.g., `index.html`) and add the following code:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number System Converter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
        input[type="text"], select {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 10px;
            border: none;
            background-color: #28a745;
            color: #fff;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Number System Converter</h2>
        <div class="form-group">
            <label for="number">Enter Number:</label>
            <input type="text" id="number" required>
        </div>
        <div class="form-group">
            <label for="base-from">From Base:</label>
            <select id="base-from">
                <option value="2">Binary (2)</option>
                <option value="8">Octal (8)</option>
                <option value="10">Decimal (10)</option>
                <option value="16">Hexadecimal (16)</option>
            </select>
        </div>
        <div class="form-group">
            <label for="base-to">To Base:</label>
            <select id="base-to">
                <option value="2">Binary (2)</option>
                <option value="8">Octal (8)</option>
                <option value="10">Decimal (10)</option>
                <option value="16">Hexadecimal (16)</option>
            </select>
        </div>
        <button onclick="convertNumber()">Convert</button>
        <div class="result" id="result">Result: </div>
    </div>

    <script>
        function convertNumber() {
            const number = document.getElementById('number').value;
            const baseFrom = parseInt(document.getElementById('base-from').value);
            const baseTo = parseInt(document.getElementById('base-to').value);

            try {
                const numberInDecimal = parseInt(number, baseFrom);

                let result;
                if (baseTo === 2) {
                    result = numberInDecimal.toString(2);
                } else if (baseTo === 8) {
                    result = numberInDecimal.toString(8);
                } else if (baseTo === 10) {
                    result = numberInDecimal.toString(10);
                } else if (baseTo === 16) {
                    result = numberInDecimal.toString(16).toUpperCase();
                } else {
                    throw new Error("Invalid base");
                }

                document.getElementById('result').innerText = `Result: ${result}`;
            } catch (error) {
                alert('Error: ' + error.message);
            }
        }
    </script>
</body>
</html>
```

### Explanation:

1. **HTML Structure:**
   - **Form Elements:** Includes input fields and dropdowns to enter the number and select the source and target bases.
   - **Button:** Triggers the conversion process.
   - **Result Display:** Shows the conversion result.

2. **CSS Styling:**
   - **Basic Styles:** Styles the webpage for a clean and modern look with responsive design elements.

3. **JavaScript Logic:**
   - **Conversion Function:** Takes the input number, source base, and target base, performs the conversion, and displays the result.
   - **Error Handling:** Displays an alert message if there's an error during conversion.

This code provides a simple, user-friendly interface for converting numbers between different bases directly in a web browser. You can further enhance it with additional features or more sophisticated UI elements as needed.
