<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Journey Of Dreams</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        /* ===== BODY & HOME ===== */
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            font-family: Arial, sans-serif;
            position: relative;
        }

        #home {
            width: 100%;
            height: 100vh;
            background: url('https://res.cloudinary.com/dd1pcuf8c/image/upload/v1763529978/samples/ecommerce/accessories-bag.jpg') no-repeat center center/cover;
            display: flex;
            flex-direction: column;
            justify-content: flex-start; /* Mulai dari atas */
            align-items: center;
            padding: 50px 20px 20px 20px; /* Padding atas lebih besar */
            position: relative;
        }

        /* overlay gelap */
        #home::before {
            content: "";
            position: absolute;
            inset: 0;
            background: rgba(0,0,0,0.4);
            z-index: 0;
        }

        #home * {
            position: relative;
            z-index: 1;
        }

        h1 {
            font-family: Poppins, sans-serif;
            font-size: 3em;
            color: #f89320;
            margin-bottom: 50px;
            text-align: center;
        }

        .options {
            display: flex;
            gap: 50px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .option {
            background: rgba(255, 255, 255, 0.85);
            padding: 20px;
            border-radius: 10px;
            box-shadow: rgba(0,0,0,0.2) 0px 5px 15px;
            cursor: pointer;
            transition: transform 0.3s;
            min-width: 180px;
        }

        .option:hover {
            transform: scale(1.05);
        }

        .option h2 {
            margin: 0 0 10px;
            font-size: 1.8em;
        }

        .option p {
            margin: 0;
            font-size: 14px;
        }

        /* ===== PRODUK ===== */
        #products {
            display: none;
            padding: 30px 20px;
        }

        #jersey-products,
        #kaos-products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product {
            background: #fff;
            border-radius: 15px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 6px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .product:hover {
            transform: translateY(-5px);
        }

        .product img {
            width: 100%;
            aspect-ratio: 16 / 9;
            object-fit: cover;
            border-radius: 10px;
        }

        .product h3 {
            margin: 12px 0 5px;
            font-size: 16px;
            color: #333;
        }

        .product p {
            margin: 0;
            font-weight: bold;
            color: #e74c3c;
            font-size: 15px;
        }

        /* ===== BACK BUTTON ===== */
        .back {
            display: none;
            text-align: center;
            margin: 20px 0;
            text-decoration: none;
            color: #4a90e2;
            font-weight: bold;
            cursor: pointer;
        }

        /* ===== SOCIAL MEDIA ===== */
        .social-media {
            position: fixed;   /* selalu di bawah layar */
            bottom: 20px;      /* jarak dari bawah */
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 20px;
            z-index: 9999;
        }

        .social-media a {
            color: white;
            font-size: 30px;
            background: rgba(0,0,0,0.5);
            padding: 12px;
            border-radius: 50%;
            transition: transform 0.3s;
        }

        .social-media a:hover {
            transform: scale(1.2);
        }

        .social-media .fa-whatsapp { color: #25D366; }
        .social-media .fa-instagram { color: #E1306C; }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 600px) {
            #jersey-products,
            #kaos-products {
                grid-template-columns: 1fr;
            }
            .product img {
                aspect-ratio: 4 / 3;
            }
            .options {
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- HOME PAGE -->
    <div id="home">
        <h1>Selamat Datang di Journey Of Dreams store</h1>
        <div class="options">
            <div class="option" onclick="showProducts('jersey')">
                <h2>Jersey</h2>
                <p>Koleksi jersey olahraga dan kasual</p>
            </div>
            <div class="option" onclick="showProducts('kaos')">
                <h2>Kaos</h2>
                <p>Koleksi kaos santai dan stylish</p>
            </div>
        </div>
    </div>

    <!-- PRODUK PAGE -->
    <div id="products">
        <!-- Jersey -->
        <div id="jersey-products" style="display: none;">
            <div class="product">
                <img src="https://res.cloudinary.com/dd1pcuf8c/image/upload/v1767038814/4a9fd2a17a67a4f25248839e078273a4_use9ip.jpg" alt="Jersey Sepak Bola">
                <h3>Jersey Sepak Bola Tim A</h3>
                <p>Rp 150.000</p>
            </div>
            <div class="product">
                <img src="https://res.cloudinary.com/dd1pcuf8c/image/upload/v1767038814/4a9fd2a17a67a4f25248839e078273a4_use9ip.jpg" alt="Jersey Basket">
                <h3>Jersey Basket Tim B</h3>
                <p>Rp 180.000</p>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/250x200?text=Jersey+Lari" alt="Jersey Lari">
                <h3>Jersey Lari Casual</h3>
                <p>Rp 120.000</p>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/250x200?text=Jersey+Futsal" alt="Jersey Futsal">
                <h3>Jersey Futsal Tim C</h3>
                <p>Rp 160.000</p>
            </div>
        </div>

        <!-- Kaos -->
        <div id="kaos-products" style="display: none;">
            <div class="product">
                <img src="https://via.placeholder.com/250x200?text=Kaos+Polos" alt="Kaos Polos">
                <h3>Kaos Polos Hitam</h3>
                <p>Rp 50.000</p>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/250x200?text=Kaos+Motif" alt="Kaos Motif">
                <h3>Kaos Motif Grafis</h3>
                <p>Rp 75.000</p>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/250x200?text=Kaos+V-Neck" alt="Kaos V-Neck">
                <h3>Kaos V-Neck Putih</h3>
                <p>Rp 60.000</p>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/250x200?text=Kaos+Band" alt="Kaos Band">
                <h3>Kaos Band Musik</h3>
                <p>Rp 85.000</p>
            </div>
        </div>

        <!-- BACK BUTTON -->
        <div class="back" id="back-btn" onclick="showHome()">Kembali ke Halaman Utama</div>
    </div>

    <!-- SOCIAL MEDIA BOTTOM -->
    <div class="social-media">
        <a href="https://wa.me/6281234567890" target="_blank">
            <i class="fab fa-whatsapp"></i>
        </a>
        <a href="https://instagram.com/journeyofdreams" target="_blank">
            <i class="fab fa-instagram"></i>
        </a>
    </div>

    <!-- JAVASCRIPT -->
    <script>
        function showProducts(type) {
            document.getElementById('home').style.display = 'none';
            document.getElementById('products').style.display = 'block';
            document.getElementById('back-btn').style.display = 'block';
            
            if(type === 'jersey') {
                document.getElementById('jersey-products').style.display = 'grid';
                document.getElementById('kaos-products').style.display = 'none';
            } else if(type === 'kaos') {
                document.getElementById('kaos-products').style.display = 'grid';
                document.getElementById('jersey-products').style.display = 'none';
            }
        }

        function showHome() {
            document.getElementById('home').style.display = 'flex';
            document.getElementById('products').style.display = 'none';
            document.getElementById('back-btn').style.display = 'none';
            document.getElementById('jersey-products').style.display = 'none';
            document.getElementById('kaos-products').style.display = 'none';
        }
    </script>
</body>
</html>
