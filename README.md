# bihari-bangers
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Bhojpuri Beats 🎵</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    color: white;
    min-height: 100vh;
    overflow-x: hidden;

    background:
        linear-gradient(rgba(30,20,10,.55), rgba(20,10,5,.75)),
        url("background.jpg");

    background-size: cover;
    background-position: center;
    background-attachment: fixed;
}

/* Dark glass overlay */
body::before {
    content: "";
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,.12);
    pointer-events: none;
    z-index: -1;
}

/* TOP BAR */

.topbar {
    position: fixed;
    top: 20px;
    left: 25px;
    right: 25px;

    display: flex;
    justify-content: space-between;
    align-items: center;

    z-index: 10;
}

.time {
    font-size: 18px;
    font-weight: bold;
}

.buttons {
    display: flex;
    gap: 12px;
    align-items: center;
}

.btn {
    border: 1px solid rgba(255,255,255,.25);
    background: rgba(255,255,255,.13);
    backdrop-filter: blur(15px);

    padding: 11px 18px;
    border-radius: 30px;

    color: white;
    cursor: pointer;
    transition: .3s;
}

.btn:hover {
    background: rgba(255,255,255,.25);
    transform: scale(1.04);
}

/* MAIN */

.container {
    min-height: 100vh;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    text-align: center;

    padding: 80px 20px 180px;
}

/* ONLINE */

.online {
    background: rgba(255,255,255,.15);
    border: 1px solid rgba(255,255,255,.2);

    backdrop-filter: blur(10px);

    padding: 8px 18px;
    border-radius: 30px;

    font-size: 14px;

    margin-bottom: 20px;
}

.dot {
    display: inline-block;
    width: 9px;
    height: 9px;

    background: #62e36c;
    border-radius: 50%;

    margin-right: 6px;
}

/* TITLE */

.title {
    font-size: clamp(55px, 9vw, 130px);
    font-family: Georgia, serif;

    text-shadow:
        0 5px 20px rgba(0,0,0,.8);

    line-height: 1;

    margin-bottom: 25px;
}

.subtitle {
    font-size: 18px;
    opacity: .85;
    letter-spacing: 3px;
}

/* NOTICE */

.notice {
    margin-top: 30px;

    max-width: 600px;

    background: rgba(80,25,15,.55);
    border: 1px solid rgba(255,255,255,.2);

    backdrop-filter: blur(15px);

    padding: 15px 25px;

    border-radius: 18px;

    font-size: 14px;
}

/* PLAYER */

.player {
    position: fixed;

    bottom: 30px;
    left: 50%;

    transform: translateX(-50%);

    width: min(700px, calc(100% - 30px));

    background: rgba(20,20,20,.65);
    border: 1px solid rgba(255,255,255,.25);

    backdrop-filter: blur(25px);

    border-radius: 25px;

    padding: 15px 20px;

    display: flex;
    align-items: center;
    gap: 15px;

    z-index: 20;

    box-shadow: 0 10px 50px rgba(0,0,0,.5);
}

/* COVER */

.cover {
    width: 60px;
    height: 60px;

    border-radius: 50%;

    object-fit: cover;

    border: 2px solid rgba(255,255,255,.5);
}

/* SONG INFO */

.song-info {
    flex: 1;
    text-align: left;
}

.song-name {
    font-weight: bold;
    font-size: 16px;
}

.artist {
    opacity: .65;
    font-size: 13px;

    margin-top: 5px;
}

/* CONTROLS */

.controls {
    display: flex;
    align-items: center;
    gap: 10px;
}

.control {
    width: 42px;
    height: 42px;

    border-radius: 50%;
    border: none;

    background: rgba(255,255,255,.15);

    color: white;
    font-size: 18px;

    cursor: pointer;

    transition: .2s;
}

.control:hover {
    background: white;
    color: black;
}

.play {
    width: 48px;
    height: 48px;

    background: white;
    color: black;

    font-size: 20px;
}

/* PROGRESS */

.progress-area {
    position: absolute;

    left: 20px;
    right: 20px;
    bottom: 7px;
}

.progress {
    width: 100%;
    height: 3px;

    appearance: none;

    cursor: pointer;
}

.progress::-webkit-slider-thumb {
    appearance: none;

    width: 10px;
    height: 10px;

    border-radius: 50%;
    background: white;
}

/* SONG LIST */

.song-list {
    position: fixed;

    right: 20px;
    top: 100px;

    width: 250px;

    background: rgba(0,0,0,.45);
    backdrop-filter: blur(20px);

    padding: 15px;

    border-radius: 20px;

    z-index: 30;

    display: none;
}

.song-list.show {
    display: block;
}

.song-list h3 {
    margin-bottom: 12px;
}

.song {
    padding: 10px;

    border-radius: 10px;

    cursor: pointer;

    transition: .2s;
}

.song:hover {
    background: rgba(255,255,255,.15);
}

/* MOBILE */

@media(max-width:700px) {

    .topbar {
        left: 15px;
        right: 15px;
    }

    .buttons .btn {
        padding: 9px 12px;
        font-size: 12px;
    }

    .title {
        font-size: 55px;
    }

    .subtitle {
        font-size: 13px;
    }

    .player {
        bottom: 15px;
        padding: 12px;
    }

    .cover {
        width: 50px;
        height: 50px;
    }

    .controls .control:nth-child(1),
    .controls .control:nth-child(3) {
        display: none;
    }

}
</style>
</head>

