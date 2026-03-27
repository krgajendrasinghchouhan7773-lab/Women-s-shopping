<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elegance Boutique - Women's Fashion</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {margin:0;padding:0;box-sizing:border-box;}
        body{font-family:'Arial',sans-serif;line-height:1.6;color:#333;}
        header{background:linear-gradient(135deg,#ff6b9d 0%,#c44569 100%);color:white;padding:1rem 0;position:fixed;width:100%;top:0;z-index:1000;box-shadow:0 2px 10px rgba(0,0,0,0.1);}
        nav{display:flex;justify-content:space-between;align-items:center;max-width:1200px;margin:0 auto;padding:0 2rem;}
        .logo{font-size:1.8rem;font-weight:bold;}
        .nav-links{display:flex;list-style:none;gap:2rem;}
        .nav-links a{color:white;text-decoration:none;transition:opacity 0.3s;}
        .nav-links a:hover{opacity:0.8;}
        .cart-icon{font-size:1.5rem;cursor:pointer;position:relative;}
        .cart-count{position:absolute;top:-8px;right:-8px;background:#ff4757;color:white;border-radius:50%;width:20px;height:20px;font-size:0.8rem;display:flex;align-items:center;justify-content:center;}
        .hero{background:linear-gradient(rgba(0,0,0,0.4),rgba(0,0,0,0.4)),url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23f8f9fa" width="1200" height="600"/><path fill="%23ff6b9d" d="M0 300Q200 100 400 300T800 300T1200 300V600H0z"/><circle fill="%23c44569" cx="300" cy="200" r="80"/><circle fill="%23ff9ff3" cx="900" cy="150" r="60"/></svg>');height:100vh;background-size:cover;background-position:center;display:flex;align-items:center;justify-content:center;text-align:center;color:white;margin-top:80px;}
        .hero-content h1{font-size:3.5rem;margin-bottom:1rem;animation:fadeInUp 1s ease;}
        .hero-content p{font-size:1.3rem;margin-bottom:2rem;animation:fadeInUp 1s ease 0.2s both;}
        .cta-button{display:inline-block;background:#ff6b9d;color:white;padding:15px 40px;text-decoration:none;border-radius:50px;font-weight:bold;transition:all 0.3s;animation:fadeInUp 1s ease 0.4s both;}
        .cta-button:hover{transform:translateY(-3px);box-shadow:0 10px 25px rgba(255,107,157,0.4);}
        .products{padding:100px 2rem;max-width:1200px;margin:0 auto;}
        .section-title{text-align:center;font-size:2.5rem;margin-bottom:3rem;color:#c44569;}
        .products-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:2rem;}
        .product-card{background:white;border-radius:20px;overflow:hidden;box-shadow:0 10px 30px rgba(0,0,0,0.1);transition:all 0.3s;position:relative;}
        .product-card:hover{transform:translateY(-10px);box-shadow:0 20px 40px rgba(0,0,0,0.2);}
        .product-image{height:300px;background:linear-gradient(45deg,#ff9ff3,#ff6b9d);display:flex;align-items:center;justify-content:center;font-size:4rem;color:white;}
        .product-info{padding:1.5rem;}
        .product-title{font-size:1.3rem;margin-bottom:0.5rem;color:#333;}
        .product-price{font-size:1.5rem;font-weight:bold;color:#ff6b9d;margin-bottom:1rem;}
        .add-to-cart{width:100%;background:#ff6b9d;color:white;border:none;padding:12px;border-radius:10px;font-size:1rem;cursor:pointer;transition:background 0.3s;}
        .add-to-cart:hover{background:#c44569;}
        .features{background:#f8f9fa;padding:100px 2rem;}
        .features-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:2rem;max-width:1200px;margin:0 auto;}
        .feature{text-align:center;padding:2rem;}
        .feature i{font-size:3rem;color:#ff6b9d;margin-bottom:1rem;}
        footer{background:#333;color:white;text-align:center;padding:3rem 2rem 1rem;}
        .footer-content{max-width:1200px;margin:0 auto;display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:2rem;margin-bottom:2rem;}
        .footer-section h3{color:#ff6b9d;margin-bottom:1rem;}
        .footer-section a{color:#ccc;text-decoration:none;display:block;margin-bottom:0.5rem;}
        .social-links{display:flex;justify-content:center;gap:1rem;margin-top:1rem;}
        .social-links a{display:inline-block;width:40px;height:40px;background:#ff6b9d;color:white;text-align:center;line-height:40px;border-radius:50%;transition:transform 0.3s;}
        .social-links a:hover{transform:translateY(-3px);}
        @keyframes fadeInUp{from{opacity:0;transform:translateY(30px);}to{opacity:1;transform:translateY(0);}}
        @media (max-width:768px){.nav-links{display:none;}.hero-content h1{font-size:2.5rem;}.products{padding:80px 1rem;}}
        .cart-modal{display:none;position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.5);z-index:2000;align-items:center;justify-content:center;}
        .cart-content{background:white;padding:2rem;border-radius:20px;max-width:500px;width:90%;max-height:80vh;overflow-y:auto;}
        .close-cart{float:right;font-size:2rem;cursor:pointer;color:#999;}
        @media (max-width: 480px) {.hero-content h1{font-size:2rem;}.hero-content p{font-size:1rem;}}
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">Elegance Boutique</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#products">Shop</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="cart-icon" onclick="toggleCart()">
                <i class="fas fa-shopping-bag"></i>
                <span class="cart-count" id="cartCount">0</span>
            </div>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Discover Your Style</h1>
            <p>Premium women's fashion at unbeatable prices</p>
            <a href="#products" class="cta-button">Shop Now</a>
        </div>
    </section>

    <section class="products" id="products">
        <h2 class="section-title">Featured Collection</h2>
        <div class="products-grid">
            <div class="product-card">
                <div class="product-image"><i class="fas fa-female"></i></div>
                <div class="product-info">
                    <h3 class="product-title">Summer Dress</h3>
                    <div class="product-price">$49.99</div>
                    <button class="add-to-cart" onclick="addToCart('Summer Dress', 49.99)">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image"><i class="fas fa-tshirt"></i></div>
                <div class="product-info">
                    <h3 class="product-title">Silk Blouse</h3>
                    <div class="product-price">$34.99</div>
                    <button class="add-to-cart" onclick="addToCart('Silk Blouse', 34.99)">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image"><i class="fas fa-high-heel"></i></div>
                <div class="product-info">
                    <h3 class="product-title">Designer Heels</h3>
                    <div class="product-price">$89.99</div>
                    <button class="add-to-cart" onclick="addToCart('Designer Heels', 89.99)">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image"><i class="fas fa-handbag"></i></div>
                <div class="product-info">
                    <h3 class="product-title">Leather Bag</h3>
                    <div class="product-price">$129.99</div>
                    <button class="add-to-cart" onclick="addToCart('Leather Bag', 129.99)">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image"><i class="fas fa-gem"></i></div>
                <div class="product-info">
                    <h3 class="product-title">Gold Necklace</h3>
                    <div class="product-price">$59.99</div>
                    <button class="add-to-cart" onclick="addToCart('Gold Necklace', 59.99)">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image"><i class="fas fa-sneakers"></i></div>
                <div class="product-info">
                    <h3 class="product-title">Sneakers</h3>
                    <div class="product-price">$79.99</div>
                    <button class="add-to-cart" onclick="addToCart('Sneakers', 79.99)">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <section class="features">
        <div class="features-grid">
            <div class="feature">
                <i class="fas fa-shipping-fast"></i>
                <h3>Free Shipping</h3>
                <p>Orders over $50</p>
            </div>
            <div class="feature">
                <i class="fas fa-undo"></i>
                <h3>30-Day Returns</h3>
                <p>Hassle-free returns</p>
            </div>
            <div class="feature">
                <i class="fas fa-lock"></i>
                <h3>Secure Checkout</h3>
                <p>SSL protected</p>
            </div>
            <div class="feature">
                <i class="fas fa-headset"></i>
                <h3>24/7 Support</h3>
                <p>We're here for you</p>
            </div>
        </div>
    </section>

    <div class="cart-modal" id="cartModal">
        <div class="cart-content">
            <span class="close-cart" onclick="toggleCart()">&times;</span>
            <h2><i class="fas fa-shopping-cart"></i> Shopping Cart</h2>
            <div id="cartItems"></div>
            <div style="margin-top:2rem;text-align:right;">
                <h3>Total: $<span id="cartTotal">0.00</span></h3>
                <button style="width:100%;background:#ff6b9d;color:white;border:none;padding:15px;border-radius:10px;font-size:1.1rem;cursor:pointer;margin-top:1rem;">Checkout</button>
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Elegance Boutique</h3>
                <p>Premium women's fashion</p>
            </div>
            <div class="footer-section">
                <h3>Shop</h3>
                <a href="#products">Dresses</a>
                <a href="#products">Tops</a>
                <a href="#products">Shoes</a>
                <a href="#products">Accessories</a>
            </div>
            <div class="footer-section">
                <h3>Support</h3>
                <a href="#">Help Center</a>
                <a href="#">Returns</a>
                <a href="#">Shipping</a>
                <a href="#">Contact</a>
            </div>
            <div class="footer-section">
                <h3>Follow</h3>
                <div class="social-links">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                </div>
            </div>
        </div>
        <p>&copy; 2024 Elegance Boutique. All rights reserved.</p>
    </footer>

    <script>
        let cart = []; let cartCount = 0;
        function addToCart(name, price) {
            cart.push({name, price}); cartCount++; updateCartCount();
            alert(`${name} added to cart! 🎉`);
        }
        function updateCartCount() { document.getElementById('cartCount').textContent = cartCount; }
        function toggleCart() {
            const modal = document.getElementById('cartModal');
            modal.style.display = modal.style.display === 'flex' ? 'none' : 'flex';
            if (modal.style.display === 'flex') displayCart();
        }
        function displayCart() {
            const cartItems = document.getElementById('cartItems');
            const cartTotal = document.getElementById('cartTotal');
            if (cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align:center;color:#999;">Your cart is empty 😢</p>';
                cartTotal.textContent = '0.00'; return;
            }
            let total = 0;
            cartItems.innerHTML = cart.map((item, index) => {
                total += item.price;
                return `<div style="display:flex;justify-content:space-between;align-items:center;padding:1rem;border:1px solid #eee;border-radius:10px;margin-bottom:1rem;">
                    <div><strong>${item.name}</strong></div>
                    <div>$${item.price.toFixed(2)}</div>
                    <button onclick="removeFromCart(${index})" style="background:#ff4757;color:white;border:none;padding:8px 12px;border-radius:5px;cursor:pointer;font-size:0.9rem;">Remove</button>
                </div>`;
            }).join('');
            cartTotal.textContent = total.toFixed(2);
        }
        function removeFromCart(index) {
            cart.splice(index, 1); cartCount--; updateCartCount(); displayCart();
        }
        window.onclick = function(event) {
            const modal = document.getElementById('cartModal');
            if (event.target === modal) toggleCart();
        }
        document.querySelector('.cta-button').onclick = function(e) {
            e.preventDefault(); document.querySelector('#products').scrollIntoView({behavior:'smooth'});
        }
    </script>
</body>
</html># Women-s-shopping
Cheap and high quality
