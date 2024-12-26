<!DOCTYPE html>
<html lang="el">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Το Άλμπουμ μας</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Arial, sans-serif;
            background: url('hearts-background.jpg') center/cover no-repeat;
        }

        #start-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        #start-btn {
            background-color: #ff6b6b;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 20px;
            cursor: pointer;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.2s, box-shadow 0.2s;
        }

        #start-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 10px rgba(0, 0, 0, 0.2);
        }

        #album {
            display: none;
            width: 80%;
            height: 80%;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        .page {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: 100%;
            flex-shrink: 0;
            position: absolute;
            transform-origin: left;
            transform: rotateY(180deg);
            backface-visibility: hidden;
            transition: transform 0.8s;
        }

        .page img {
            max-width: 90%;
            max-height: 90%;
            border-radius: 10px;
        }

        .page.active {
            transform: rotateY(0);
        }

        #message {
            text-align: center;
            font-size: 20px;
            padding: 20px;
            color: #333;
        }
    </style>
</head>
<body>

<div id="start-container">
    <h1>Το Άλμπουμ μας</h1>
    <button id="start-btn">Έναρξη</button>
</div>

<div id="album">
    <!-- Φωτογραφίες -->
    <div class="page"><img src="photo1.jpg" alt="Φωτογραφία 1"></div>
    <div class="page"><img src="photo2.jpg" alt="Φωτογραφία 2"></div>
    <div class="page"><img src="photo3.jpg" alt="Φωτογραφία 3"></div>
    <!-- Μήνυμα -->
    <div class="page">
        <div id="message">
            Σε αγαπάω πάρα❤️ πολύ θέλω να το ξέρεις αυτό. Συγγνώμη που σου φέρθηκα έτσι τις τελευταίες μέρες και έχεις πιεστεί αρκετά. Ελπίζω αυτό να σε κάνει να ηρεμήσεις και να σου δώσει να καταλάβεις ότι εγώ εσένα θέλω και καμιά άλλη, τώρα και για πάντα μαζί. Σε αγαπάω❤️
        </div>
    </div>
</div>

<script>
    const startBtn = document.getElementById('start-btn');
    const startContainer = document.getElementById('start-container');
    const album = document.getElementById('album');
    const pages = document.querySelectorAll('.page');

    let currentIndex = 0;

    startBtn.addEventListener('click', () => {
        startContainer.style.display = 'none';
        album.style.display = 'flex';
    });

    album.addEventListener('click', () => {
        if (currentIndex < pages.length) {
            pages[currentIndex].classList.add('active');
            currentIndex++;
        }
    });
</script>

</body>
</html>
