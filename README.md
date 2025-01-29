<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rastreamento de Produto - @tukarth</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f9f9f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        .tracking-container {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
            max-width: 600px;
            width: 100%;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .tracking-step {
            display: flex;
            align-items: center;
            margin: 20px 0;
        }
        .step-circle {
            background-color: #4CAF50;
            color: white;
            width: 40px;
            height: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 50%;
            font-weight: bold;
        }
        .step-info {
            margin-left: 15px;
        }
        .step-title {
            font-weight: bold;
            color: #333;
        }
        .step-date {
            font-size: 0.9em;
            color: #777;
        }
    </style>
</head>
<body>
    <div class="tracking-container">
        <h1>Rastreamento de Pedido - @tukarth</h1>

        <div class="tracking-step">
            <div class="step-circle">1</div>
            <div class="step-info">
                <div class="step-title">Pedido Confirmado</div>
                <div class="step-date">Data: 25/01/2025</div>
            </div>
        </div>

        <div class="tracking-step">
            <div class="step-circle">2</div>
            <div class="step-info">
                <div class="step-title">Em Processamento</div>
                <div class="step-date">Data: 26/01/2025</div>
            </div>
        </div>

        <div class="tracking-step">
            <div class="step-circle">3</div>
            <div class="step-info">
                <div class="step-title">Produto Despachado</div>
                <div class="step-date">Data: 27/01/2025</div>
            </div>
        </div>

        <div class="tracking-step">
            <div class="step-circle">4</div>
            <div class="step-info">
                <div class="step-title">Saiu para Entrega</div>
                <div class="step-date">Data: 28/01/2025</div>
            </div>
        </div>

        <div class="tracking-step">
            <div class="step-circle">5</div>
            <div class="step-info">
                <div class="step-title">Entregue</div>
                <div class="step-date">Data: 29/01/2025</div>
            </div>
        </div>
    </div>
</body>
</html>



