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
