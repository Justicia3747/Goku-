<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Reproductor de audio</title>
  <style>
    /* Hacemos el iframe invisible */
    #yt-audio { display: none; }
  </style>
</head>
<body>

<h1>Reproduciendo audio desde YouTube Music</h1>
<button id="play-btn">▶️ Reproducir</button>
<button id="pause-btn">⏸️ Pausar</button>

<!-- Iframe oculto que carga el audio del video -->
<iframe
  id="yt-audio"
  src="https://www.youtube.com/embed/6y7goU0h8sY?autoplay=0&loop=1&playlist=6y7goU0h8sY"
  allow="autoplay"
></iframe>

<script>
// API de iframe de YouTube para controlar el reproductor
let player;

function onYouTubeIframeAPIReady() {
  player = new YT.Player('yt-audio');
}

// Carga el API asincrónicamente
const tag = document.createElement('script');
tag.src = "https://www.youtube.com/iframe_api";
document.head.appendChild(tag);

// Botones control
document.getElementById('play-btn').addEventListener('click', () => {
  if (player && player.playVideo) player.playVideo();
});
document.getElementById('pause-btn').addEventListener('click', () => {
  if (player && player.pauseVideo) player.pauseVideo();
});
</script>

</body>
</html>
