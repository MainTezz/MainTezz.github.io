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
    transition: background-color 0.3s ease-in-out;
  }

  #playButton {
    padding: 10px 20px;
    font-size: 18px;
    background-color: #4caf50;
    color: white;
    border: none;
    cursor: pointer;
    margin-bottom: 20px;
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

    character.addEventListener('click', () => {
      if (!isPlaying) {
        changeCharacterColor();
      }
    });

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
        const newPositionX = Math.random() * (window.innerWidth - 50);
        const newPositionY = Math.random() * (window.innerHeight - 50);
        character.style.left = newPositionX + 'px';
        character.style.top = newPositionY + 'px';
        setTimeout(moveCharacter, 1000);
      }
    }

    function changeCharacterColor() {
      const colors = ['#ff6347', '#66cc99', '#ff9900', '#3366ff', '#9933cc'];
      const randomColor = colors[Math.floor(Math.random() * colors.length)];
      character.style.backgroundColor = randomColor;
    }
  </script>
</body>
</html>
