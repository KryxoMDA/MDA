let cart = [];
let total = 0;

function addToCart(product, price) {
    cart.push({ product, price });
    total += price;
    updateCart();
}

function updateCart() {
    const cartList = document.getElementById('cart-items');
    const totalElement = document.getElementById('total');
    cartList.innerHTML = ''; // Réinitialiser le panier
    cart.forEach(item => {
        const li = document.createElement('li');
        li.textContent = `${item.product} - ${item.price}€`;
        cartList.appendChild(li);
    });
    totalElement.textContent = `Total : ${total}€`;
}
/* Styles de base */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 1em;
    text-align: center;
}

nav ul {
    list-style-type: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin-right: 15px;
}

nav a {
    color: white;
    text-decoration: none;
}

main {
    padding: 20px;
}

.category {
    margin-bottom: 40px;
}

.category h2 {
    color: #333;
}

.product {
    display: inline-block;
    width: 200px;
    margin: 10px;
    padding: 10px;
    border: 1px solid #ddd;
    text-align: center;
}

.product img {
    max-width: 100%;
    height: auto;
}

button {
    background-color: #4CAF50;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

aside {
    background-color: #f9f9f9;
    padding: 15px;
    position: fixed;
    right: 0;
    top: 50px;
    width: 250px;
    border-left: 1px solid #ddd;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

#cart-items {
    list-style-type: none;
    padding: 0;
}

#cart-items li {
    margin: 5px 0;
}
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ma Boutique</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- En-tête -->
    <header>
        <h1>Ma Boutique en Ligne</h1>
        <nav>
            <ul>
                <li><a href="#home">Accueil</a></li>
                <li><a href="#category-clothing">Vêtements</a></li>
                <li><a href="#category-electronics">Électronique</a></li>
                <li><a href="#category-accessories">Accessoires</a></li>
                <li><a href="#cart">Panier</a></li>
            </ul>
        </nav>
    </header>

    <!-- Section des catégories -->
    <main>
        <section id="category-clothing" class="category">
            <h2>Vêtements</h2>
            <div class="product">
                <img src="https://via.placeholder.com/150" alt="Produit 1">
                <h3>Produit 1</h3>
                <p>Prix : 20€</p>
                <button onclick="addToCart('Produit 1', 20)">Ajouter au Panier</button>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/150" alt="Produit 2">
                <h3>Produit 2</h3>
                <p>Prix : 25€</p>
                <button onclick="addToCart('Produit 2', 25)">Ajouter au Panier</button>
            </div>
        </section>

        <section id="category-electronics" class="category">
            <h2>Électronique</h2>
            <div class="product">
                <img src="https://via.placeholder.com/150" alt="Produit 3">
                <h3>Produit 3</h3>
                <p>Prix : 100€</p>
                <button onclick="addToCart('Produit 3', 100)">Ajouter au Panier</button>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/150" alt="Produit 4">
                <h3>Produit 4</h3>
                <p>Prix : 120€</p>
                <button onclick="addToCart('Produit 4', 120)">Ajouter au Panier</button>
            </div>
        </section>

        <section id="category-accessories" class="category">
            <h2>Accessoires</h2>
            <div class="product">
                <img src="https://via.placeholder.com/150" alt="Produit 5">
                <h3>Produit 5</h3>
                <p>Prix : 15€</p>
                <button onclick="addToCart('Produit 5', 15)">Ajouter au Panier</button>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/150" alt="Produit 6">
                <h3>Produit 6</h3>
                <p>Prix : 30€</p>
                <button onclick="addToCart('Produit 6', 30)">Ajouter au Panier</button>
            </div>
        </section>
    </main>

    <!-- Panier -->
    <aside id="cart">
        <h2>Votre Panier</h2>
        <ul id="cart-items"></ul>
        <p id="total">Total : 0€</p>
    </aside>

    <script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ma Boutique</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Ma Boutique en Ligne</h1>
        <nav>
            <a href="#">Accueil</a>
            <a href="#">Produits</a>
            <a href="#">Panier</a>
        </nav>
    </header>
    <main>
        <h2>Nos Produits</h2>
        <div class="product">
            <img src="https://via.placeholder.com/150" alt="Produit 1">
            <h3>Produit 1</h3>
            <p>Prix : 20€</p>
            <button onclick="addToCart('Produit 1', 20)">Ajouter au Panier</button>
        </div>
        <div class="product">
            <img src="https://via.placeholder.com/150" alt="Produit 2">
            <h3>Produit 2</h3>
            <p>Prix : 30€</p>
            <button onclick="addToCart('Produit 2', 30)">Ajouter au Panier</button>
        </div>
    </main>
    <aside>
        <h2>Votre Panier</h2>
        <ul id="cart"></ul>
        <p id="total">Total : 0€</p>
    </aside>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}
header {
    background-color: #333;
    color: white;
    padding: 1em;
    text-align: center;
}
header nav a {
    color: white;
    margin: 0 10px;
    text-decoration: none;
}
main {
    padding: 2em;
    display: flex;
    justify-content: space-around;
}
.product {
    border: 1px solid #ddd;
    padding: 1em;
    text-align: center;
}
.product img {
    max-width: 100%;
}
aside {
    background-color: #f9f9f9;
    padding: 1em;
    position: fixed;
    right: 0;
    top: 50px;
    width: 250px;
    border-left: 1px solid #ddd;
}

 let cart = [];
let total = 0;

function addToCart(product, price) {
    cart.push({ product, price });
    total += price;
    updateCart();
}

function updateCart() {
    const cartList = document.getElementById('cart');
    const totalElement = document.getElementById('total');
    cartList.innerHTML = '';
    cart.forEach(item => {
        const li = document.createElement('li');
        li.textContent = `${item.product} - ${item.price}€`;
        cartList.appendChild(li);
    });
    totalElement.textContent = `Total : ${total}€`;
}
# MDA
