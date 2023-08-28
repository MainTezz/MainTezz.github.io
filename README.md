<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Customizable Character</title>
<style>
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
  }
  
  #character {
    width: 50px;
    height: 50px;
    background-color: blue;
    position: relative;
  }

  #playButton {
    padding: 10px 20px;
    font-size: 18px;
    background-color: #4caf50;
    color: white;
    border: none;
    cursor: pointer;
  }
</style>
</head>
<body>
  <div id="character"></div>
  <button id="playButton">Play</button>

  <script>
    const character = document.getElementById('character');
    const playButton = document.getElementById('playButton');
    let isPlaying = false;

    playButton.addEventListener('click', () => {
      if (!isPlaying) {
        isPlaying = true;
        playButton.innerText = 'Stop';
        moveCharacter();
      } else {
        isPlaying = false;
        playButton.innerText = 'Play';
      }
    });

    function moveCharacter() {
      if (isPlaying) {
        const newPosition = Math.random() * 200;
        character.style.left = newPosition + 'px';
        character.style.top = newPosition + 'px';
        setTimeout(moveCharacter, 1000);
      }
    }
  </script>
</body>
</html>
