# Joc-<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aventura Economică</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        .card { width: 300px; margin: auto; padding: 20px; border-radius: 10px; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); }
        button { width: 100%; padding: 10px; margin: 5px 0; border: none; border-radius: 5px; cursor: pointer; }
        .save { background-color: green; color: white; }
        .spend { background-color: red; color: white; }
        .invest { background-color: blue; color: white; }
    </style>
</head>
<body>
    <div class="card">
        <h2 id="message">Bine ai venit! Începe aventura ta financiară.</h2>
        <p id="money">Monede: 100</p>
        <button class="save" onclick="handleAction('save')">Economisește</button>
        <button class="spend" onclick="handleAction('spend')">Cheltuiește</button>
        <button class="invest" onclick="handleAction('invest')">Investește</button>
    </div>

    <script>
        let money = 100;
        function handleAction(action) {
            let message = "";
            if (action === "save") {
                money += 20;
                message = "Ai economisit 20 de monede!";
            } else if (action === "spend") {
                if (money >= 10) {
                    money -= 10;
                    message = "Ai cheltuit 10 monede.";
                } else {
                    message = "Nu ai suficiente monede!";
                }
            } else if (action === "invest") {
                money = Math.floor(money * 1.2);
                message = "Investiția ta a avut succes! Ai câștigat 20% în plus.";
            }
            document.getElementById("message").innerText = message;
            document.getElementById("money").innerText = "Monede: " + money;
        }
    </script>
</body>
</html>