<body>

<!-- TOP -->

<div class="topbar">

    <div class="time" id="time">
        10:30 AM
    </div>

    <div class="buttons">

        <button class="btn" onclick="toggleMute()">
            🔊
        </button>

        <button class="btn" onclick="toggleSongs()">
            🎵 Songs
        </button>

        <button class="btn">
            ❤️ Support
        </button>

    </div>

</div>


<!-- MAIN -->

<div class="container">

    <div class="online">
        <span class="dot"></span>
        <span id="online">892</span> people online
    </div>

    <h1 class="title">
        भोजपुरी<br>Bangers
    </h1>

    <div class="subtitle">
        DESI VIBES • BHOJPURI MUSIC • NONSTOP
    </div>

    <div class="notice">

        🎧 Welcome to Bhojpuri Bangers

        <br><br>

        Sirf Bhojpuri music ka asli adda ❤️

    </div>

</div>


<!-- SONG LIST -->

<div class="song-list" id="songList">

    <h3>🎵 Bhojpuri Songs</h3>

    <div class="song" onclick="playSong(0)">
        ▶️ Yadav Ji Ke Khatal Me
    </div>

    <div class="song" onclick="playSong(1)">
        ▶️ Bhojpuri Banger 2
    </div>

    <div class="song" onclick="playSong(2)">
        ▶️ Desi Bhojpuri Beat
    </div>

</div>


<!-- PLAYER -->

<div class="player">

    <img
        id="cover"
        class="cover"
        src="cover.jpg"
        alt="Song Cover"
    >

    <div class="song-info">

        <div
            class="song-name"
            id="songName">
            Yadav Ji Ke Khatal Me
        </div>

        <div
            class="artist"
            id="artist">
            Saurav Yadav Official
        </div>

    </div>


    <div class="controls">

        <button
            class="control"
            onclick="previousSong()">
            ⏮
        </button>

        <button
            class="control play"
            id="playBtn"
            onclick="playPause()">
            ▶
        </button>

        <button
            class="control"
            onclick="nextSong()">
            ⏭
        </button>

    </div>

    <div class="progress-area">

        <input
            type="range"
            class="progress"
            id="progress"
            value="0"
            min="0"
            max="100"
            onchange="changeProgress()">

    </div>

</div>


<!-- AUDIO -->

<audio id="audio"></audio>


<script>

const songs = [

    {
        name: "Yadav Ji Ke Khatal Me",
        artist: "Saurav Yadav Official",
        file: "songs/song1.mp3",
        cover: "cover.jpg"
    },

    {
        name: "Bhojpuri Banger 2",
        artist: "Bhojpuri Artist",
        file: "songs/song2.mp3",
        cover: "cover2.jpg"
    },

    {
        name: "Desi Bhojpuri Beat",
        artist: "Bhojpuri Artist",
        file: "songs/song3.mp3",
        cover: "cover3.jpg"
    }

];


let currentSong = 0;

const audio = document.getElementById("audio");
const playBtn = document.getElementById("playBtn");
const progress = document.getElementById("progress");


// LOAD SONG

function loadSong(index) {

    currentSong = index;

    const song = songs[index];

    audio.src = song.file;

    document.getElementById("songName").innerText =
        song.name;

    document.getElementById("artist").innerText =
        song.artist;

    document.getElementById("cover").src =
        song.cover;
}


// PLAY / PAUSE

function playPause() {

    if (audio.paused) {

        audio.play();

        playBtn.innerHTML = "⏸";

    } else {

        audio.pause();

        playBtn.innerHTML = "▶";

    }

}


// NEXT

function nextSong() {

    currentSong++;

    if (currentSong >= songs.length) {
        currentSong = 0;
    }

    loadSong(currentSong);

    audio.play();

    playBtn.innerHTML = "⏸";
}


// PREVIOUS

function previousSong() {

    currentSong--;

    if (currentSong < 0) {
        currentSong = songs.length - 1;
    }

    loadSong(currentSong);

    audio.play();

    playBtn.innerHTML = "⏸";
}


// SONG FROM LIST

function playSong(index) {

    loadSong(index);

    audio.play();

    playBtn.innerHTML = "⏸";

}


// AUTO NEXT

audio.addEventListener("ended", function() {

    nextSong();

});


// PROGRESS

audio.addEventListener("timeupdate", function() {

    if (audio.duration) {

        const percent =
            (audio.currentTime / audio.duration) * 100;

        progress.value = percent;

    }

});


function changeProgress() {

    if (audio.duration) {

        audio.currentTime =
            (progress.value / 100) * audio.duration;

    }

}


// MUTE

function toggleMute() {

    audio.muted = !audio.muted;

}


// SONG MENU

function toggleSongs() {

    document
        .getElementById("songList")
        .classList.toggle("show");

}


// TIME

function updateTime() {

    const now = new Date();

    document.getElementById("time").innerText =
        now.toLocaleTimeString([], {
            hour: "2-digit",
            minute: "2-digit"
        });

}

setInterval(updateTime, 1000);

updateTime();


// ONLINE COUNTER

setInterval(function() {

    let number =
        850 + Math.floor(Math.random() * 100);

    document.getElementById("online").innerText =
        number;

}, 5000);


// FIRST SONG

loadSong(0);

</script>

</body>
</html>
