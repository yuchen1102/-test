<!DOCTYPE html>
<html>
  <head>
    <title>10進制轉換成2進制</title>
  </head>
  <body>
    <label for="decimal-input">輸入10進制數字：</label>
    <input type="text" id="decimal-input" />
    <button onclick="convert()">轉換成2進制</button>
    <p id="binary-output"></p>
    <script>
      function convert() {
        const decimal = parseInt(document.getElementById("decimal-input").value);
        const binary = decimalToBinary(decimal);
        document.getElementById("binary-output").innerText = `2進制：${binary}`;
      }
      function decimalToBinary(decimal) {
        return (decimal >>> 0).toString(2);
      }
    </script>
  </body>
</html>
