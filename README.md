<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Popup Example</title>
<style>
  body {
    font-family: Arial, sans-serif;
  }
  .popup {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 20px;
    background-color: white;
    border: 1px solid #ccc;
    box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.1);
    z-index: 9999;
    text-align: center;
  }
  .overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 9998;
  }
  .button {
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
  }
</style>
</head>
<body>
<button class="button" id="playButton">Play</button>
<div class="overlay" id="overlay"></div>
<div class="popup" id="popup">
  <p>Loading<span id="loadingDots"></span></p>
</div>
<div id="player"></div>
<script>
  const playButton = document.getElementById('playButton');
  const overlay = document.getElementById('overlay');
  const popup = document.getElementById('popup');
  const loadingDots = document.getElementById('loadingDots');
  const playerDiv = document.getElementById('player');
  let dotsInterval;
  let isSongPlayed = false;

  playButton.addEventListener('click', () => {
    overlay.style.display = 'block';
    popup.style.display = 'block';
    loadingDots.innerHTML = '';

    dotsInterval = setInterval(() => {
      loadingDots.innerHTML += '.';
      if (loadingDots.innerHTML.length > 3) {
        loadingDots.innerHTML = '';
      }

      // Play the YouTube video after 10 seconds
      if (!isSongPlayed && loadingDots.innerHTML.length > 20) {
        isSongPlayed = true;
        clearInterval(dotsInterval);
        playerDiv.innerHTML = '<iframe width="560" height="315" src="https://www.youtube.com/embed/zXX0w0FKR_s?autoplay=1" frameborder="0" allowfullscreen></iframe>';
      }
    }, 500); // Change this value to adjust the speed of the moving dots
  });
</script>
</body>
</html>
