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

    .error {
      background: #ffebee;
      color: #c62828;
      border: 1px solid #ffcdd2;
    }
  </style>
  <div class="calculator-container">
    <h1>Old Mutual Tax Calculator</h1>
    <label for="country">Select Country:</label>
    <select id="country">
      <option value="za">South Africa</option>
      <option value="na">Namibia</option>
      <option value="zw">Zimbabwe</option>
    </select>
    <label for="income">Annual Income:</label>
    <input type="number" id="income" placeholder="Enter income (e.g. 500000)" />
    <button onclick="calculateTax()">Calculate Tax</button>
    <div id="result" class="result" style="display:none;"></div>
  </div>

  <script>
    function calculateTax() {
      const income = parseFloat(document.getElementById("income").value);
      const country = document.getElementById("country").value;
      const resultEl = document.getElementById("result");

      if (isNaN(income) || income < 0) {
        resultEl.textContent = "❌ Please enter a valid income.";
        resultEl.className = "result error";
        resultEl.style.display = "block";
        return;
      }

      let tax = 0;
      let currency = '';

      switch (country) {
        case "za": // South Africa
          currency = 'ZAR';
          if (income <= 237100) tax = income * 0.18;
          else if (income <= 370500) tax = 42678 + (income - 237100) * 0.26;
          else if (income <= 512800) tax = 77362 + (income - 370500) * 0.31;
          else if (income <= 673000) tax = 121475 + (income - 512800) * 0.36;
          else if (income <= 857900) tax = 179147 + (income - 673000) * 0.39;
          else if (income <= 1817000) tax = 251258 + (income - 857900) * 0.41;
          else tax = 644489 + (income - 1817000) * 0.45;
          break;

        case "na": // Namibia
          currency = 'NAD';
          if (income <= 100000) tax = 0;
          else if (income <= 150000) tax = (income - 100000) * 0.18;
          else if (income <= 350000) tax = 9000 + (income - 150000) * 0.25;
          else if (income <= 550000) tax = 59000 + (income - 350000) * 0.28;
          else if (income <= 850000) tax = 115000 + (income - 550000) * 0.30;
          else if (income <= 1550000) tax = 205000 + (income - 850000) * 0.32;
          else tax = 429000 + (income - 1550000) * 0.37;
          break;

        case "zw": // Zimbabwe
          currency = 'USD';
          if (income <= 1200) tax = 0;
          else if (income <= 3600) tax = (income - 1200) * 0.20;
          else if (income <= 12000) tax = 480 + (income - 3600) * 0.25;
          else if (income <= 24000) tax = 2730 + (income - 12000) * 0.30;
          else if (income <= 36000) tax = 6330 + (income - 24000) * 0.35;
          else tax = 10530 + (income - 36000) * 0.40;
          tax += tax * 0.03; // AIDS levy 3%
          break;
      }

      resultEl.textContent = `✅ Estimated Tax Payable: ${currency} ${tax.toFixed(2)}`;
      resultEl.className = "result";
      resultEl.style.display = "block";
    }
  </script>
