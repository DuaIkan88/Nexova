<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LUXE | Premium Catalog</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- VARIABLES & RESET --- */
        :root {
            --bg-color: #0f0f0f;
            --card-bg: #1a1a1a;
            --text-main: #f0f0f0;
            --text-muted: #a0a0a0;
            --gold: #D4AF37;
            --gold-hover: #b59020;
            --shopee: #ee4d2d;
            --whatsapp: #25D366;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            text-decoration: none;
            list-style: none;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
        }

        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }

        /* --- HEADER & NAV --- */
        header {
            background-color: rgba(15, 15, 15, 0.95);
            padding: 1.5rem 5%;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid #333;
            display: flex;
            justify-content: space-between;
            align-items: center;
            backdrop-filter: blur(10px);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--gold);
            letter-spacing: 2px;
        }

        nav ul {
            display: flex;
            gap: 2rem;
        }

        nav a {
            color: var(--text-main);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: 0.3s;
        }

        nav a:hover {
            color: var(--gold);
        }

        /* Mobile Menu Icon (Hidden on PC) */
        .menu-toggle {
            display: none;
            color: var(--gold);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* --- HERO SECTION --- */
        .hero {
            height: 80vh;
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1441986300917-64674bd600d8?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            color: var(--gold);
            animation: fadeIn Up 1s ease;
        }

        .hero p {
            font-size: 1.2rem;
            color: #ddd;
            margin-bottom: 2rem;
            max-width: 600px;
            font-weight: 300;
        }

        .btn-main {
            padding: 12px 35px;
            background-color: transparent;
            border: 2px solid var(--gold);
            color: var(--gold);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: 0.4s;
            cursor: pointer;
        }

        .btn-main:hover {
            background-color: var(--gold);
            color: #000;
        }

        /* --- CATALOG SECTION --- */
        .catalog {
            padding: 4rem 5%;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .section-title span {
            display: block;
            width: 60px;
            height: 3px;
            background-color: var(--gold);
            margin: 0 auto;
        }

        /* PRODUCT GRID */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
        }

        /* PRODUCT CARD */
        .product-card {
            background-color: var(--card-bg);
            border: 1px solid #333;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.5);
            border-color: var(--gold);
        }

        .product-img-box {
            width: 100%;
            height: 300px;
            overflow: hidden;
            position: relative;
        }

        .product-img-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .product-card:hover .product-img-box img {
            transform: scale(1.1);
        }

        /* Label "New" or "Sale" */
        .badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: var(--gold);
            color: #000;
            padding: 5px 12px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
            border-radius: 2px;
        }

        .product-info {
            padding: 1.5rem;
            text-align: center;
        }

        .product-category {
            font-size: 0.8rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 0.5rem;
        }

        .product-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--text-main);
        }

        .product-price {
            font-family: 'Playfair Display', serif;
            font-size: 1.3rem;
            color: var(--gold);
            margin-bottom: 1.2rem;
            font-weight: 700;
        }

        .product-actions {
            display: flex;
            justify-content: center;
            gap: 10px;
        }

        .btn-shop, .btn-wa {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            transition: 0.3s;
            font-size: 1.1rem;
        }

        .btn-shop {
            background-color: #333;
            color: #fff;
        }

        .btn-shop:hover {
            background-color: var(--shopee); /* Shopee Orange */
        }

        .btn-wa {
            background-color: #333;
            color: #fff;
        }

        .btn-wa:hover {
            background-color: var(--whatsapp);
        }

        .btn-detail {
            background-color: transparent;
            border: 1px solid #555;
            color: #ccc;
            padding: 0 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
        }
        
        .btn-detail:hover {
            border-color: var(--text-main);
            color: var(--text-main);
        }

        /* --- CONTACT/FOOTER --- */
        footer {
            background-color: #050505;
            padding: 4rem 5% 2rem;
            border-top: 1px solid #222;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .footer-col h4 {
            color: var(--gold);
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .footer-col p, .footer-col a {
            color: var(--text-muted);
            margin-bottom: 0.8rem;
            font-size: 0.9rem;
            display: block;
            transition: 0.3s;
        }

        .footer-col a:hover {
            color: var(--gold);
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 1rem;
        }

        .social-links a {
            width: 35px;
            height: 35px;
            background: #222;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            color: var(--text-main);
        }

        .social-links a:hover {
            background: var(--gold);
            color: #000;
        }

        .copyright {
            text-align: center;
            border-top: 1px solid #222;
            padding-top: 2rem;
            font-size: 0.8rem;
            color: #666;
        }

        /* --- RESPONSIVE MEDIA QUERIES --- */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            nav {
                display: none; /* Simplifikasi menu mobile untuk demo ini */
            }

            .menu-toggle {
                display: block;
            }

            .product-grid {
                grid-template-columns: 1fr; /* 1 kolom di HP */
                padding: 0 20px;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">LUXE.</div>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#collection">Koleksi</a></li>
                <li><a href="#about">Tentang</a></li>
                <li><a href="#contact">Kontak</a></li>
            </ul>
        </nav>
        <div class="menu-toggle">
            <i class="fas fa-bars"></i>
        </div>
    </header>

    <section id="home" class="hero">
        <h1>Elegance Defined.</h1>
        <p>Temukan koleksi produk eksklusif kami yang dirancang dengan kesempurnaan dan kualitas terbaik untuk gaya hidup Anda.</p>
        <a href="#collection" class="btn-main">Lihat Katalog</a>
    </section>

    <section id="collection" class="catalog">
        <div class="section-title">
            <h2>Koleksi Terbaru</h2>
            <span></span>
        </div>

        <div class="product-grid">
            
            <div class="product-card">
                <div class="badge">BEST SELLER</div>
                <div class="product-img-box">
                    <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-1.2.1&auto=format&fit=crop&w=989&q=80" alt="Jam Tangan Mewah">
                </div>
                <div class="product-info">
                    <p class="product-category">Aksesoris</p>
                    <h3 class="product-title">Minimalist White Watch</h3>
                    <div class="product-price">Rp 1.499.000</div>
                    
                    <div class="product-actions">
                        <a href="#" class="btn-detail">Detail</a>
                        <a href="https://shopee.co.id/toko-anda" target="_blank" class="btn-shop" title="Beli di Shopee">
                            <i class="fas fa-shopping-bag"></i>
                        </a>
                        <a href="https://wa.me/6281234567890?text=Halo%20saya%20tertarik%20produk%20ini" target="_blank" class="btn-wa" title="Chat WhatsApp">
                            <i class="fab fa-whatsapp"></i>
                        </a>
                    </div>
                </div>
            </div>

            <div class="product-card">
                <div class="product-img-box">
                    <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Sepatu Nike">
                </div>
                <div class="product-info">
                    <p class="product-category">Footwear</p>
                    <h3 class="product-title">Red Urban Sneakers</h3>
                    <div class="product-price">Rp 2.200.000</div>
                    
                    <div class="product-actions">
                        <a href="#" class="btn-detail">Detail</a>
                        <a href="#" class="btn-shop"><i class="fas fa-shopping-bag"></i></a>
                        <a href="#" class="btn-wa"><i class="fab fa-whatsapp"></i></a>
                    </div>
                </div>
            </div>

            <div class="product-card">
                <div class="badge">NEW</div>
                <div class="product-img-box">
                    <img src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Headphone">
                </div>
                <div class="product-info">
                    <p class="product-category">Elektronik</p>
                    <h3 class="product-title">Gold Edition Headphones</h3>
                    <div class="product-price">Rp 3.500.000</div>
                    
                    <div class="product-actions">
                        <a href="#" class="btn-detail">Detail</a>
                        <a href="#" class="btn-shop"><i class="fas fa-shopping-bag"></i></a>
                        <a href="#" class="btn-wa"><i class="fab fa-whatsapp"></i></a>
                    </div>
                </div>
            </div>

            <div class="product-card">
                <div class="product-img-box">
                    <img src="https://images.unsplash.com/photo-1548036328-c9fa89d128fa?ixlib=rb-1.2.1&auto=format&fit=crop&w=1349&q=80" alt="Tas Kulit">
                </div>
                <div class="product-info">
                    <p class="product-category">Tas Wanita</p>
                    <h3 class="product-title">Classic Leather Bag</h3>
                    <div class="product-price">Rp 899.000</div>
                    
                    <div class="product-actions">
                        <a href="#" class="btn-detail">Detail</a>
                        <a href="#" class="btn-shop"><i class="fas fa-shopping-bag"></i></a>
                        <a href="#" class="btn-wa"><i class="fab fa-whatsapp"></i></a>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <footer id="contact">
        <div class="footer-content">
            <div class="footer-col">
                <h4>Tentang Kami</h4>
                <p>LUXE menghadirkan kurasi produk terbaik untuk Anda yang mengutamakan kualitas dan estetika. Belanja dengan gaya, hidup dengan elegan.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-tiktok"></i></a>
                </div>
            </div>
            
            <div class="footer-col">
                <h4>Link Cepat</h4>
                <a href="#home">Beranda</a>
                <a href="#collection">Katalog Produk</a>
                <a href="#">Cara Pemesanan</a>
                <a href="#">FAQ & Garansi</a>
            </div>

            <div class="footer-col">
                <h4>Hubungi Kami</h4>
                <p><i class="fas fa-map-marker-alt"></i> Jakarta Selatan, Indonesia</p>
                <p><i class="fas fa-envelope"></i> hello@luxecatalog.com</p>
                <p><i class="fas fa-phone"></i> +62 812-3456-7890</p>
                
                <div style="margin-top: 20px;">
                    <a href="#" style="color: var(--gold); border: 1px solid var(--gold); padding: 8px 15px; display:inline-block; margin-right:5px; border-radius:4px;">
                        <i class="fas fa-store"></i> Tokopedia
                    </a>
                    <a href="#" style="color: #fff; background: var(--shopee); padding: 8px 15px; display:inline-block; border-radius:4px; border:none;">
                        <i class="fas fa-shopping-bag"></i> Shopee
                    </a>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 LUXE Catalog. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        // Simple script untuk toggle menu di mobile (Opsional)
        const menuToggle = document.querySelector('.menu-toggle');
        const nav = document.querySelector('nav');

        menuToggle.addEventListener('click', () => {
            if(nav.style.display === 'block') {
                nav.style.display = 'none';
            } else {
                nav.style.display = 'block';
                nav.style.position = 'absolute';
                nav.style.top = '70px';
                nav.style.right = '0';
                nav.style.width = '100%';
                nav.style.background = '#1a1a1a';
                nav.style.textAlign = 'center';
                nav.style.padding = '20px';
            }
        });
    </script>
</body>
</html>
