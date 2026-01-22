# coffee-order-menu
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coffee Order Menu</title>
    <style>
        /* CSS: Menata tampilan */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: white;
            padding: 10px;
            text-align: center;
        }

        h1, h2 {
            font-size: 2rem;
        }

        form {
            display: flex;
            flex-direction: column;
            max-width: 400px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        label {
            margin-top: 10px;
            font-size: 1rem;
        }

        select {
            padding: 10px;
            margin-top: 5px;
            font-size: 1rem;
        }

        button {
            margin-top: 20px;
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            border-radius: 5px;
        }

        button:hover {
            background-color: #218838;
        }

        #orderResult {
            margin-top: 20px;
            font-size: 1.2rem;
            color: green;
            text-align: center;
        }
    </style>
</head>
<body>
    <header>
        <h1>Order Your Coffee</h1>
    </header>

    <main>
        <section id="orderOnline">
            <h2>Choose Your Coffee</h2>
            <form id="orderForm">
                <label for="coffeeType">Select Coffee Type:</label>
                <select id="coffeeType" required>
                    <option value="Espresso">Espresso</option>
                    <option value="Cappuccino">Cappuccino</option>
                    <option value="Latte">Latte</option>
                    <option value="Americano">Americano</option>
                </select>
                
                <label for="size">Select Size:</label>
                <select id="size" required>
                    <option value="Small">Small</option>
                    <option value="Medium">Medium</option>
                    <option value="Large">Large</option>
                </select>

                <button type="submit">Place Order</button>
            </form>
            <div id="orderResult"></div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Coffee Shop</p>
    </footer>

    <script>
        /* JavaScript: Menangani pengiriman data */
        document.getElementById("orderForm").addEventListener("submit", function(event) {
            event.preventDefault(); // Mencegah form untuk refresh halaman

            let coffeeType = document.getElementById("coffeeType").value;
            let size = document.getElementById("size").value;

            let orderResult = document.getElementById("orderResult");
            orderResult.innerHTML = `Your order: <strong>${size} ${coffeeType}</strong> has been placed.`;

            // Kirim data pesanan ke server atau backend
            console.log(`Order placed: ${size} ${coffeeType}`);
            // socket.emit('newOrder', { coffeeType, size }); // Kirim ke backend (misalnya WebSocket)
        });
    </script>
</body>
</html>
