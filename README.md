<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Reproductor YouTube</title>
  <style>
    #player {
      display: none; /* Ocultamos el video */
    }
  </style>
</head>
<body>

<h1>🎵 Reproductor de sonido</h1>
<button onclick="play()">▶️ Reproducir</button>
<button onclick="pause()">⏸️ Pausar</button>

<!-- Iframe oculto -->
<div id="player"></div>

<script>
  let player;

  // Carga el API de YouTube
  const tag = document.createElement('script');
  tag.src = "https://www.youtube.com/iframe_api";
  document.head.appendChild(tag);

  // Se llama automáticamente cuando el API se carga
  function onYouTubeIframeAPIReady() {
    player = new YT.Player('player', {
      height: '0',
      width: '0',
      videoId: '6y7goU0h8sY', // ID del video
      playerVars: {
        autoplay: 0,
        controls: 0,
        loop: 1,
        playlist: '6y7goU0h8sY'
      },
      events: {
        'onReady': () => console.log('Listo')
      }
    });
  }

  function play() {
    if (player) player.playVideo();
  }

  function pause() {
    if (player) player.pauseVideo();
  }
</script>

</body>
</html>
