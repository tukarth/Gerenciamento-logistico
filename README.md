<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Logística - Sistema Completo</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 1.5rem;
            text-align: center;
            position: relative;
        }
        .clock {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 1rem;
            font-weight: bold;
        }
        nav {
            background-color: #0056b3;
            padding: 1rem;
            text-align: center;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }
        main {
            padding: 2rem;
            text-align: center;
        }
        .button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .form-container {
            background-color: white;
            padding: 1.5rem;
            margin: 2rem auto;
            border-radius: 8px;
            width: 80%;
            max-width: 600px;
            box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
        }
        table {
            width: 100%;
            margin: 2rem auto;
            border-collapse: collapse;
        }
        th, td {
            padding: 10px;
            text-align: center;
            border: 1px solid #ddd;
        }
        th {
            background-color: #007bff;
            color: white;
        }
        footer {
            background-color: #007bff;
            color: white;
            text-align: center;
            padding: 1rem;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
    <script>
        // Função para atualizar o relógio
        function updateClock() {
            const now = new Date();
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');
            document.getElementById('clock').textContent = `${hours}:${minutes}:${seconds}`;
        }

        // Atualiza o relógio a cada segundo
        setInterval(updateClock, 1000);
        window.onload = updateClock;

        // Função para atualizar status
        function updateStatus() {
            const status = document.getElementById('status').value;
            const statusDiv = document.getElementById('statusDisplay');
            const now = new Date().toLocaleTimeString();
            statusDiv.innerHTML = `<p>Status atualizado em: ${now} - ${status}</p>`;
        }

        // Função para adicionar um novo relatório
        function addReport() {
            const reportDate = document.getElementById('reportDate').value;
            const reportStatus = document.getElementById('reportStatus').value;
            const table = document.getElementById('reportTable');
            const row = table.insertRow();
            const dateCell = row.insertCell(0);
            const statusCell = row.insertCell(1);
            dateCell.textContent = reportDate;
            statusCell.innerHTML = `<a href="https://www.correios.com.br" target="_blank">${reportStatus}</a>`;
        }

        // Função para redirecionar para o site dos Correios
        function redirectToCorreios() {
            window.open("https://www.correios.com.br", "_blank");
        }

        // Função para enviar um email sem abrir o cliente de email
        async function sendEmail() {
            const email = "arthur.oliveira99@cs.brazcubas.edu.br";
            const subject = "Contato pelo site Logística";
            const body = document.getElementById('message').value;
            const response = await fetch('https://api.example.com/send-email', { // Use um serviço de email API
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({
                    to: email,
                    subject: subject,
                    body: body,
                }),
            });
            if (response.ok) {
                alert("Mensagem enviada com sucesso! Entraremos em contato em breve.");
            } else {
                alert("Houve um problema ao enviar a mensagem. Tente novamente mais tarde.");
            }
        }

        // Função para simular envio de mensagem
        function sendMessage() {
            alert("Mensagem enviada com sucesso! Entraremos em contato em breve.");
        }
    </script>
</head>
<body>
    <header>
        <h1>Logística</h1>
        <div class="clock" id="clock"></div>
        <p>Gerenciamento logístico eficiente e dinâmico</p>
    </header>
    <nav>
        <a href="#">Página Inicial</a>
        <a href="#">Serviços</a>
        <a href="#" onclick="redirectToCorreios()">Correios</a>
        <a href="#">Contato</a>
    </nav>
    <main>
        <h2>Atualização de Status</h2>
        <div class="form-container">
            <input type="text" id="status" placeholder="Digite o novo status da entrega..." style="width: 80%; padding: 10px; margin-bottom: 10px;">
            <button class="button" onclick="updateStatus()">Atualizar Status</button>
        </div>
        <div id="statusDisplay" class="form-container">
            <p>Aguardando atualização...</p>
        </div>

        <h2>Relatórios Logísticos</h2>
        <div class="form-container">
            <input type="date" id="reportDate" style="padding: 10px; margin-bottom: 10px;">
            <input type="text" id="reportStatus" placeholder="Informe o status do relatório..." style="width: 80%; padding: 10px; margin-bottom: 10px;">
            <button class="button" onclick="addReport()">Adicionar Relatório</button>
        </div>
        <table id="reportTable">
            <thead>
                <tr>
                    <th>Data</th>
                    <th>Status (clique para detalhes)</th>
                </tr>
            </thead>
            <tbody>
                <!-- Relatórios vão aparecer aqui -->
            </tbody>
        </table>

        <h2>Contato</h2>
        <div class="form-container">
            <p>Envie-nos uma mensagem</p>
            <input type="email" placeholder="Seu email" style="width: 80%; padding: 10px; margin-bottom: 10px;"><br>
            <textarea id="message" placeholder="Sua mensagem..." style="width: 80%; padding: 10px; margin-bottom: 10px; height: 100px;"></textarea><br>
            <button class="button" onclick="sendEmail()">Enviar</button>
        </div>
    </main>
    <footer>
        <p>© 2025 @TUKARTH Logística. Todos os direitos reservados.</p>
    </footer>
</body>
</html>

