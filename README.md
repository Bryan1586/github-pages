<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="robots" content="noindex">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Acceso restringido</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 40px;
            background-color: #f0f0f0;
        }
        .contenido {
            display: none;
            margin-top: 30px;
        }
        .imagen {
            width: 200px;
            margin: 10px;
            border-radius: 12px;
        }
        input[type="text"] {
            padding: 8px;
            margin: 10px;
            width: 300px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="preguntas">
        <p>¿Cuál es mi apodo?</p>
        <input type="text" id="respuesta1"><br>

        <p>¿Cuál es tu apodo?</p>
        <input type="text" id="respuesta2"><br>

        <p><em>Si tú eres la persona correcta, sabrás que responder</em></p>

        <button onclick="verificarRespuestas()">Verificar</button>
    </div>

    <div id="contenido" class="contenido">
        <h2>Vuelve cuando realmente me quieras</h2>
        <h3>Quizás no sea muy tarde</h3>

        <div>
            <a href="https://www.youtube.com/watch?v=yKNxeF4KMsY" target="_blank">
                <img class="imagen" src="https://img.youtube.com/vi/yKNxeF4KMsY/0.jpg" alt="Yellow">
            </a>
            <a href="https://www.youtube.com/watch?v=RB-RcX5DS5A" target="_blank">
                <img class="imagen" src="https://img.youtube.com/vi/RB-RcX5DS5A/0.jpg" alt="The Scientist">
            </a>
            <a href="https://www.youtube.com/watch?v=k4V3Mo61fJM" target="_blank">
                <img class="imagen" src="https://img.youtube.com/vi/k4V3Mo61fJM/0.jpg" alt="Fix You">
            </a>
        </div>
    </div>

    <script>
        function verificarRespuestas() {
            const r1 = document.getElementById("respuesta1").value.toLowerCase().trim();
            const r2 = document.getElementById("respuesta2").value.toLowerCase().trim();
            const valido1 = (r1 === "ryan");
            const valido2 = (r2 === "lunita" || r2 === "cielito");

            if (valido1 && valido2) {
                document.getElementById("contenido").style.display = "block";
                document.getElementById("preguntas").style.display = "none";  // Elimina las preguntas después de respuestas correctas
            } else {
                alert("Respuestas incorrectas. No puedes acceder al contenido.");
            }
        }
    </script>
</body>
</html>
