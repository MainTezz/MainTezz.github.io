<!DOCTYPE html>
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
  <p>Loading<span id="loadingDots">...</span></p>
</div>
<script>
  const playButton = document.getElementById('playButton');
  const overlay = document.getElementById('overlay');
  const popup = document.getElementById('popup');
  const loadingDots = document.getElementById('loadingDots');
  let dotsInterval;

  playButton.addEventListener('click', () => {
    overlay.style.display = 'block';
    popup.style.display = 'block';
    loadingDots.innerHTML = '...';

    dotsInterval = setInterval(() => {
      if (loadingDots.innerHTML.length >= 5) {
        loadingDots.innerHTML = '';
      } else {
        loadingDots.innerHTML += '.';
      }
    }, 500); // Change this value to adjust the speed of the moving dots

    // Simulate loading
    setTimeout(() => {
      overlay.style.display = 'none';
      popup.style.display = 'none';
      clearInterval(dotsInterval);
    }, 3000); // Change this value to control how long the loading message appears
  });
</script>
</body>
</html>
