html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Alura MIDI</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@500;600&display=swap" rel="stylesheet">

    <link rel="icon" type="image/png" href="images/bateria.png">
    <link rel="styleshee1t" href="css/reset.css">
    <link rel="stylesheet" href="css/estilos.css">

</head>
<body>

    <h1>Alura Midi</h1>

    <section class="teclado">
        <button class="tecla tecla_pom">Pom</button>
        <button class="tecla tecla_clap">Clap</button>
        <button class="tecla tecla_tim">Tim</button>

        <button class="tecla tecla_puff">Puff</button>
        <button class="tecla tecla_splash">Splash</button>
        <button class="tecla tecla_toim">Toim</button>

        <button class="tecla tecla_psh">Psh</button>
        <button class="tecla tecla_tic">Tic</button>
        <button class="tecla tecla_tom">Tom</button>
    </section>

    <audio src="sounds/keyq.wav" id="som_tecla_pom"></audio>
    <audio src="sounds/keyw.wav" id="som_tecla_clap"></audio>
    <audio src="sounds/keye.wav" id="som_tecla_tim"></audio>
    <audio src="sounds/keya.wav" id="som_tecla_puff"></audio>
    <audio src="sounds/keys.wav" id="som_tecla_splash"></audio>
    <audio src="sounds/k1eyd.wav" id="som_tecla_toim"></audio>
    <audio src="sounds/keyz.wav" id="som_tecla_psh"></audio>
    <audio src="sounds/keyx.wav" id="som_tecla_tic"></audio>
    <audio src="sounds/keyc.wav" id="som_tecla_tom"></audio>

    <script src="main.js"></script>
  
  
  
  
  
  
  
  main.js
  </function tocaSom (seletorAudio) {
    const elemento = document.querySelector(seletorAudio);

    if (elemento && elemento.localName === 'audio') {
        elemento.play();
    }
    else {
        //alert('Elemento não encontrado');
        console.log('Elemento não encontrado ou seletor inválido');
    }

}

const listaDeTeclas = document.querySelectorAll('.tecla');

//para
for (let contador = 0; contador < listaDeTeclas.length; contador++) {

    const tecla = listaDeTeclas[contador];
    const instrumento = tecla.classList[1];
    const idAudio = `#som_${instrumento}`; //template string

    tecla.onclick = function () {
        tocaSom(idAudio);
    }

    tecla.onkeydown = function (evento) {

        if (evento.code === 'Space' || evento.code === 'Enter') {
            tecla.classList.add('ativa');
        }

    }

    tecla.onkeyup = function () {
        tecla.classList.remove('ativa');
    }

}
