<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tip Calculator</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f2f2f2;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }
    .container {
        background-color: #fff;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        text-align: center;
    }
    h2 {
        margin-top: 0;
        color: #333;
    }
    label {
        display: block;
        margin-bottom: 5px;
        color: #666;
    }
    input[type="number"] {
        width: 150px;
        padding: 8px;
        margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }
    button {
        padding: 10px 20px;
        background-color: #007bff;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }
    button:hover {
        background-color: #0056b3;
    }
    #result {
        margin-top: 20px;
        font-size: 18px;
        color: #333;
    }
</style>
</head>
<body>

<div class="container">
    <h2>Tip Calculator</h2>
    <form id="tipForm">
        <label for="bill">Total Bill Amount (₹):</label>
        <input type="number" id="bill" name="bill" min="0" step="0.01" required>
        <label for="serviceQuality">Service Quality (1-5):</label>
        <input type="number" id="serviceQuality" name="serviceQuality" min="1" max="5" required>
        <label for="numberOfPeople">Number of People:</label>
        <input type="number" id="numberOfPeople" name="numberOfPeople" min="1" required>
        <button type="button" onclick="calculateTip()">Calculate Tip</button>
    </form>
    <div id="result"></div>
</div>

<script>
function calculateTip() {
    var bill = parseFloat(document.getElementById("bill").value);
    var serviceQuality = parseInt(document.getElementById("serviceQuality").value);
    var numberOfPeople = parseInt(document.getElementById("numberOfPeople").value);
    
    var tipPerPerson = (bill * (serviceQuality / 100)) / numberOfPeople;
    
    var resultElement = document.getElementById("result");
    resultElement.innerHTML = "Tip per person: ₹" + tipPerPerson.toFixed(2);
}
</script>

</body>
</html>
