<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Calculadora</title>
</head>
<body>
  <div id="font-buttons">
    <button onclick="adjustFontSize(1)">Aumentar fonte</button>
    <button onclick="adjustFontSize(-1)">Diminuir fonte</button>
  </div>

  <div id="header">Calculadora Simples</div>

  <button onclick="calcular()">Calcular</button>

  <div id="resultado"></div>

  <script>
    let currentFontSize = 24;

    function adjustFontSize(change) {
      currentFontSize += change;
      document.getElementById("header").style.fontSize = currentFontSize + "px";
      document.getElementById("resultado").style.fontSize = currentFontSize + "px";
    }

    function calcular() {
      const valor1 = parseFloat(prompt("Digite o primeiro valor:"));
      const valor2 = parseFloat(prompt("Digite o segundo valor:"));
      const operacao = prompt("Digite a operação (+, -, *, /):");

      let resultado;

      switch (operacao) {
        case "+":
          resultado = valor1 + valor2;
          break;
        case "-":
          resultado = valor1 - valor2;
          break;
        case "*":
          resultado = valor1 * valor2;
          break;
        case "/":
          resultado = valor2 !== 0 ? valor1 / valor2 : "Erro: divisão por zero";
          break;
        default:
          resultado = "Operação inválida!";
      }

      document.getElementById("resultado").innerText = "Resultado: " + resultado;
    }
  </script>
</body>
</html>
