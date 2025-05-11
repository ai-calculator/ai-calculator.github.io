---
layout: tool
title:  Old Mutual Tax Calculator
tags:   [Old Mutual Tax Calculator]
category: [Tax Calculator]
---

  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 500px;
      margin: auto;
      padding: 20px;
    }
    label, select, input {
      display: block;
      margin-bottom: 10px;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
  <label for="country">Select Country:</label>
  <select id="country">
    <option value="za">South Africa</option>
    <option value="na">Namibia</option>
    <option value="zw">Zimbabwe</option>
  </select>
  
  <label for="income">Enter Annual Income:</label>
  <input type="number" id="income" placeholder="e.g. 500000" />

  <button onclick="calculateTax()">Calculate Tax</button>
  
  <div class="result" id="result"></div>
<script>
    function calculateTax() {
  const income = parseFloat(document.getElementById("income").value);
  const country = document.getElementById("country").value;
  const resultEl = document.getElementById("result");
  if (isNaN(income) || income < 0) {
    resultEl.textContent = "Please enter a valid income.";
    return;
  }
  let tax = 0;
  switch (country) {
    case "za": // South Africa (Simplified example)
      tax = income <= 226000 ? 0 : income * 0.18;
      break;
    case "na": // Namibia (Simplified example)
      tax = income <= 50000 ? 0 : income * 0.20;
      break;
    case "zw": // Zimbabwe (Simplified example)
      tax = income <= 120000 ? 0 : income * 0.25;
      break;
    default:
      resultEl.textContent = "Country not supported.";
      return;
  }
  resultEl.textContent = `Estimated Tax: ${tax.toLocaleString('en-ZA', { style: 'currency', currency: 'ZAR' })}`;
}
</script>
