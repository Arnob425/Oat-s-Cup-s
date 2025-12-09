<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DBL FLASHER</title>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@700&display=swap');

    body {
        margin: 0;
        padding: 0;
        font-family: 'Orbitron', sans-serif;
        overflow: hidden;
        color: #fff;
        text-align: center;
    }

    /* Background Video */
    video {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -3;
        filter: brightness(0.45);
    }

    /* Free Fire Wallpaper Overlay */
    .overlay {
        background-image: url("freefire.jpg"); /* এখানে তোমার ওয়ালপেপারের নাম দাও */
        background-size: cover;
        background-position: center;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        opacity: 0.25;
        z-index: -2;
    }

    /* Dark Overlay Layer */
    .shadow {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0,0,0,0.6);
        z-index: -1;
    }

    /* Title */
    h1 {
        margin-top: 120px;
        font-size: 55px;
        letter-spacing: 4px;
        color: #00eaff;
        text-shadow: 0 0 20px #00eaff, 0 0 40px #00eaff;
        animation: glow 2.5s infinite alternate;
    }

    @keyframes glow {
        from { text-shadow: 0 0 10px #00eaff; }
        to { text-shadow: 0 0 30px #00eaff, 0 0 60px #00eaff; }
    }

    /* Instagram Button */
    .insta-btn {
        margin-top: 50px;
        padding: 18px 40px;
        background: #ff006a;
        border-radius: 40px;
        font-size: 22px;
        color: white;
        text-decoration: none;
        transition: 0.3s;
        display: inline-block;
        box-shadow: 0 0 20px #ff006a;
    }

    .insta-btn:hover {
        background: #ff2ca3;
        box-shadow: 0 0 35px #ff2ca3;
        transform: scale(1.08);
    }
</style>
</head>
<body>

<!-- Background Video -->
<video autoplay loop muted>
    <source src="bgvideo.mp4" type="video/mp4"> 
    <!-- এখানে তোমার ভিডিওর নাম দেবে -->
</video>

<div class="overlay"></div>
<div class="shadow"></div>

<!-- Title -->
<h1>DBL FLASHER</h1>

<!-- Instagram Button -->
<a class="insta-btn" 
   href="https://www.instagram.com/arnob.exe_/?next=%2F" 
   target="_blank">FOLLOW ME ON INSTAGRAM</a>

<!-- Background Music -->
<audio autoplay loop>
    <source src="spotlight.mp3" type="audio/mpeg">
</audio>

</body>
</html>
