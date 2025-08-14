# chat
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Preguntas para ti ❤️</title>
<style>
    body {
        font-family: 'Arial', sans-serif;
        text-align: center;
        background-color: #ffe6e6;
        margin: 0;
        padding: 20px;
    }
    h1 {
        color: #d63384;
    }
    .pregunta {
        background: white;
        padding: 20px;
        border-radius: 15px;
        box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        max-width: 400px;
        margin: auto;
        margin-top: 20px;
    }
    button {
        padding: 10px 20px;
        margin-top: 10px;
        font-size: 16px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        background-color: #ff4d6d;
        color: white;
        transition: background-color 0.3s;
    }
    button:hover {
        background-color: #d63384;
    }
</style>
</head>
<body>

<h1>💌 Preguntas para ti 💌</h1>
<div id="contenedor"></div>

<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<script>
    const preguntas = [
        "¿Cuál es tu color favorito?",
        "¿Qué es lo que más te gusta hacer?",
        "¿Te gusta pasar tiempo conmigo?"
    ];
    let indice = 0;
    const contenedor = document.getElementById("contenedor");

    function mostrarPregunta() {
        if (indice < preguntas.length) {
            contenedor.innerHTML = `
                <div class="pregunta">
                    <p>${preguntas[indice]}</p>
                    <input type="text" id="respuesta" style="padding:8px;width:80%;border-radius:8px;border:1px solid #ccc;">
                    <br>
                    <button onclick="guardarRespuesta()">Siguiente</button>
                </div>
            `;
        } else {
            contenedor.innerHTML = `
                <div class="pregunta">
                    <h2>Última pregunta 😏</h2>
                    <p>¿Quieres ser mi novia?</p>
                    <button onclick="aceptar()">Sí</button>
                    <button onclick="aceptar()">Claro que sí</button>
                </div>
            `;
        }
    }

    function guardarRespuesta() {
        const resp = document.getElementById("respuesta").value;
        if (resp.trim() === "") return alert("Por favor, responde 😄");
        indice++;
        mostrarPregunta();
    }

    function aceptar() {
        confetti();
        contenedor.innerHTML = `
            <h2>💖 ¡Sabía que dirías que sí! 💖</h2>
            <p>Me haces la persona más feliz del mundo 😍</p>
        `;
    }

    mostrarPregunta();
</script>

</body>
</html>

