<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TreadMtl - Tire Shop</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="logo">
            <img src="logo.png" alt="TreadMtl Logo"> <!-- Replace with your actual logo -->
        </div>
        <div class="lang-toggle">
            <button onclick="toggleLanguage()">English / Français</button>
        </div>
    </header>

    <section class="promo">
        <h1>Welcome to TreadMtl!</h1>
        <p>Get a 12% discount on any purchase over $500 before tax on 4 tires!</p>
    </section>

    <section class="tire-search">
        <h2>Find Your Tires</h2>
        <form id="search-form">
            <label for="car-model">Enter your car model or tire dimensions:</label>
            <input type="text" id="car-model" placeholder="e.g., 205/55R16 or Honda Civic">
            <button type="submit">Search</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2025 TreadMtl - Located in Laval</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
    margin: 0;
    padding: 0;
}

header {
    background-color: #1A1A2E; /* Navy Blue */
    color: white;
    padding: 10px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo img {
    height: 50px;
}

.lang-toggle button {
    background-color: #4CAF50;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
}

.lang-toggle button:hover {
    background-color: #45a049;
}

.promo {
    background-color: #999; /* Gray */
    color: #fff;
    text-align: center;
    padding: 20px;
}

.tire-search {
    margin: 20px;
    text-align: center;
}

.tire-search input {
    padding: 10px;
    width: 300px;
    margin-top: 10px;
}

footer {
    background-color: #1A1A2E;
    color: white;
    text-align: center;
    padding: 10px;
    position: fixed;
    bottom: 0;
    width: 100%;
}
function toggleLanguage() {
    const currentLanguage = document.body.getAttribute('lang');
    if (currentLanguage === 'en') {
        document.body.setAttribute('lang', 'fr');
        document.querySelector('.promo h1').innerText = 'Bienvenue à TreadMtl!';
        document.querySelector('.promo p').innerText = 'Obtenez une réduction de 12 % sur tout achat de 500 $ avant taxes pour 4 pneus!';
        document.querySelector('.tire-search h2').innerText = 'Trouvez vos pneus';
        document.querySelector('label').innerText = "Entrez votre modèle de voiture ou dimensions des pneus:";
        document.querySelector('button[type="submit"]').innerText = 'Rechercher';
        document.querySelector('footer p').innerText = 'TreadMtl - Situé à Laval';
    } else {
        document.body.setAttribute('lang', 'en');
        document.querySelector('.promo h1').innerText = 'Welcome to TreadMtl!';
        document.querySelector('.promo p').innerText = 'Get a 12% discount on any purchase over $500 before tax on 4 tires!';
        document.querySelector('.tire-search h2').innerText = 'Find Your Tires';
        document.querySelector('label').innerText = 'Enter your car model or tire dimensions:';
        document.querySelector('button[type="submit"]').innerText = 'Search';
        document.querySelector('footer p').innerText = 'TreadMtl - Located in Laval';
    }
}

document.getElementById('search-form').addEventListener('submit', function (event) {
    event.preventDefault();
    const searchQuery = document.getElementById('car-model').value;
    alert('Searching for: ' + searchQuery);
});

