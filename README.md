# Music-player
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Player</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        #player {
            margin: 20px;
        }

        audio {
            width: 100%;
            max-width: 400px;
        }

        button {
            margin: 5px;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div id="player">
    <audio id="audioPlayer" controls>
        <source src="your_audio_file.mp3" type="audio/mp3">
        Your browser does not support the audio element.
    </audio>
    <br>
    <button onclick="playPause()">Play/Pause</button>
    <button onclick="stop()">Stop</button>
    <br>
    Volume: <input type="range" id="volumeControl" min="0" max="1" step="0.1" value="1" oninput="setVolume()">
</div>

<script>
    const audioPlayer = document.getElementById('audioPlayer');
    const volumeControl = document.getElementById('volumeControl');

    function playPause() {
        if (audioPlayer.paused) {
            audioPlayer.play();
        } else {
            audioPlayer.pause();
        }
    }

    function stop() {
        audioPlayer.pause();
        audioPlayer.currentTime = 0;
    }

    function setVolume() {
        audioPlayer.volume = volumeControl.value;
    }
</script>

</body>
</html>