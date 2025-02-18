<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cuestionario</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            background: linear-gradient(135deg, #f0f0f0, #e0e0e0);
            color: #333;
            text-align: center;
            padding: 20px;
            margin: 0;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            position: relative;
        }
        .page {
            display: none;
            animation: fadeIn 0.5s;
            background: rgba(255, 255, 255, 0.9);
            padding: 20px; /* Menos padding para más espacio */
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 90%;
            position: relative;
            overflow: hidden;
            margin: 20px;
            z-index: 2;
        }
        .page.active {
            display: block;
        }
        h1 {
            font-size: 1.8em; /* Tamaño de fuente más pequeño */
            margin-bottom: 15px; /* Menos margen */
            color: #555;
        }
        p {
            font-size: 1em; /* Tamaño de fuente más pequeño */
            line-height: 1.6;
            color: #555;
            margin-bottom: 20px; /* Menos margen */
        }
        .options {
            display: flex;
            flex-direction: column;
            gap: 10px; /* Menos espacio entre opciones */
            margin-bottom: 20px; /* Menos margen */
        }
        .options label {
            display: flex;
            align-items: center;
            background: #f9f9f9;
            padding: 10px; /* Menos padding */
            border-radius: 10px;
            cursor: pointer;
            transition: background 0.3s ease;
        }
        .options label:hover {
            background: #e0e0e0;
        }
        .options input {
            margin-right: 10px;
        }
        .buttons {
            display: flex;
            justify-content: center;
            gap: 15px; /* Menos espacio entre botones */
            margin-top: 15px; /* Menos margen */
        }
        .buttons button {
            font-size: 1em; /* Tamaño de fuente más pequeño */
            padding: 10px 15px; /* Menos padding */
            border: none;
            border-radius: 10px;
            cursor: pointer;
            background: #555;
            color: white;
            transition: background 0.3s ease, transform 0.3s ease;
        }
        .buttons button:hover {
            background: #333;
            transform: scale(1.1);
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>

    <!-- Página de introducción -->
    <div class="page active" id="introduccion">
        <h1>Hola...</h1>
        <p>
            Quería hacer esto de una manera diferente. A veces, cuando hablamos en mensajes, no siempre es fácil ser totalmente sinceros o directos. Así que hice esto para que puedas responder con toda la confianza del mundo. No hay respuestas incorrectas, solo quiero saber qué piensas. Tómate tu tiempo y responde lo que realmente sientas.
        </p>
        <div class="buttons">
            <button onclick="nextPage(1)">Comenzar</button>
        </div>
    </div>

    <!-- Página 1 -->
    <div class="page" id="page1">
        <h1>¿Te molesta o incomoda que te escriba?</h1>
        <div class="options">
            <label>
                <input type="radio" name="pregunta1" value="No, me gusta que lo hagas">
                No, me gusta que lo hagas
            </label>
            <label>
                <input type="radio" name="pregunta1" value="A veces, cuando es muy seguido">
                A veces, cuando es muy seguido
            </label>
            <label>
                <input type="radio" name="pregunta1" value="Sí, prefiero que no lo hagas">
                Sí, prefiero que no lo hagas
            </label>
        </div>
        <div class="buttons">
            <button onclick="nextPage(2)">Siguiente</button>
        </div>
    </div>

    <!-- Página 2 -->
    <div class="page" id="page2">
        <h1>¿Te agrado más allá de una amistad?</h1>
        <div class="options">
            <label>
                <input type="radio" name="pregunta2" value="Sí, me llamas la atención">
                Sí, me llamas la atención
            </label>
            <label>
                <input type="radio" name="pregunta2" value="No, solo te veo como amigo">
                No, solo te veo como amigo
            </label>
            <label>
                <input type="radio" name="pregunta2" value="No lo sé, no lo he pensado bien">
                No lo sé, no lo he pensado bien
            </label>
        </div>
        <div class="buttons">
            <button onclick="prevPage(1)">Anterior</button>
            <button onclick="nextPage(3)">Siguiente</button>
        </div>
    </div>

    <!-- Página 3 -->
    <div class="page" id="page3">
        <h1>¿Te incomodaría que te hablara en persona en la prepa?</h1>
        <div class="options">
            <label>
                <input type="radio" name="pregunta3" value="No, me gustaría que lo hicieras">
                No, me gustaría que lo hicieras
            </label>
            <label>
                <input type="radio" name="pregunta3" value="No me incomodaría, pero prefiero que sigamos como estamos">
                No me incomodaría, pero prefiero que sigamos como estamos
            </label>
            <label>
                <input type="radio" name="pregunta3" value="Sí, preferiría que no">
                Sí, preferiría que no
            </label>
        </div>
        <div class="buttons">
            <button onclick="prevPage(2)">Anterior</button>
            <button onclick="nextPage(4)">Siguiente</button>
        </div>
    </div>

    <!-- Página 4 (Última pregunta) -->
    <div class="page" id="page4">
        <h1>¿Qué piensas sobre intentar algo más que una amistad?</h1>
        <div class="options">
            <label>
                <input type="radio" name="pregunta4" value="Me gustaría intentarlo">
                Me gustaría intentarlo
            </label>
            <label>
                <input type="radio" name="pregunta4" value="Prefiero que sigamos siendo amigos">
                Prefiero que sigamos siendo amigos
            </label>
            <label>
                <input type="radio" name="pregunta4" value="No estoy segura, necesito pensarlo mejor">
                No estoy segura, necesito pensarlo mejor
            </label>
        </div>
        <div class="buttons">
            <button onclick="prevPage(3)">Anterior</button>
            <button onclick="enviarRespuestas()">Enviar</button>
        </div>
    </div>

    <!-- Página de agradecimiento -->
    <div class="page" id="gracias">
        <h1>¡Gracias por responder!</h1>
        <p>Tus respuestas han sido enviadas. 😊</p>
    </div>

    <script>
        function nextPage(pageNumber) {
            // Oculta la página actual
            document.querySelector('.page.active').classList.remove('active');
            // Muestra la siguiente página
            document.getElementById('page' + pageNumber).classList.add('active');
        }

        function prevPage(pageNumber) {
            // Oculta la página actual
            document.querySelector('.page.active').classList.remove('active');
            // Muestra la página anterior
            document.getElementById('page' + pageNumber).classList.add('active');
        }

        function enviarRespuestas() {
            const respuestas = {
                pregunta1: document.querySelector('input[name="pregunta1"]:checked')?.value,
                pregunta2: document.querySelector('input[name="pregunta2"]:checked')?.value,
                pregunta3: document.querySelector('input[name="pregunta3"]:checked')?.value,
                pregunta4: document.querySelector('input[name="pregunta4"]:checked')?.value,
            };

            // Enviar respuestas a los 4 formularios de Formspree
            enviarRespuestaFormspree("https://formspree.io/f/xyzkbova", respuestas.pregunta1);
            enviarRespuestaFormspree("https://formspree.io/f/xzzdkowl", respuestas.pregunta2);
            enviarRespuestaFormspree("https://formspree.io/f/xeoepndy", respuestas.pregunta3);
            enviarRespuestaFormspree("https://formspree.io/f/movjprza", respuestas.pregunta4);

            // Mostrar la página de agradecimiento
            document.querySelector('.page.active').classList.remove('active');
            document.getElementById('gracias').classList.add('active');
        }

        function enviarRespuestaFormspree(url, respuesta) {
            const correo = "emmanuel07salinas@gmail.com";
            const asunto = "Respuesta del cuestionario";
            const cuerpo = `La respuesta fue: ${respuesta}`;

            // Usar Formspree para enviar el correo
            fetch(url, {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                },
                body: JSON.stringify({
                    email: correo,
                    subject: asunto,
                    message: cuerpo,
                }),
            })
            .then(response => {
                if (!response.ok) {
                    console.error("Error al enviar la respuesta.");
                }
            })
            .catch(error => {
                console.error("Error:", error);
            });
        }
    </script>

</body>
</html>
