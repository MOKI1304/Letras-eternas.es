# Letras-eternas.es<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tienda de Poemas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        header {
            background: #4CAF50;
            color: white;
            padding: 10px 20px;
            text-align: center;
        }
        nav {
            background: #333;
            color: white;
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
        }
        nav a {
            color: white;
            text-decoration: none;
        }
        nav a:hover {
            text-decoration: underline;
        }
        main {
            padding: 20px;
        }
        .poemas, .mercado, .carrito {
            margin-top: 20px;
        }
        .poema {
            border: 1px solid #ddd;
            margin: 10px 0;
            padding: 10px;
            border-radius: 5px;
        }
        .poema button {
            background: #4CAF50;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
        }
        .poema button:hover {
            background: #45a049;
        }
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 10px 0;
            margin-top: 20px;
        }
    </style>
</head>
<body>

<header>
    <h1>Tienda de Poemas y Libros</h1>
</header>

<nav>
    <a href="#poemas">Poemas</a>
    <a href="#mercado">Mercado</a>
    <a href="#carrito">Carrito</a>
</nav>

<main>
    <!-- Poemas Section -->
    <section id="poemas" class="poemas">
        <h2>Poemas</h2>
        <div class="poema">
            <h3>Poema 1: El Susurro del Viento</h3>
            <p>Un hermoso poema sobre la naturaleza...</p>
            <button onclick="addToCart('Poema 1', 5)">Comprar por $5</button>
        </div>
        <div class="poema">
            <h3>Poema 2: Bajo la Luna</h3>
            <p>Un poema que te transporta a noches mágicas...</p>
            <button onclick="addToCart('Poema 2', 7)">Comprar por $7</button>
        </div>
    </section>

    <!-- Mercado Section -->
    <section id="mercado" class="mercado">
        <h2>Mercado</h2>
        <div class="poema">
            <h3>Libro: Poemas del Alma</h3>
            <p>Una colección especial de poemas clásicos.</p>
            <button onclick="addToCart('Libro: Poemas del Alma', 20)">Comprar por $20</button>
        </div>
        <div class="poema">
            <h3>Cuaderno de Poesía</h3>
            <p>Un cuaderno para escribir tus propios poemas.</p>
            <button onclick="addToCart('Cuaderno de Poesía', 10)">Comprar por $10</button>
        </div>
    </section>

    <!-- Carrito Section -->
    <section id="carrito" class="carrito">
        <h2>Carrito</h2>
        <ul id="cartItems">
            <li>No hay productos en el carrito.</li>
        </ul>
        <h3>Total: $<span id="totalPrice">0</span></h3>
    </section>
</main>

<footer>
    <p>Gracias por visitar nuestra tienda de poemas y libros.</p>
</footer>

<script>
    const cart = [];
    const cartItemsElement = document.getElementById('cartItems');
    const totalPriceElement = document.getElementById('totalPrice');

    function addToCart(itemName, price) {
        cart.push({ name: itemName, price: price });
        updateCart();
    }

    function updateCart() {
        cartItemsElement.innerHTML = '';
        let total = 0;

        cart.forEach((item, index) => {
            const li = document.createElement('li');
            li.textContent = ${item.name} - $${item.price};
            cartItemsElement.appendChild(li);
            total += item.price;
        });

        if (cart.length === 0) {
            cartItemsElement.innerHTML = '<li>No hay productos en el carrito.</li>';
        }

        totalPriceElement.textContent = total;
    }
</script>

</body>
</html>
