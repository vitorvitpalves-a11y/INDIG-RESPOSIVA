<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alemão do Grau</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }
        
        body {
            background: #0b0b0b;
            color: #fff;
        }
        
        header {
            background: #000;
            padding: 15px 0;
            box-shadow: 0 0 20px #25D366;
        }
        
        .navbar {
            max-width: 1000px;
            margin: auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .navbar h1 {
            color: #25D366;
        }
        
        .navbar ul {
            list-style: none;
            display: flex;
            gap: 20px;
        }
        
        .navbar a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
        }
        
        .navbar a:hover {
            color: #25D366;
        }
        
        .section {
            max-width: 900px;
            margin: 40px auto;
            background: #111;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 15px #25D366;
        }
        
        h2 {
            margin-bottom: 15px;
            color: #25D366;
        }
        
        form {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        input,
        textarea {
            padding: 12px;
            border-radius: 5px;
            border: none;
            outline: none;
        }
        /* BOTÃO WHATSAPP STREET */
        
        .btn-whatsapp {
            background: #000;
            color: #25D366;
            border: 2px solid #25D366;
            padding: 16px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            text-transform: uppercase;
            box-shadow: 0 0 20px #25D366;
            transition: 0.3s;
        }
        
        .btn-whatsapp:hover {
            background: #25D366;
            color: #000;
            box-shadow: 0 0 10px #25D366, 0 0 30px #25D366, 0 0 60px #25D366;
            transform: scale(1.05);
        }
        /* PULSAR */
        
        .pulse {
            animation: pulse 1.5s infinite;
        }
        
        @keyframes pulse {
            0% {
                box-shadow: 0 0 10px #25D366;
            }
            50% {
                box-shadow: 0 0 30px #25D366;
            }
            100% {
                box-shadow: 0 0 10px #25D366;
            }
        }
        
        .icone {
            font-size: 20px;
        }
        
        .msg-sucesso {
            display: none;
            margin-top: 15px;
            text-align: center;
            color: #25D366;
            font-weight: bold;
        }
        
        footer {
            text-align: center;
            padding: 15px;
            background: #000;
            color: #aaa;
        }
    </style>
</head>

<body>

    <header>
        <nav class="navbar">
            <h1>Alemão do Grau</h1>
            <ul>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>

    <section id="sobre" class="section">
        <h2>Sobre</h2>
        <p>Alemão bota pra respeitar 😎🔥</p>
    </section>

    <section id="contato" class="section">
        <h2>Contato</h2>

        <form id="formContato">
            <label for="nome">Nome</label>
            <input type="text" id="nome" required>

            <label for="mensagem">Mensagem</label>
            <textarea id="mensagem" required></textarea>

            <button type="submit" class="btn-whatsapp pulse">
                <span class="icone">📱</span> Enviar no WhatsApp
            </button>

            <p id="msgSucesso" class="msg-sucesso">
                Mensagem enviada com sucesso! ✅
            </p>
        </form>
    </section>

    <footer>
        <p>© Todos os direitos reservados</p>
    </footer>

    <!-- SOM -->
    <audio id="somClick">
        <source src="click.mp3" type="audio/mpeg">
    </audio>

    <!-- SCRIPT -->
    <script>
        const form = document.getElementById("formContato");
        const msg = document.getElementById("msgSucesso");
        const som = document.getElementById("somClick");

        form.addEventListener("submit", function(e) {
            e.preventDefault();

            const nome = document.getElementById("nome").value;
            const mensagem = document.getElementById("mensagem").value;

            som.play();
            msg.style.display = "block";

            const numero = "5511934406051";
            const texto = `Olá, Alemão`;
            const link = `https://wa.me/${numero}?text=${encodeURIComponent(texto)}`;

            setTimeout(() => {
                window.open(link, "_blank");
                form.reset();
            }, 800);
        });
    </script>
