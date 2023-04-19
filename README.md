<!DOCTYPE html>
<html>
  <head>
    <title>BMI 計算機</title>
    <style>
      .overweight {
        color: red;
      }

      .normal {
        color: green;
      }

      .underweight {
        color: blue;
      }
    </style>
  </head>
  <body>
    <h1>BMI 計算機</h1>
    <label for="height">身高 (公分):</label>
    <input type="number" id="height" name="height"><br>
    <label for="weight">體重 (公斤):</label>
    <input type="number" id="weight" name="weight"><br>
    <button id="calculate">計算 BMI</button>
    <p><span style="color: black;">您的 BMI 為:</span> <span id="bmi" style="color: black;"></span></p>
    <p><span style="color: black;">評估結果:</span> <span id="result"></span></p>
    <script>
      const heightInput = document.getElementById("height");
      const weightInput = document.getElementById("weight");
      const bmiOutput = document.getElementById("bmi");
      const resultOutput = document.getElementById("result");
      const calculateButton = document.getElementById("calculate");

      function updateBMI() {
        const height = parseFloat(heightInput.value);
        const weight = parseFloat(weightInput.value);
        const bmi = calculateBMIValue(height, weight);
        bmiOutput.textContent = bmi.toFixed(2);
        showResult(bmi);
      }

      function calculateBMIValue(height, weight) {
        const heightInMeter = height / 100;
        const bmi = weight / (heightInMeter * heightInMeter);
        return bmi;
      }

      function showResult(bmi) {
        if (bmi < 18.5) {
          resultOutput.textContent = "過輕";
          resultOutput.className = "underweight";
        } else if (bmi < 25) {
          resultOutput.textContent = "剛好";
          resultOutput.className = "normal";
        } else {
          resultOutput.textContent = "過重";
          resultOutput.className = "overweight";
        }
      }

      calculateButton.addEventListener("click", updateBMI);
    </script>
  </body>
</html>
