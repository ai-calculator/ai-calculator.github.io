---
layout: page
title:  Old Mutual Tax Calculator
description: "Quickly estimate your annual tax based on your income and country of residence. Select South Africa, Namibia, or Zimbabwe to get started."
tags:   [Old Mutual Tax Calculator]
category: [Tax Calculator]
image: '/images/Old-Mutual-Tax-Calculator.webp'
istool: true
---

  <style>
    .calculator-container {
      background: #ffffff;
      border-radius: 12px;
      padding: 30px;
      max-width: 400px;
      width: 100%;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
    }

    h1 {
      font-size: 22px;
      margin-bottom: 20px;
      text-align: center;
      color: #2c3e50;
    }

    label {
      font-weight: 600;
      margin-top: 15px;
      display: block;
      color: #333;
    }

    select, input {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
      box-sizing: border-box;
    }

    button {
      width: 100%;
      padding: 12px;
      margin-top: 20px;
      background-color: #007b5e;
      color: #fff;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #00664d;
    }

    .result {
      margin-top: 20px;
      padding: 10px;
      background: #e8f5e9;
      color: #2e7d32;
      border: 1px solid #c8e6c9;
      border-radius: 8px;
      font-weight: bold;
      text-align: center;
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
