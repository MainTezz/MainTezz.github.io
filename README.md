<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>Game Menu</title>
</head>
<body>
  <div class="menu">
    <button id="playButton">Currently starting game!</button>
    <div class="option">
      <label for="musicSelect">Music:</label>
      <select id="musicSelect">
        <option value="soundtrack1">Soundtrack 1</option>
        <option value="soundtrack2">Soundtrack 2</option>
        <option value="soundtrack3">Soundtrack 3</option>
        <option value="customPlaylist">Custom Playlist</option>
      </select>
    </div>
    <div class="option">
      <label for="soundEffectSelect">Sound Effects:</label>
      <select id="soundEffectSelect">
        <option value="default">Default</option>
        <option value="cinematic">Cinematic</option>
        <option value="sciFi">Sci-Fi</option>
        <option value="customSet">Custom Set</option>
      </select>
    </div>
    <div class="option">
      <label for="masterVolume">Master Volume:</label>
      <input type="range" id="masterVolume" min="0" max="100" value="50">
    </div>
    <button id="controlsButton">Controls</button>
  </div>
  <script src="script.js"></script>
</body>
</html>
