<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hardware Ko Toh Boi!</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&family=Montserrat:wght@700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Roboto', sans-serif;
      background: #f5f7fa;
      color: #333;
      line-height: 1.6;
    }

    header {
      background: linear-gradient(135deg, #1a2a6c, #2a4a7c);
      color: white;
      padding: 25px 20px;
      text-align: center;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }

    .title {
      font-family: 'Montserrat', sans-serif;
      font-size: 2.8rem;
      font-weight: 700;
      letter-spacing: 1px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
      margin-bottom: 10px;
    }

    .subtitle {
      font-size: 1.1rem;
      opacity: 0.9;
    }

    nav {
      background: #2a4a7c;
      padding: 15px 0;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    .nav-container {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: center;
    }

    .nav-link {
      color: white;
      text-decoration: none;
      padding: 10px 20px;
      margin: 0 10px;
      border-radius: 5px;
      transition: background 0.3s ease;
      font-weight: 500;
    }

    .nav-link:hover {
      background: rgba(255,255,255,0.1);
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }

    .main-content {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
      margin-top: 20px;
    }

    .products-section {
      flex: 1;
      min-width: 300px;
    }

    .cart-section {
      width: 320px;
    }

    .section-title {
      font-size: 1.5rem;
      margin-bottom: 20px;
      padding-bottom: 10px;
      border-bottom: 2px solid #2a4a7c;
      color: #2a4a7c;
    }

    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 25px;
    }

    .product-card {
      background: white;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 5px 15px rgba(0,0,0,0.08);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .product-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.12);
    }

    .product-image {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-bottom: 1px solid #eee;
    }

    .product-info {
      padding: 18px;
    }

    .product-name {
      font-size: 1.2rem;
      font-weight: 500;
      margin-bottom: 8px;
      color: #1a2a6c;
    }

    .product-price {
      font-size: 1.3rem;
      font-weight: 700;
      color: #e74c3c;
      margin-bottom: 15px;
    }

    .add-to-cart {
      width: 100%;
      padding: 12px;
      background: linear-gradient(to right, #2a4a7c, #1a2a6c);
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1rem;
      font-weight: 500;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    .add-to-cart:hover {
      background: linear-gradient(to right, #1a2a6c, #2a4a7c);
    }

    .cart {
      background: white;
      border-radius: 10px;
      padding: 25px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.08);
      position: sticky;
      top: 20px;
    }

    .cart-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
    }

    .cart-items {
      max-height: 350px;
      overflow-y: auto;
      margin-bottom: 20px;
    }

    .cart-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 0;
      border-bottom: 1px solid #eee;
    }

    .item-details {
      flex: 1;
    }

    .item-name {
      font-weight: 500;
    }

    .item-quantity {
      color: #777;
      font-size: 0.9rem;
    }

    .item-price {
      font-weight: 500;
      color: #e74c3c;
    }

    .cart-total {
      display: flex;
      justify-content: space-between;
      font-size: 1.3rem;
      font-weight: 700;
      padding: 15px 0;
      border-top: 2px solid #eee;
      margin-top: 10px;
    }

    .total-price {
      color: #e74c3c;
    }

    .checkout-btn {
      width: 100%;
      padding: 15px;
      background: linear-gradient(to right, #27ae60, #2ecc71);
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1.1rem;
      font-weight: 500;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    .checkout-btn:hover {
      background: linear-gradient(to right, #219653, #27ae60);
    }

    .empty-cart {
      text-align: center;
      color: #777;
      padding: 20px 0;
    }

    .about-section, .contact-section {
      background: white;
      border-radius: 10px;
      padding: 30px;
      margin: 40px 0;
      box-shadow: 0 5px 15px rgba(0,0,0,0.08);
    }

    .about-content {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
      align-items: center;
    }

    .about-text {
      flex: 1;
      min-width: 300px;
    }

    .about-image {
      flex: 1;
      min-width: 300px;
      height: 300px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 1.2rem;
      overflow: hidden;
    }
    
    .about-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .contact-content {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
    }

    .contact-info {
      flex: 1;
      min-width: 300px;
    }

    .contact-form {
      flex: 1;
      min-width: 300px;
    }

    .contact-item {
      display: flex;
      align-items: center;
      margin-bottom: 20px;
    }

    .contact-icon {
      background: #2a4a7c;
      color: white;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-right: 15px;
    }

    .form-group {
      margin-bottom: 20px;
    }

    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: 500;
    }

    .form-control {
      width: 100%;
      padding: 12px;
      border: 1px solid #ddd;
      border-radius: 5px;
      font-family: 'Roboto', sans-serif;
    }

    .submit-btn {
      background: linear-gradient(to right, #2a4a7c, #1a2a6c);
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 1rem;
      font-weight: 500;
      transition: background 0.3s ease;
    }

    .submit-btn:hover {
      background: linear-gradient(to right, #1a2a6c, #2a4a7c);
    }

    footer {
      background: #1a2a6c;
      color: white;
      padding: 40px 20px 20px;
      margin-top: 40px;
    }

    .footer-content {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 30px;
    }

    .footer-column {
      flex: 1;
      min-width: 250px;
    }

    .footer-column h3 {
      margin-bottom: 20px;
      font-size: 1.3rem;
    }

    .footer-links {
      list-style: none;
    }

    .footer-links li {
      margin-bottom: 10px;
    }

    .footer-links a {
      color: #ddd;
      text-decoration: none;
      transition: color 0.3s ease;
    }

    .footer-links a:hover {
      color: white;
    }

    .social-links {
      display: flex;
      gap: 15px;
      margin-top: 20px;
    }

    .social-link {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 40px;
      height: 40px;
      background: rgba(255,255,255,0.1);
      border-radius: 50%;
      color: white;
      text-decoration: none;
      transition: background 0.3s ease;
    }

    .social-link:hover {
      background: rgba(255,255,255,0.2);
    }

    .copyright {
      text-align: center;
      padding-top: 20px;
      margin-top: 30px;
      border-top: 1px solid rgba(255,255,255,0.1);
      font-size: 0.9rem;
      color: #ddd;
    }

    @media (max-width: 768px) {
      .main-content {
        flex-direction: column;
      }
      
      .cart-section {
        width: 100%;
      }
      
      .title {
        font-size: 2.2rem;
      }
      
      .nav-container {
        flex-wrap: wrap;
      }
    }
  </style>
</head>
<body>

<header>
  <h1 class="title">ǶąɾժաąɾҠօ Ͳօհ βօì! イオへパ</h1>
  <p class="subtitle">Your trusted hardware partner for quality tools and equipment</p>
</header>

<nav>
  <div class="nav-container">
    <a href="#products" class="nav-link">Products</a>
    <a href="#about" class="nav-link">About Us</a>
    <a href="#contact" class="nav-link">Contact</a>
  </div>
</nav>

<div class="container">
  <div class="main-content">
    <div class="products-section" id="products">
      <h2 class="section-title">Our Products</h2>
      <div class="products-grid" id="product-list">
        <!-- Products inserted by JavaScript -->
        <div class="product-card">
          <img src="https://i.postimg.cc/QN2QSZPG/63792f6f3877cc773175a1b2-jaasie-men-39-s-thor-hammer-pretend.jpg" alt="Hammer ni rene" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Hammer ni rene</h3>
            <p class="product-price">₱100,000,002,154,165,150</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/m2rzGbnB/images-14.jpg" alt="Screwdriver pambutas ng hollow blocks" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Screwdriver pambutas ng hollow blocks</h3>
            <p class="product-price">₱512,132,051,432,032</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/YCgy8x8d/drilling-equipment-electric-driller-tool-600nw-2466765527.webp" alt="Drill kupit ni porman" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Drill kupit ni porman</h3>
            <p class="product-price">₱3,032,651,463,521,541,651,684</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/636jWxKY/15380.webp" alt="Wrench galing junkshop" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Wrench galing junkshop</h3>
            <p class="product-price">₱66,514,656,854,651</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/8k78ML86/crack-resistance-easily-penetrated-enhanced-durability-stainless-steel-nails-5x100-mm-3-9-inch-608.jpg" alt="Pako kupit ni kulas (100pcs)" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Pako kupit ni kulas (100pcs)</h3>
            <p class="product-price">₱2,652,514,654,648,645,684</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/MGp1P78B/file-00000000624061f789a756c32fb3f1e4.png" alt="Semento ko toh Bo!" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Semento ko toh Bo!</h3>
            <p class="product-price">₱1,000,000</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/jSdWtRkJ/images-12.jpg" alt="Buhangin order ni porman" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Buhangin order ni porman</h3>
            <p class="product-price">₱10,000,000,000,000</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
        <div class="product-card">
          <img src="https://i.postimg.cc/JznhSPGk/images-11.jpg" alt="Graba padala ni engineer" class="product-image">
          <div class="product-info">
            <h3 class="product-name">Graba padala ni engineer</h3>
            <p class="product-price">₱20,000,000,000,000</p>
            <button class="add-to-cart">Add to Cart</button>
          </div>
        </div>
      </div>
    </div>
    
    <div class="cart-section">
      <div class="cart">
        <div class="cart-header">
          <h2 class="section-title">Your Cart</h2>
        </div>
        <div class="cart-items" id="cart-items">
          <!-- Cart items inserted by JavaScript -->
          <div class="empty-cart">Your cart is empty</div>
        </div>
        <div class="cart-total">
          <span>Total:</span>
          <span class="total-price">₱<span id="cart-total">0.00</span></span>
        </div>
        <button class="checkout-btn">Proceed to Checkout</button>
      </div>
    </div>
  </div>
  
  <div class="about-section" id="about">
    <h2 class="section-title">About Us</h2>
    <div class="about-content">
      <div class="about-text">
        <p>Welcome to <strong>Hardware Ko Toh Boi!</strong>, your one-stop shop for all hardware needs since 1995. We take pride in offering high-quality tools and equipment that professionals and DIY enthusiasts trust.</p>
        <br>
        <p>Our mission is to provide reliable hardware solutions with exceptional customer service. With over 25 years of experience in the industry, we understand what our customers need and strive to exceed their expectations.</p>
        <br>
        <p>We source our products from reputable manufacturers and ensure that every item in our inventory meets our strict quality standards. Whether you're a professional contractor or a weekend warrior, we have the right tools for your project.</p>
        <br>
        <h3>Why Choose Us?</h3>
        <ul style="margin-left: 20px; margin-top: 10px;">
          <li>Premium quality products</li>
          <li>Competitive prices</li>
          <li>Expert advice and support</li>
          <li>Fast and reliable delivery</li>
          <li>Customer satisfaction guarantee</li>
        </ul>
      </div>
      <div class="about-image">
        <img src="https://i.postimg.cc/D05cwnLC/IMG-20251015-144433.jpg" alt="Hardware Store">
      </div>
    </div>
  </div>
  
  <div class="contact-section" id="contact">
    <h2 class="section-title">Contact Us</h2>
    <div class="contact-content">
      <div class="contact-info">
        <p>Have questions or need assistance? We're here to help! Reach out to us through any of the following methods:</p>
        <br>
        <div class="contact-item">
          <div class="contact-icon">
            <i class="fas fa-map-marker-alt"></i>
          </div>
          <div>
            <h4>Our Location</h4>
            <p>Basta Dyan Lang,hanapin mo nalang</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">
            <i class="fas fa-phone"></i>
          </div>
          <div>
            <h4>Call Us</h4>
            <p>+63 912 345 6789</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">
            <i class="fas fa-envelope"></i>
          </div>
          <div>
            <h4>Email Us</h4>
            <p>info@hardwarekotohboi.com</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">
            <i class="fas fa-clock"></i>
          </div>
          <div>
            <h4>Store Hours</h4>
            <p>Monday - Saturday: 8:00 AM - 8:00 PM</p>
            <p>Sunday: 9:00 AM - 5:00 PM</p>
          </div>
        </div>
      </div>
      <div class="contact-form">
        <form id="contactForm">
          <div class="form-group">
            <label for="name">Your Name</label>
            <input type="text" id="name" class="form-control" required>
          </div>
          <div class="form-group">
            <label for="email">Your Email</label>
            <input type="email" id="email" class="form-control" required>
          </div>
          <div class="form-group">
            <label for="subject">Subject</label>
            <input type="text" id="subject" class="form-control" required>
          </div>
          <div class="form-group">
            <label for="message">Your Message</label>
            <textarea id="message" class="form-control" rows="5" required></textarea>
          </div>
          <button type="submit" class="submit-btn">Send Message</button>
        </form>
      </div>
    </div>
  </div>
</div>

<footer>
  <div class="footer-content">
    <div class="footer-column">
      <h3>Hardware Ko Toh Boi!</h3>
      <p>Your trusted partner for quality tools and hardware since 1995. We provide the best products and services for all your hardware needs.</p>
      <div class="social-links">
        <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
        <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
        <a href="#" class="social-link"><i class="fab fa-youtube"></i></a>
      </div>
    </div>
    <div class="footer-column">
      <h3>Quick Links</h3>
      <ul class="footer-links">
        <li><a href="#products">Products</a></li>
        <li><a href="#about">About Us</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Delivery Information</a></li>
      </ul>
    </div>
    <div class="footer-column">
      <h3>Customer Service</h3>
      <ul class="footer-links">
        <li><a href="#">FAQ</a></li>
        <li><a href="#">Return Policy</a></li>
        <li><a href="#">Warranty</a></li>
        <li><a href="#">Payment Methods</a></li>
        <li><a href="#">Track Your Order</a></li>
      </ul>
    </div>
  </div>
  <div class="copyright">
    <p>&copy; 2023 Hardware Ko Toh Boi! - All rights reserved</p>
  </div>
</footer>

</body>
</html>
